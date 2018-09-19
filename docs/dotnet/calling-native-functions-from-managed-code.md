---
title: Вызов неуправляемых функций из управляемого кода | Документация Майкрософт
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
ms.openlocfilehash: 002093a6a9044c65e5780035ad6c19db35d6b648
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116754"
---
# <a name="calling-native-functions-from-managed-code"></a>Вызов неуправляемых функций из управляемого кода
Среда CLR предоставляет службы вызова неуправляемого или PInvoke, которая позволяет управляемому коду вызывать функции C-стиля в собственные библиотеки динамической компоновки (DLL). Такой же маршалинг данных применяется и для COM-взаимодействие со средой выполнения и для механизма «It Just Works» или IJW.  
  
 Дополнительные сведения:  
  
-   [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
-   [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
 В этом разделе примерах как `PInvoke` может использоваться. `PInvoke` может упростить маршалинг подготовленных данных, поскольку при этом предоставляется информация о маршалинге декларативно в атрибутах вместо написания кода процедуры маршалинга.  
  
> [!NOTE]
>  Библиотека маршалинга предоставляет альтернативный способ маршалинга данных между неуправляемыми и управляемыми средами оптимальным образом. См. в разделе [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md) Дополнительные сведения о библиотеке маршалинга. Библиотека маршалинга используется только для данных, а не для функций.  
  
## <a name="pinvoke-and-the-dllimport-attribute"></a>Вызов PInvoke и атрибут DllImport  
 В следующем примере показано использование `PInvoke` в программе Visual C++. Неуправляемая функция puts определена в файле msvcrt.dll. Атрибут DllImport используется для объявления функции puts.  
  
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
  
 Следующий пример эквивалентен предыдущего примера, но использует на IJW.  
  
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
  
-   Нет необходимости писать `DLLImport` объявления по неуправляемым API, программа использует атрибута. Достаточно включите файл заголовка и ссылку с библиотекой импорта.  
  
-   Механизм IJW работает немного быстрее (например, заглушки IJW не обязательно для проверки необходимости фиксации или копирования элементов данных из-за этого явно разработчиком).  
  
-   Он четко иллюстрирует аспект производительности. В этом случае тот факт, что вы переводите строки Юникода в строку ANSI и что у помощника выделение и освобождение памяти. В этом случае разработчик, пишущий код с использованием IJW, поймет, что вызов `_putws` и с помощью `PtrToStringChars` бы лучше для производительности.  
  
-   При вызове метода много неуправляемых API, использующих те же данные, маршалинг его один раз и передача копии выполняется гораздо эффективнее, чем повторный маршалинг.  
  
### <a name="disadvantages-of-ijw"></a>Недостатки IJW  
  
-   Маршалинг необходимо указывать явно в коде, а не по атрибутам (которые часто используют значения по умолчанию).  
  
-   Код маршалинга является встроенным, где более активным, в потоке логики приложения.  
  
-   Так как API-интерфейсы явного маршалинга возвращают `IntPtr` типов для обеспечения переносимости 32-разрядной на 64-разрядную версию, необходимо использовать дополнительные `ToPointer` вызовов.  
  
 Конкретный метод, представленный в C++ является метод более эффективный и явный, за счет дополнительного усложнения.  
  
 Если в приложении используется главным образом неуправляемые типы данных, или если он вызывает больше неуправляемых API, чем .NET Framework API, мы рекомендуем вам использовать функцию IJW. Для вызова отдельного неуправляемого API в основном управляемого приложения, выбор является более сложной.  
  
## <a name="pinvoke-with-windows-apis"></a>Вызов PInvoke с API-интерфейсов Windows  
 PInvoke удобно использовать для вызова функций в Windows.  
  
 В этом примере программы Visual C++ взаимодействует с функцией MessageBox, являющейся частью API-интерфейса Win32.  
  
```cpp  
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
  
 Выводится окно сообщения, которое имеет заголовок PInvoke Test и с текстом Hello World!.  
  
 Сведения о маршалинге также используется вызовом PInvoke для поиска функций в библиотеке DLL. В файле user32.dll отсутствует на самом деле нет функция MessageBox, но CharSet = CharSet:: ANSI позволяет PInvoke использовать MessageBoxA в версии ANSI вместо MessageBoxW, который является версией Юникода. Как правило рекомендуется использовать версии Юникода неуправляемых API, поскольку это упраздняет необходимость преобразования из встроенного формата Юникода строковых объектов .NET Framework в ANSI.  
  
## <a name="when-not-to-use-pinvoke"></a>Когда не следует использовать PInvoke  
 С помощью PInvoke подходит не для всех функций В стиле в библиотеках DLL. Например предположим, что имеется функция MakeSpecial в файле mylib.dll объявляется следующим образом:  
  
 `char * MakeSpecial(char * pszString);`  
  
 Если PInvoke используется в приложении Visual C++, можно написать что-то подобное следующему:  
  
```cpp
[DllImport("mylib")]
extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);
```
  
 Основная трудность здесь заключается в том, что мы не можем удалить память для неуправляемых строк, возвращаемых MakeSpecial. Другие функции, вызываемые посредством PInvoke возвращают указатель на внутренний буфер, который пользователю освобождать не нужно. В этом случае с помощью функции IJW является очевидным выбором.  
  
## <a name="limitations-of-pinvoke"></a>Ограничения PInvoke  
 Невозможно вернуть точно тот же указатель из неуправляемой функции, которая была взята в качестве параметра. Если неуправляемая функция возвращает указатель, который был передан на него посредством PInvoke, может возникнуть повреждение области памяти и исключения.  
  
```cpp  
__declspec(dllexport)  
char* fstringA(char* param) {  
   return param;  
}  
```  
  
 Следующий пример иллюстрирует эту проблему, и несмотря на то, что программа может показаться выдает корректные результаты, выходные данные поступают из памяти, которая была освобождена.  
  
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
 С помощью `PInvoke`, необходим не маршалинг между управляемыми и неуправляемыми примитивными типами C++ одной формы. Например маршалинг не является обязательным, между Int32 и int или между Double и double.  
  
 Однако требуется маршалировать типы, у которых нет той же форме. Сюда относятся типы char, string и struct. В следующей таблице показаны сопоставления, используемые маршалером для различных типов:  
  
|Wtypes.h|Visual C++|Visual C++ с параметром/CLR|Среда CLR|  
|--------------|------------------|-----------------------------|-----------------------------|  
|HANDLE|void \*|void \*|IntPtr, UIntPtr|  
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
|LPCSTR|Char \*|Строка ^ [in], StringBuilder ^ [в, out]|Строка ^ [in], StringBuilder ^ [в, out]|  
|LPCSTR|const char \*|Строка ^|String|  
|LPWSTR|wchar_t \*|Строка ^ [in], StringBuilder ^ [в, out]|Строка ^ [in], StringBuilder ^ [в, out]|  
|LPCWSTR|const wchar_t \*|Строка ^|String|  
|FLOAT|float|float|Single|  
|DOUBLE|double|double|Double|  
  
 Маршалер фиксирует память, выделенную в куче среды выполнения, если адрес передается к неуправляемой функции. Фиксирование не позволяет сборщику мусора перемещать блоки памяти во время сжатия.  
  
 В примере, показанном ранее в этом разделе, параметр CharSet атрибута DllImport указывает, как управляемые строки необходимо маршалировать; в этом случае это должно выполняться в строки ANSI для неуправляемой стороны.  
  
 Сведения о маршалинге для отдельных аргументов неуправляемой функции можно указать с помощью атрибута MarshalAs. Существует несколько способов маршалинга строка \* аргумент: BStr, ANSIBStr, TBStr, LPStr, LPWStr и LPTStr. По умолчанию используется LPStr.  
  
 В этом примере строка маршалируется как строку символов Юникода двухбайтовые, LPWStr. Выходные данные — первая буква Hello World! Поскольку второй байт строки имеет значение null и помещает интерпретирует это как маркер конец строки.  
  
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
  
 Атрибут MarshalAs находится в пространстве имен System::Runtime:: InteropServices. Атрибут может использоваться с другими типами данных, таких как массивы.  
  
 Как упоминалось выше, библиотека маршалинга предоставляет новый и оптимизированный способ маршалинга данных между неуправляемой и управляемой средами. Дополнительные сведения см. в разделе [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md).  
  
## <a name="performance-considerations"></a>Особенности производительности  
 PInvoke включает служебные данные в объеме от 10 до 30 x86 инструкций на вызов. Кроме этого, процесс маршалинга создает дополнительные издержки. Есть затраты на маршалинг между непреобразуемыми типами, имеющими одинаковые представления в управляемом и неуправляемом коде. Например имеется преобразовании между int и Int32 затраты отсутствуют.  
  
 Для повышения производительности имеют меньше вызовов PInvoke маршалинга столько данных, возможно, вместо большего, маршалинг меньше данных на один вызов.  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие исходного кода и платформы.NET](../dotnet/native-and-dotnet-interoperability.md)