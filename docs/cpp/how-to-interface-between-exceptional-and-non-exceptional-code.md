---
title: Практическое руководство. Интерфейс между кодом с исключениями и без исключений
ms.custom: how-to
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
ms.openlocfilehash: b6da1142ee04668033a516f2c20c4a2354ff5598
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576687"
---
# <a name="how-to-interface-between-exceptional-and-non-exceptional-code"></a>Практическое руководство. Интерфейс между кодом с исключениями и без исключений

В этой статье описывается, как реализовать согласованную обработку исключений в модуль C++, а также способ преобразования этих исключений и из кодов ошибок на границах исключение.

Иногда приходится модуля C++ интерфейс с кодом, который не использует исключения (без исключений код). Такой интерфейс называется *границ исключение*. Например, необходимо вызвать функцию Win32 `CreateFile` в программе C++. `CreateFile` не создавать исключения; Вместо этого он задает коды ошибок, которые могут быть получены с `GetLastError` функции. Если программа C++ является нетривиальным, затем в ней, возможно, требуется, чтобы согласованную политику обработки ошибок основанной на исключении. И, возможно, не нужно отказаться от исключений, просто потому, что возможность взаимодействовать с кодом без поддержки исключений, и не хотите смешивать политики на основе исключения и исключение основанным ошибок модуля в C++.

## <a name="calling-non-exceptional-functions-from-c"></a>Вызов функции без поддержки исключений из C++

При вызове функции, без поддержки исключений с C++, суть программы-оболочки для этой функции в функции C++, которая обнаруживает все ошибки и затем, возможно, вызывает исключение. При создании функции-оболочки, сначала решить, какой тип гарантия исключения для предоставления: нет-throw, strong или basic. Во-вторых разработать функции, таким образом, чтобы все ресурсы, к примеру, дескрипторы файлов, освобождаются правильно в том случае, если создается исключение. Как правило это означает, что использовать интеллектуальные указатели и аналогичными диспетчерами ресурсов его владельцем ресурсов. Дополнительные сведения о рекомендациях по проектированию см. в разделе [как: разработка с учетом безопасности исключений](../cpp/how-to-design-for-exception-safety.md).

### <a name="example"></a>Пример

В следующем примере показано функции C++, использующие Win32 `CreateFile` и `ReadFile` функции, чтобы открыть и прочитать два файла.  `File` Класс является получение ресурса является инициализация (RAII) оболочку для дескрипторов файлов. Его конструктор определяет условие «файл не найден» и создает исключение для распространения ошибки вверх по стеку вызовов модуля C++ (в этом примере `main()` функции). Если исключение после `File` объект полностью создан, автоматически вызывает деструктор `CloseHandle` освободить дескриптор файла. (При желании можно использовать Active Template Library (ATL) `CHandle` класс для этой же цели или `unique_ptr` вместе с пользовательский метод удаления.) Функции, которые вызывают Win32 и CRT API обнаружения ошибок и затем вызывают исключения C++, с помощью локально определенные `ThrowLastErrorIf` функцию, которая в свою очередь использует `Win32Exception` класс, производный от `runtime_error` класса. Все функции в этом примере предоставляют надежная гарантия исключения; Если исключение создается в любой момент в этих функциях, утечки ресурсов и изменении ни одно состояние программы.

```cpp
// compile with: /EHsc
#include <Windows.h>
#include <stdlib.h>
#include <vector>
#include <iostream>
#include <string>
#include <limits>
#include <stdexcept>

using namespace std;

string FormatErrorMessage(DWORD error, const string& msg)
{
    static const int BUFFERLENGTH = 1024;
    vector<char> buf(BUFFERLENGTH);
    FormatMessageA(FORMAT_MESSAGE_FROM_SYSTEM, 0, error, 0, buf.data(),
        BUFFERLENGTH - 1, 0);
    return string(buf.data()) + "   ("  + msg  + ")";
}

class Win32Exception : public runtime_error
{
private:
    DWORD m_error;
public:
    Win32Exception(DWORD error, const string& msg)
        : runtime_error(FormatErrorMessage(error, msg)), m_error(error) { }

    DWORD GetErrorCode() const { return m_error; }
};

void ThrowLastErrorIf(bool expression, const string& msg)
{
    if (expression) {
        throw Win32Exception(GetLastError(), msg);
    }
}

class File
{
private:
    HANDLE m_handle;

    // Declared but not defined, to avoid double closing.
    File& operator=(const File&);
    File(const File&);
public:
    explicit File(const string& filename)
    {
        m_handle = CreateFileA(filename.c_str(), GENERIC_READ, FILE_SHARE_READ,
            nullptr, OPEN_EXISTING, FILE_ATTRIBUTE_READONLY, nullptr);
        ThrowLastErrorIf(m_handle == INVALID_HANDLE_VALUE,
            "CreateFile call failed on file named " + filename);
    }

    ~File() { CloseHandle(m_handle); }

    HANDLE GetHandle() { return m_handle; }
};

size_t GetFileSizeSafe(const string& filename)
{
    File fobj(filename);
    LARGE_INTEGER filesize;

    BOOL result = GetFileSizeEx(fobj.GetHandle(), &filesize);
    ThrowLastErrorIf(result == FALSE, "GetFileSizeEx failed: " + filename);

    if (filesize.QuadPart < (numeric_limits<size_t>::max)()) {
        return filesize.QuadPart;
    } else {
        throw;
    }
}

vector<char> ReadFileVector(const string& filename)
{
    File fobj(filename);
    size_t filesize = GetFileSizeSafe(filename);
    DWORD bytesRead = 0;

    vector<char> readbuffer(filesize);

    BOOL result = ReadFile(fobj.GetHandle(), readbuffer.data(), readbuffer.size(),
        &bytesRead, nullptr);
    ThrowLastErrorIf(result == FALSE, "ReadFile failed: " + filename);

    cout << filename << " file size: " << filesize << ", bytesRead: "
        << bytesRead << endl;

    return readbuffer;
}

bool IsFileDiff(const string& filename1, const string& filename2)
{
    return ReadFileVector(filename1) != ReadFileVector(filename2);
}

#include <iomanip>

int main ( int argc, char* argv[] )
{
    string filename1("file1.txt");
    string filename2("file2.txt");

    try
    {
        if(argc > 2) {
            filename1 = argv[1];
            filename2 = argv[2];
        }

        cout << "Using file names " << filename1 << " and " << filename2 << endl;

        if (IsFileDiff(filename1, filename2)) {
            cout << "+++ Files are different." << endl;
        } else {
            cout<< "=== Files match." << endl;
        }
    }
    catch(const Win32Exception& e)
    {
        ios state(nullptr);
        state.copyfmt(cout);
        cout << e.what() << endl;
        cout << "Error code: 0x" << hex << uppercase << setw(8) << setfill('0')
            << e.GetErrorCode() << endl;
        cout.copyfmt(state); // restore previous formatting
    }
}
```

