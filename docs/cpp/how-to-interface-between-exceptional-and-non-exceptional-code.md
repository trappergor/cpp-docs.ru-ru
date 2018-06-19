---
title: 'Как: интерфейс между кодом с исключениями и без поддержки исключений | Документы Microsoft'
ms.custom: how-to
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2cf2216ba75912520f744f0f0331a50520aa895
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417279"
---
# <a name="how-to-interface-between-exceptional-and-non-exceptional-code"></a>Практическое руководство. Интерфейс между кодом с исключениями и без исключений
В этой статье описываются способы реализации согласованной обработки исключений в модуль C++, а также способ преобразования этих исключений в и из кодов ошибок на границах исключение.  
  
 Иногда приходится модуля C++ интерфейс с кодом, который не использует исключения (код без поддержки исключений). Такой интерфейс называется *границ исключение*. Например, можно вызвать функцию Win32 `CreateFile` в программе C++. `CreateFile` не создавать исключения; Вместо этого он задает коды ошибок, которые можно получить с `GetLastError` функции. Если программы C++ является нетривиальной, затем в нем вы, вероятно, предпочитают согласованные политики обработки ошибок на исключение. И, возможно, не требуется прервать исключения только потому, что интерфейс с кодом без поддержки исключений, и не хотите смешивать политики на основе исключения и исключение основанным ошибок модуля в C++.  
  
## <a name="calling-non-exceptional-functions-from-c"></a>Вызов функции без поддержки исключений из C++  
 При вызове функции без поддержки исключений C++, идея состоит в том, чтобы заключать этой функции в функции C++, обнаруживаются ошибки и возможно вызывает исключение. При создании функции-оболочки, сначала решить, какой тип исключения гарантии для предоставления: нет throw, строгое или basic. Во-вторых разработать функции, таким образом, чтобы все ресурсы, например, дескрипторов файлов, освобождаются правильно в том случае, если возникает исключение. Как правило это означает, использовать интеллектуальные указатели или аналогичные диспетчеров ресурсов на ресурсы. Дополнительные сведения о проектировании отчетов см. в разделе [как: проектирования в целях безопасности исключение](../cpp/how-to-design-for-exception-safety.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано функции C++, использующих Win32 `CreateFile` и `ReadFile` функции внутренне для открытия и чтения два файла.  `File` Класс является получением ресурса является инициализация (RAII) оболочку для дескрипторов файлов. Его конструктор определяет условие «файл не найден» и выдает исключение распространение ошибки вверх по стеку вызовов модуля C++ (в этом примере `main()` функции). Если исключение после `File` объект полностью создан, автоматически вызывает деструктор `CloseHandle` для освобождения дескриптора файла. (При желании можно использовать Active Template Library (ATL) `CHandle` класса для этой же цели или `unique_ptr` вместе с пользовательский метод удаления.) Функции, которые вызывают Win32 и API CRT выявить ошибки и затем создает исключений C++, с помощью локально определенные `ThrowLastErrorIf` функции, которая в свою очередь использует `Win32Exception` класс, производный от `runtime_error` класса. Все функции в этом примере позволяет гарантировать надежный исключение; Если в любой момент в этих функциях, создается исключение, состояние программы, не изменяется и утечки ресурсов.  
  
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
            cout << "*** Files are different." << endl;  
        } else {  
            cout<< "*** Files match." << endl;  
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
  
## <a name="calling-exceptional-code-from-non-exceptional-code"></a>Вызов исключительные кода из кода без исключений  
 Функции C++, которые объявлены как «"extern C"» может быть вызван C программы. C++ COM-серверы могут использоваться код, написанный на любом из нескольких различных языков. При реализации открытые функции поддержкой исключений в C++ вызывать код без поддержки исключений, функция C++ не должно допускать любые исключения, распространяются обратно в вызывающий объект. Таким образом функция C++ необходимо специально перехватить каждое исключение, он знает, как обрабатывать и, при необходимости, преобразовывать исключение код ошибки, который понимает вызывающего объекта. Если не все возможные исключения известны, функция C++ должны иметь `catch(...)` блок в соответствии с последним обработчиком. В этом случае лучше отчетов Неустранимая ошибка вызывающему объекту, так как приложение может находиться в неизвестном состоянии.  
  
 В следующем примере показано функцию, которая предполагает, что любое исключение, которое может быть создано Win32Exception или тип исключения, производного от `std::exception`. Функция перехватывает все исключения из этих типов и распространяет сведения об ошибке, как код ошибки Win32 в вызывающий объект.  
  
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
  
 При преобразовании из-за исключений коды ошибок, одна возможная проблема заключается том коды ошибок часто не содержит полноты информации, который может хранить исключение. Для решения этой проблемы можно предоставить `catch` блок для каждой определенный тип исключения, исключение может создаваться и ведение журнала для записи подробности исключения до преобразования в код ошибки. Этот подход можно создать много повторяющийся код, если несколько функций все использовать тот же набор `catch` блоков. Чтобы избежать повторения кода, рекомендуется командой рефакторинга этих блоков в одну функцию частной служебная программа, реализующая `try` и `catch` блокирует и принимает объект функции, который вызывается в `try` блока. В каждой общей функции передается код функции программы как лямбда-выражение.  
  
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
  
 В следующем примере показан способ записи лямбда-выражение, определяющее функтор. Если определен как «встроенный» функтором с помощью лямбда-выражение, часто бывает легче читать, чем если бы он был оформлен в виде функции по имени объекта.  
  
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
 [Обработка ошибок и исключений](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Практическое руководство. Разработка с учетом безопасности исключений](../cpp/how-to-design-for-exception-safety.md)