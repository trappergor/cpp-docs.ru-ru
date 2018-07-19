---
title: Вызов неуправляемых функций из управляемого кода | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- native functions called from managed code [C++]
- managed code [C++], interoperability
- platform invoke [C++], interoperability
- interoperabiliy [C++], calling native functions from managed code
- calling native functions from managed code
- interop [C++], calling native functions from managed code
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c0d7e69c95790122f44dc59d06f2843afbddfb2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112047"
---
# <a name="calling-native-functions-from-managed-code"></a>Вызов неуправляемых функций из управляемого кода
Общеязыковая среда выполнения предоставляет службы вызова платформы или PInvoke, позволяющая управляемому коду вызывать функции в стиле языка C в собственные динамической библиотеки (DLL). Такой же маршалинг данных применяется и для COM-взаимодействие со средой выполнения и для механизма «Это просто работает» или IJW.  
  
 Дополнительные сведения:  
  
-   [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
-   [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [Подробный обзор вызова неуправляемого кода](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
  
 Примеры в этом разделе, иллюстрируют способ `PInvoke` может использоваться. `PInvoke` можно упростить маршалинг подготовленных данных, поскольку при этом предоставляется информация о маршалинге декларативно в атрибутах вместо написания кода процедуры маршалинга.  
  
> [!NOTE]
>  Библиотека маршалинга предоставляет альтернативный способ маршалинга данных между машинным и управляемым средами оптимальным образом. В разделе [Обзор из маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md) Дополнительные сведения о библиотеке маршалинга. Библиотека маршалинга используется только для данных, а не для функций.  
  
## <a name="pinvoke-and-the-dllimport-attribute"></a>PInvoke и атрибут DllImport  
 В следующем примере показано использование `PInvoke` в программе Visual C++. Помещает собственной функции определяется в msvcrt.dll. Атрибут DllImport используется для объявления помещает.  
  
```  
// platform_invocation_services.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", CharSet=CharSet::Ansi)]  
extern "C" int puts(String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 Следующий пример эквивалентен предыдущего примера, но использует IJW.  
  
```  
// platform_invocation_services_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#include <stdio.h>  
  
int main() {  
   String ^ pStr = "Hello World!";  
   char* pChars = (char*)Marshal::StringToHGlobalAnsi(pStr).ToPointer();   
   puts(pChars);  
  
   Marshal::FreeHGlobal((IntPtr)pChars);  
}  
```  
  
### <a name="advantages-of-ijw"></a>Преимущества использования IJW  
  
-   Нет необходимости писать `DLLImport` атрибут объявления для неуправляемых API, используемые программой. Просто включите файл заголовка и связи с библиотекой импорта.  
  
-   Механизм IJW работает немного быстрее (например, заглушки IJW не требуют проверки для необходимых для ПИН-кода или копирования элементов данных, поскольку оно выполняется явно разработчиком).  
  
-   Это четко иллюстрирует проблем с производительностью. В этом случае тот факт, что выполняется преобразование строки Юникода в строку ANSI и которые имеют помощника выделение и освобождение памяти. В этом случае разработчик пишет код с использованием IJW, поймет, что вызов `_putws` и с помощью `PtrToStringChars` бы удобнее использовать для повышения производительности.  
  
-   При вызове метода много неуправляемых API, использующих те же данные маршалинга их один раз и передача копии выполняется гораздо эффективнее, чем повторный маршалинг.  
  
### <a name="disadvantages-of-ijw"></a>Недостатки IJW  
  
-   Маршалинг необходимо указывать явно в коде, а не по атрибутам (которые часто используют значения по умолчанию).  
  
-   Код маршалинга является встроенным образом, где более активным в потоке логику приложения.  
  
-   Поскольку API-интерфейсы явного маршалинга возвращают `IntPtr` типы для обеспечения переносимости 32-разрядной на 64-разрядную версию, необходимо использовать дополнительные `ToPointer` вызовов.  
  
 Конкретный метод, представленный в C++ является более эффективный и явный метод за счет некоторые трудности.  
  
 Если в приложении используется главным образом неуправляемые типы данных или если она вызывает больше неуправляемых API, чем API платформы .NET Framework, рекомендуется, можно использовать функцию IJW. Для вызова отдельного неуправляемого API в основном управляемое приложение, выбор является более сложной.  
  
## <a name="pinvoke-with-windows-apis"></a>PInvoke с интерфейсами API Windows  
 PInvoke удобно вызывать функции в Windows.  
  
 В этом примере программы Visual C++ взаимодействует с функцией MessageBox, является частью API-интерфейса Win32.  
  
```  
// platform_invocation_services_4.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
typedef void* HWND;  
[DllImport("user32", CharSet=CharSet::Ansi)]  
extern "C" int MessageBox(HWND hWnd, String ^ pText, String ^ pCaption, unsigned int uType);  
  
int main() {  
   String ^ pText = "Hello World! ";  
   String ^ pCaption = "PInvoke Test";  
   MessageBox(0, pText, pCaption, 0);  
}  
```  
  
 Результатом является окно сообщения с заголовком PInvoke теста и содержит текст Hello World!.  
  
 Сведения о маршалинге также используется PInvoke для поиска функций в библиотеке DLL. В библиотеке user32.dll может фактически функции MessageBox, но не CharSet = включить CharSet::Ansi PInvoke для использования вместо MessageBoxW, которая является версией Юникода MessageBoxA в формате ANSI. Как правило рекомендуется использовать версии Юникода неуправляемых API, поскольку, исключает преобразования из собственного формата Юникода строковых объектов .NET Framework в ANSI.  
  
## <a name="when-not-to-use-pinvoke"></a>Когда не следует использовать PInvoke  
 С помощью PInvoke подходит не для всех функций C-стиле, в библиотеках DLL. Например предположим, что имеется функция MakeSpecial mylib.dll объявляется следующим образом:  
  
 `char * MakeSpecial(char * pszString);`  
  
 Если PInvoke используется в приложениях Visual C++, можно написать примерно следующего содержания:  
  
 `[DllImport("mylib")]`  
  
 `extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);`  
  
 Трудность здесь заключается в том, что мы не можем удалить память для неуправляемых строк, возвращаемых MakeSpecial. Другие функции, вызываемые посредством PInvoke вернуть указатель на внутренний буфер, который не должен быть освобождена пользователем. В этом случае с помощью функции IJW является очевидным выбором.  
  
## <a name="limitations-of-pinvoke"></a>Ограничения PInvoke  
 Нельзя вернуть точно тот же указатель из неуправляемой функции, которая была взята в качестве параметра. Если неуправляемая функция возвращает указатель, который был передан на него посредством PInvoke, может возникнуть повреждение памяти и исключения.  
  
```  
__declspec(dllexport)  
char* fstringA(char* param) {  
   return param;  
}  
```  
  
 Следующий пример иллюстрирует эту проблему, и несмотря на то, что программа может показаться для предоставления правильных выходных данных, выходные данные поступают из памяти, которые усечены.  
  
```  
// platform_invocation_services_5.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
#include <limits.h>  
  
ref struct MyPInvokeWrap {  
public:  
   [ DllImport("user32.dll", EntryPoint = "CharLower", CharSet = CharSet::Ansi) ]  
   static String^ CharLower([In, Out] String ^);  
};  
  
int main() {  
   String ^ strout = "AabCc";  
   Console::WriteLine(strout);  
   strout = MyPInvokeWrap::CharLower(strout);  
   Console::WriteLine(strout);  
}  
```  
  
## <a name="marshaling-arguments"></a>Маршалинг аргументов  
 С `PInvoke`, необходим без маршалирования между управляемыми и неуправляемыми примитивными типами C++ одной формы. Например без маршалирования необходим между Int32 и int или между Double и double.  
  
 Тем не менее необходимо выполнить маршалинг типов, которые имеют ту же форму. Сюда входят типы, char, строки и структуры. В следующей таблице показаны сопоставления, используемые модулем маршалера для различных типов:  
  
|Wtypes.h|Visual C++|Visual C++ с параметром/CLR|Среда CLR|  
|--------------|------------------|-----------------------------|-----------------------------|  
|HANDLE|void *|void *|IntPtr UIntPtr|  
|BYTE|unsigned char|unsigned char|Byte|  
|SHORT|short|short|Int16|  
|WORD|unsigned short|unsigned short|UInt16|  
|INT|int|int|Int32|  
|UINT|unsigned int|unsigned int|UInt32|  
|LONG|long|long|Int32|  
|BOOL|long|bool|Boolean|  
|DWORD|unsigned long|unsigned long|UInt32|  
|ULONG|unsigned long|unsigned long|UInt32|  
|CHAR|char|char|Char|  
|LPCSTR|char *|Строка ^ [in], StringBuilder ^ [в, out]|Строка ^ [in], StringBuilder ^ [в, out]|  
|LPCSTR|const char *|Строка ^|String|  
|LPWSTR|wchar_t *|Строка ^ [in], StringBuilder ^ [в, out]|Строка ^ [in], StringBuilder ^ [в, out]|  
|LPCWSTR|const wchar_t *|Строка ^|String|  
|FLOAT|float|float|Single|  
|DOUBLE|double|double|Double|  
  
 Маршалер фиксирует память, выделенную в куче среды выполнения, если адрес передается в неуправляемую функцию. Фиксирование не позволяет сборщику мусора Перемещение выделенного блока памяти в процессе сжатия.  
  
 В примере, показанном выше в этом разделе, параметр CharSet DllImport указывает строки как управляемый маршалинга; в этом случае это должно выполняться в строки ANSI для неуправляемой стороны.  
  
 Можно указать сведения о маршалинге для отдельных аргументов функций машинного кода с помощью атрибута MarshalAs. Существует несколько вариантов маршалинг строки * аргумент: BStr, ANSIBStr, TBStr, LPStr, LPWStr и LPTStr. Значение по умолчанию — LPStr.  
  
 В этом примере строка маршалируется как двухбайтовые символьной строки в Юникоде, LPWStr. Выходные данные — первая буква Hello World! Поскольку второй байт строки имеет значение null и помещает интерпретирует это как конец строки маркера.  
  
```  
// platform_invocation_services_3.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[DllImport("msvcrt", EntryPoint="puts")]  
extern "C" int puts([MarshalAs(UnmanagedType::LPWStr)] String ^);  
  
int main() {  
   String ^ pStr = "Hello World!";  
   puts(pStr);  
}  
```  
  
 Атрибут MarshalAs находится в пространстве имен System::Runtime::InteropServices. Атрибут можно использовать с другими типами данных, таких как массивы.  
  
 Как упоминалось выше, библиотека маршалинга предоставляет новый и оптимизированный способ маршалинга данных между средами управляемого и неуправляемого. Дополнительные сведения см. в разделе [Обзор из маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md).  
  
## <a name="performance-considerations"></a>Особенности производительности  
 PInvoke включает служебные данные в объеме от 10 до 30 x86 инструкций на вызов. Помимо этого фиксированные издержки маршалинга создает дополнительные издержки. Нет никаких маршалинга затрат между преобразуемые типы, которые имеют одинаковое представление в управляемом и неуправляемом коде. Например нет никаких затрат для преобразования между int и Int32.  
  
 Для повышения производительности имеют меньше вызовов PInvoke маршалировать объема данных, возможно, а не несколько вызовов, которые маршалировать меньшего объема данных на один вызов.  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)