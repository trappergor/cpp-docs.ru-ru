---
title: "Вызов неуправляемых функций из управляемого кода | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "вызов неуправляемых функций из управляемого кода"
  - "взаимодействие [C++], вызов неуправляемых функций из управляемого кода"
  - "взаимодействие [C++], вызов неуправляемых функций из управляемого кода"
  - "управляемого кода [C++], взаимодействие"
  - "неуправляемые функции, вызванные из управляемого кода [C++]"
  - "вызов неуправляемого кода [C++], взаимодействие"
ms.assetid: 982cef18-20d9-42b4-8242-a77fa65f2e36
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Вызов неуправляемых функций из управляемого кода
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Среда CLR предоставляет службы вызова неуправляемого кода, которые позволяют управляемому коду вызывать функции в формате С в библиотеках динамической компоновки \(DLL\), содержащих машинный код.  Такой же маршалинг данных применяется и для COM\-взаимодействия со средой выполнения, и для механизма "It Just Works" \(IJW\).  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Использование явного вызова Pinvoke в C\+\+ \(атрибут DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
-   [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [A Closer Look at Platform Invoke](http://msdn.microsoft.com/ru-ru/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
  
 В примерах этого раздела показано, можно использовать `PInvoke`.  `PInvoke` может упростить маршалинг подготовленных данных, поскольку при этом предоставляется информация о маршалинге декларативно в атрибутах вместо написания кода процедуры маршалинга.  
  
> [!NOTE]
>  Библиотека маршалинга предоставляет альтернативный и оптимизированный способ маршалинга данных между неуправляемой и управляемой средами.  Дополнительные сведения о библиотеке маршалинга см. в разделе [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md).  Библиотека маршалинга используется только с данными, а не с функциями.  
  
## Вызов PInvoke и атрибут DllImport  
 В следующем примере показано применение вызова `PInvoke` в программе Visual C\+\+.  Неуправляемая функция puts определена в файле msvcrt.dll.  Атрибут DllImport используется для объявления функции puts.  
  
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
  
 Приведенный ниже пример эквивалентен предшествующему, но основан на IJW.  
  
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
  
### Преимущества использования IJW  
  
-   Нет необходимости писать объявления атрибута `DLLImport` для неуправляемых API, используемых программой.  Просто включите файл заголовка и ссылку с библиотекой импорта.  
  
-   Механизм IJW работает немного быстрее \(например, заглушки IJW не требуют проверки необходимости фиксации или копирования элементов данных, поскольку это делается разработчиком явно\).  
  
-   Это четко иллюстрирует аспект производительности.  В данном случае выполняется преобразование строки Юникода в строку ANSI и распределение и освобождение памяти.  Разработчик, пишущий код с использованием IJW, поймет, что вызов `_putws` и использование `PtrToStringChars` лучше с точки зрения производительности.  
  
-   Если вызвано много неуправляемых API, использующих те же данные, маршалинг копии выполняется гораздо эффективнее, чем повторный маршалинг.  
  
### Недостатки IJW  
  
-   Маршалинг должен быть явно указан в коде, а не с помощью атрибутов \(которые часто используют значения по умолчанию\).  
  
-   Код маршалинга является встроенным и потому более активным по отношению к логике приложения.  
  
-   Поскольку API\-интерфейсы явного маршалинга возвращают типы `IntPtr` для возможности переноса между 32\- и 64\-разрядными системами, необходимо использовать дополнительные вызовы `ToPointer`.  
  
 Конкретный метод, представленный в C\+\+, более эффективный и явный, но обеспечивается за счет дополнительного усложнения.  
  
 Если приложение большей частью использует неуправляемые типы данных или вызывает больше неуправляемых API, чем .NET Framework API, то рекомендуется использовать IJW.  Для вызова отдельного неуправляемого API при большинстве управляемых выбор более тонкий.  
  
## Вызов PInvoke с API\-интерфейсами Windows  
 PInvoke удобно использовать для вызова функций в Windows.  
  
 В приведенном примере программа Visual C\+\+ взаимодействует с функцией MessageBox, являющейся частью API\-интерфейса Win32.  
  
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
  
 Результат — окно сообщения с заголовком "PInvoke Test" и текстом "Hello World\!".  
  
 Информация о маршалинге также используется вызовом PInvoke для поиска функций в библиотеке DLL.  В файле user32.dll отсутствует функция MessageBox, но функция CharSet\=CharSet::Ansi позволяет PInvoke использовать MessageBoxA в версии ANSI вместо MessageBoxW, который является версией Юникода.  В общем случае, рекомендуется использовать версии Юникода неуправляемых API, поскольку это упраздняет необходимость преобразования из встроенного формата Юникода строковых объектов .NET Framework в ANSI.  
  
## Когда не следует использовать Pinvoke  
 Использование PInvoke приемлемо для всех функций в стиле С в библиотеках DLL.  Предположим, например, что в файле mylib.dll имеется функция MakeSpecial, объявленная следующим образом:  
  
 `char * MakeSpecial(char * pszString);`  
  
 Если PInvoke используется в приложениях Visual C\+\+, можно написать что\-то подобное следующему:  
  
 `[DllImport("mylib")]`  
  
 `extern "C" String * MakeSpecial([MarshalAs(UnmanagedType::LPStr)] String ^);`  
  
 Основная трудность здесь заключается в том, что мы не можем удалить память для неуправляемых строк, возвращаемых MakeSpecial.  Другие функции, вызываемые посредством Pinvoke, возвращают указатель на внутренний буфер, который пользователю освобождать не нужно.  В этом случае очевидным является выбор в пользу использования IJW.  
  
## Ограничения PInvoke  
 Невозможно вернуть точно тот же указатель из неуправляемой функции, которая была взята в качестве параметра.  Если неуправляемая функция возвращает указатель, который был передан посредством PInvoke, может возникнуть повреждение области памяти и исключения.  
  
```  
__declspec(dllexport)  
char* fstringA(char* param) {  
   return param;  
}  
```  
  
 Следующий пример иллюстрирует эту проблему. Хотя программа, как может показаться, выдает корректные результаты, результаты поступают из памяти, которая была освобождена.  
  
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
  
## Аргументы маршалинга  
 При использовании `PInvoke` маршалинг между управляемыми и неуправляемыми примитивными типами C\+\+ одной формы не требуется.  Например, между Int32 и int или между Double и double маршалинг не требуется.  
  
 Однако требуется маршалировать типы, которые не имеют одинаковую форму.  К ним относятся типы char, string и struct.  В приведенной ниже таблице показаны назначения, используемые маршалером в отношении различных типов.  
  
|wtypes.h|Visual C\+\+|Visual C\+\+ с \/clr|Среда CLR|  
|--------------|------------------|--------------------------|---------------|  
|HANDLE|void \*|void \*|IntPtr, UIntPtr|  
|BYTE|unsigned char|unsigned char|Byte|  
|SHORT|short|short|Int16|  
|WORD|unsigned short|unsigned short|UInt16|  
|INT|целое число|целое число|Int32|  
|UINT|unsigned int|unsigned int|UInt32|  
|LONG|long|long|Int32|  
|BOOL|long|bool|Boolean|  
|DWORD|unsigned long|unsigned long|UInt32|  
|ULONG|unsigned long|unsigned long|UInt32|  
|CHAR|char|char|Char|  
|LPCSTR|char \*|String ^ \[in\], StringBuilder ^ \[in, out\]|String ^ \[in\], StringBuilder ^ \[in, out\]|  
|LPCSTR|const char \*|String ^|Строковое|  
|LPWSTR|wchar\_t \*|String ^ \[in\], StringBuilder ^ \[in, out\]|String ^ \[in\], StringBuilder ^ \[in, out\]|  
|LPCWSTR|const wchar\_t \*|String ^|Строковое|  
|FLOAT|float|float|Single|  
|DOUBLE|double|double|Double|  
  
 Маршалер фиксирует память, выделенную для кучи среды выполения, если адрес передается к неуправляемой функции.  Фиксирование не позволяет сборщику мусора перемещать блоки памяти в процессе сжатия.  
  
 В приведенном ранее примере параметр CharSet атрибута DllImport указывает, как следует маршалировать управляемые строки; в данном случае это должно выполняться в строки ANSI для неуправляемой стороны.  
  
 Можно также указать сведения о маршалинге для отдельных аргументов неуправляемой функции, воспользовавшись атрибутом MarshalAs.  Есть несколько способов маршалинга аргумента String \*: BStr, ANSIBStr, TBStr, LPStr, LPWStr и LPTStr.  По умолчанию используется LPStr.  
  
 В этом примере строка маршалируется как строка двухбайтовых символов Юникода, LPWStr.  Вывод — это первая буква фразы "Hello World\!", поскольку второй байт строки нулевой, а функция puts интерпретирует это как маркер конца строки.  
  
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
  
 Атрибут MarshalAs находится в пространстве имен System::Runtime::InteropServices.  Этот атрибут может использоваться с другими типами данных, такими как массивы.  
  
 Как упоминалось выше, библиотека маршалинга предлагает новый и оптимизированный способ маршалинга данных между неуправляемыми и управляемыми средами.  Для получения дополнительной информации см. [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md).  
  
## Особенности производительности  
 PInvoke включает служебные данные в объеме от 10 до 30 инструкций x86 на вызов.  Кроме этого, процесс маршалинга создает дополнительные служебные данные.  Затраты на маршалинг данных между непреобразуемыми типами, имеющими одинаковые представления в управляемом и неуправляемом кодах, отсутствуют.  Например, при преобразовании между int и Int32 затраты отсутствуют.  
  
 Для более высокой производительности лучше иметь как можно меньше вызовов Pinvoke, осуществляющих маршалинг максимально возможного количества данных, вместо большего числа вызовов с обработкой меньшего количества данных на ячейку.  
  
## См. также  
 [Взаимодействие исходного кода и платформы.NET](../Topic/Native%20and%20.NET%20Interoperability.md)