## <a name="calling-exceptional-code-from-non-exceptional-code"></a>Вызов исключительных кода из кода без исключений

Функции C++, которые объявлены как «"extern C» могут быть вызваны программ на языке C. C++ COM-серверы могут использоваться код, написанный на любом из нескольких различных языков. При реализации открытого исключения с поддержкой функций в C++ вызывать код без поддержки исключений, функция C++ не должна разрешать исключения для распространения обратно вызывающему. Таким образом функция C++ необходимо специально перехвата всех исключений, он знает, как обрабатывать и, при необходимости преобразуйте исключение на код ошибки, который понимает вызывающий объект. Если известны не все возможные исключения, функция C++ должны иметь `catch(...)` блок в соответствии с последним обработчиком. В этом случае лучше сообщить Неустранимая ошибка вызывающему объекту, так как программа может находиться в неизвестном состоянии.

В следующем примере показано функцию, которая предполагает, что любое исключение, которое может создаваться Win32Exception или типом исключения, производного от `std::exception`. Функция перехватывает все исключения из этих типов и распространяет сведения об ошибке, как код ошибки Win32, вызывающей стороне.

```cpp
BOOL DiffFiles2(const string& file1, const string& file2)
{
    try
    {
        File f1(file1);
        File f2(file2);
        if (IsTextFileDiff(f1, f2))
        {
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);
            return FALSE;
        }
        return TRUE;
    }
    catch(Win32Exception& e)
    {
        SetLastError(e.GetErrorCode());
    }

    catch(std::exception& e)
    {
        SetLastError(MY_APPLICATION_GENERAL_ERROR);
    }
    return FALSE;
}
```

При преобразовании из-за исключений коды ошибок, одна потенциальная проблема — это, что коды ошибок часто не содержат полноты информации, который может хранить исключение. Чтобы решить эту проблему, можно предоставить **catch** блок для каждого определенного типа исключения, исключение может создаваться и ведение журнала для записи сведений о исключении, прежде чем он преобразуется в код ошибки. Этот подход можно создать повторы кода, если несколько функций все использовать тот же набор **catch** блоков. Чтобы избежать повторения кода, рекомендуется перепишет такие блоки в один закрытый служебную функцию, который реализует **попробуйте** и **catch** блокирует и принимает объект функции, который вызывается в **попробуйте** блока. В каждой общей функции передаете код служебную функцию как лямбда-выражение.

```cpp
template<typename Func>
bool Win32ExceptionBoundary(Func&& f)
{
    try
    {
        return f();
    }
    catch(Win32Exception& e)
    {
        SetLastError(e.GetErrorCode());
    }
    catch(const std::exception& e)
    {
        SetLastError(MY_APPLICATION_GENERAL_ERROR);
    }
    return false;
}
```

В следующем примере показан способ записи лямбда-выражение, определяющее функтор. Когда функтор определен как «встроенный» с помощью лямбда-выражения, часто бывает легче читать, чем было бы, если бы он был оформлен как объект именованные функции.

```cpp
bool DiffFiles3(const string& file1, const string& file2)
{
    return Win32ExceptionBoundary([&]() -> bool
    {
        File f1(file1);
        File f2(file2);
        if (IsTextFileDiff(f1, f2))
        {
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);
            return false;
        }
        return true;
    });
}
```

Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../cpp/lambda-expressions-in-cpp.md).

## <a name="see-also"></a>См. также

[Обработка ошибок и исключений](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Практическое руководство. Разработка с учетом безопасности исключений](../cpp/how-to-design-for-exception-safety.md)<br/>
