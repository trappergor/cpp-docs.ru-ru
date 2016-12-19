---
title: "Практическое руководство. Интерфейс между кодом с исключениями и без исключений | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Интерфейс между кодом с исключениями и без исключений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе описываются способы реализации согласованной обработки исключений в модуле C\+\+, а также, как перевести те исключения и наоборот кодов ошибок в диапазоне исключения.  
  
 Иногда модуль C\+\+ интерфейс с кодом, не использует исключения \(неисключительный код\).  Такой интерфейс как *граница исключения*.  Например, может потребоваться вызов функции `CreateFile` Win32 в программе C C\+\+.  `CreateFile` не создает исключения; вместо этого он задает коды ошибок, которые могут быть получены функцией `GetLastError`.  Если в программе C\+\+ нетривиальна, в которой возможно, необходимости иметь последовательной обработки ошибок исключений на основе политики.  , Не смогут отказаться исключения только потому, что интерфейс неисключительным с кодом, и ни одного требуется смешивания исключений и ошибок не\-исключение\- политики на основе в модуле C C\+\+.  
  
## Вызов не исключительные функции C из C\+\+  
 При вызове функции не исключительная в C\+\+, рекомендуется создать эту функцию в функции C\+\+, обнаруживает каких\-либо ошибок и затем, возможно, возникает исключение.  При разработке такую функцию оболочки, сначала определите тип исключения, которое будет представлен:  не запущенные, строгую или базовый.  Во\-вторых, создайте функцию так, чтобы все ресурсы, например дескрипторы файлов, правильно будут освобождены при возникновении исключения.  Как правило, это означает, что используется интеллектуального указателя или похожие диспетчеры ресурсов к собственному ресурсы.  Конструктивные соображения Дополнительные сведения о см. в разделе [Практическое руководство. Разработка с учетом безопасности исключений](../cpp/how-to-design-for-exception-safety.md).  
  
### Пример  
 В следующем примере показаны функции C\+\+, которые используют Win32 `CreateFile` и функции `ReadFile` внутренне для открытия и считывания 2 файла.  Класс `File` получение ресурса программа\-оболочка \(RAII\) для инициализации дескрипторов файлов.  Его конструктора определяет состояние файла «,» и создает исключение для распространения ошибку вверх по стеку вызовов модуля C\+\+ \(в этом примере, функции `main()` \).  Если исключение создается, после создания объекта `File` полностью построен, деструктор автоматически вызывает `CloseHandle` для освобождения дескриптора файла. \(При необходимости можно использовать класс \(ATL\) `CHandle` библиотеку шаблонных классов ATL для этой одной цели, или `unique_ptr` вместе с пользовательским deleter\). Функции, вызывающие Win32 API CRT и обнаружение ошибок и затем вызывают исключений с помощью локально определенной функции `ThrowLastErrorIf`, C\+\+, в свою очередь, используется класс `Win32Exception`, производную от класса `runtime_error`.  Все функции в этом примере предоставляют сильную гарантию исключения; если исключение создается в любой момент в эти функции, то остальные ресурсы не протекаены и нет состояния программы не изменяется.  
  
```cpp  
// compile with: /EHsc  
#include <Windows.h>  
#include <stdlib.h>  
#include <vector>  
#include <iostream>  
#include <string>  
#include <limits>  
#include <stdexcept>  
  
using namespace std;  
  
string FormatErrorMessage(DWORD error, const string& msg)  
{  
    static const int BUFFERLENGTH = 1024;  
    vector<char> buf(BUFFERLENGTH);  
    FormatMessageA(FORMAT_MESSAGE_FROM_SYSTEM, 0, error, 0, buf.data(),   
        BUFFERLENGTH - 1, 0);   
    return string(buf.data()) + "   ("  + msg  + ")";  
}  
  
class Win32Exception : public runtime_error  
{      
private:  
    DWORD m_error;  
public:  
    Win32Exception(DWORD error, const string& msg)  
        : runtime_error(FormatErrorMessage(error, msg)), m_error(error) { }  
  
    DWORD GetErrorCode() const { return m_error; }  
};  
  
void ThrowLastErrorIf(bool expression, const string& msg)   
{   
    if (expression) {   
        throw Win32Exception(GetLastError(), msg);   
    }   
}   
  
class File  
{  
private:  
    HANDLE m_handle;  
  
    // Declared but not defined, to avoid double closing.  
    File& operator=(const File&);  
    File(const File&);  
public:  
    explicit File(const string& filename)   
    {  
        m_handle = CreateFileA(filename.c_str(), GENERIC_READ, FILE_SHARE_READ,   
            nullptr, OPEN_EXISTING, FILE_ATTRIBUTE_READONLY, nullptr);  
        ThrowLastErrorIf(m_handle == INVALID_HANDLE_VALUE,   
            "CreateFile call failed on file named " + filename);  
    }  
  
    ~File() { CloseHandle(m_handle); }  
  
    HANDLE GetHandle() { return m_handle; }  
};  
  
size_t GetFileSizeSafe(const string& filename)  
{  
    File fobj(filename);  
    LARGE_INTEGER filesize;  
  
    BOOL result = GetFileSizeEx(fobj.GetHandle(), &filesize);  
    ThrowLastErrorIf(result == FALSE, "GetFileSizeEx failed: " + filename);  
  
    if (filesize.QuadPart < (numeric_limits<size_t>::max)()) {  
        return filesize.QuadPart;  
    } else {  
        throw;   
    }  
}  
  
vector<char> ReadFileVector(const string& filename)  
{  
    File fobj(filename);  
    size_t filesize = GetFileSizeSafe(filename);  
    DWORD bytesRead = 0;  
  
    vector<char> readbuffer(filesize);  
  
    BOOL result = ReadFile(fobj.GetHandle(), readbuffer.data(), readbuffer.size(),   
        &bytesRead, nullptr);  
    ThrowLastErrorIf(result == FALSE, "ReadFile failed: " + filename);  
  
    cout << filename << " file size: " << filesize << ", bytesRead: "   
        << bytesRead << endl;  
  
    return readbuffer;  
}  
  
bool IsFileDiff(const string& filename1, const string& filename2)   
{  
    return ReadFileVector(filename1) != ReadFileVector(filename2);  
}   
  
#include <iomanip>  
  
int main ( int argc, char* argv[] )  
{  
    string filename1("file1.txt");  
    string filename2("file2.txt");  
  
    try  
    {  
        if(argc > 2) {  
            filename1 = argv[1];  
            filename2 = argv[2];  
        }   
  
        cout << "Using file names " << filename1 << " and " << filename2 << endl;  
  
        if (IsFileDiff(filename1, filename2)) {  
            cout << "*** Files are different." << endl;  
        } else {  
            cout<< "*** Files match." << endl;  
        }  
    }  
    catch(const Win32Exception& e)  
    {          
        ios state(nullptr);  
        state.copyfmt(cout);  
        cout << e.what() << endl;  
        cout << "Error code: 0x" << hex << uppercase << setw(8) << setfill('0')   
            << e.GetErrorCode() << endl;  
        cout.copyfmt(state); // restore previous formatting  
    }  
}  
  
```  
  
## Вызов кода из кода неисключительного исключительный  
 Функция C\+\+, объявленные как extern «C» могут вызываться для программ на языке C — программами.  Серверы модели COM C\+\+ могут использоваться в коде, созданном на любом из нескольких различных языков.  При реализации функции общего исключения языковых в C\+\+, который будет вызывать неисключительный код функции C\+\+ не может разрешить все исключения для распространения обратно вызывающему объекту.  Поэтому функция C\+\+ должна определить каждое исключение, он знает, как обрабатывать и, при необходимости, преобразует исключение в код ошибки, который понимает вызывающий объект.  Если не все возможные исключения известно, что функция C\+\+ должна содержать блок `catch(…)` последний обработчик.  В таком случае лучше уведомить неустранимую ошибку в вызывающий объект, так как программа может находиться в неизестном состоянии.  
  
 В следующем примере показаны функции, высказывать любые исключения, исключение может создаваться или Win32Exception или тип исключения, производный от `std::exception`.  Функция перехватывающий любые исключения этих типов и распространяет сведения об ошибке как код ошибки Win32 вызывающему объекту.  
  
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
  
 При преобразовании из исключений в ошибки кодам, одна потенциальная проблема, коды ошибок не всего богатства часто содержат сведения, исключение может хранить.  Чтобы исправить это, можно предоставить блок `catch` для каждого конкретного типа исключения, которое может быть возникает и запустите средство ведения журнала, чтобы записать данные исключения до его преобразования в код ошибки.  Этот подход может создать много повторение кода, если несколько функций, используется один и тот же набор блоков `catch`.  Удобный способ избежать повторения кода, выполнять эти блоки в одну включить функцию удобство использования, реализующий блоки `try` и `catch` и принимает объект функции, который вызывается в блоке `try`.  В каждой открытой функции, передайте код для удобства использования функции как лямбда\-выражение.  
  
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
  
 В следующем примере показано, как создать лямбда\-выражение, которое определяет функтором.  Если указано функтором «и» с помощью лямбда\-выражения, часто проще читать, чем его, если он был записан как объект именем функции.  
  
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
  
 Дополнительные сведения о лямбда\-выражениях см. в разделе [Лямбда\-выражения](../cpp/lambda-expressions-in-cpp.md).  
  
## См. также  
 [Обработка ошибок и исключений](../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Практическое руководство. Разработка с учетом безопасности исключений](../cpp/how-to-design-for-exception-safety.md)