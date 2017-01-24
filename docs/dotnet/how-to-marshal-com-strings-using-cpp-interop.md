---
title: "Практическое руководство. Маршалирование строк COM с помощью взаимодействия C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "взаимодействие C++, строки"
  - "COM [C++], маршалинг строк"
  - "маршалинг данных [C++], строки"
  - "взаимодействие [C++], строки"
  - "маршалинг [C++], строки"
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Маршалирование строк COM с помощью взаимодействия C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе описывается порядок передачи строк BSTR \(основной формат строк в программировании с использованием модели COM\) между управляемыми и неуправляемыми функциями.  Дополнительные сведения о взаимодействии с другими строковыми типами см. в следующих разделах:  
  
-   [Практическое руководство. Маршалирование строк Юникода с использованием взаимодействия C\+\+](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Практическое руководство. Маршалирование строк ANSI с использованием взаимодействия C\+\+](../Topic/How%20to:%20Marshal%20ANSI%20Strings%20Using%20C++%20Interop.md)  
  
 В следующем примере кода используются директивы \#pragma [managed, unmanaged](../preprocessor/managed-unmanaged.md), которые встраивают управляемые и неуправляемые функции в один файл. Эти функции также взаимодействуют и в случае их распределения в отдельные файлы.  Файлы, содержащие только неуправляемые функции, не требуется компилировать с использованием параметра [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
 В следующем примере описывается порядок передачи строк BSTR \(формат строк в программировании с использованием модели COM\) из управляемой в неуправляемую функцию.  В вызывающей управляемой функции используется метод <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> для получения адреса представления содержимого строки .NET System.String в формате BSTR.  Этот указатель закрепляется с помощью функции [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md). Благодаря этому физический адрес указателя не изменяется в процессе сборки мусора при выполнении неуправляемой функции.  Сборщик мусора не освобождает память до тех пор, пока закрепленный с помощью функции [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md) указатель не выйдет за пределы области действия.  
  
```  
// MarshalBSTR1.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(BSTR bstr) {  
   printf_s("%S", bstr);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = "test string";  
  
   IntPtr ip = Marshal::StringToBSTR(s);  
   BSTR bs = static_cast<BSTR>(ip.ToPointer());  
   pin_ptr<BSTR> b = &bs;  
  
   NativeTakesAString( bs );  
   Marshal::FreeBSTR(ip);  
}  
```  
  
## Пример  
 В следующем примере описывается порядок передачи строк BSTR из неуправляемой в неуправляемую функцию.  В принимающей управляемой функции входная строка может использоваться непосредственно в формате BSTR или преобразовываться к типу <xref:System.String> с помощью метода <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> для использования в других управляемых функциях.  Поскольку память, представляющая строку BSTR, выделяется в неуправляемой куче, в которой не выполняется сборка мусора, закрепление не требуется.  
  
```  
// MarshalBSTR2.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedTakesAString(BSTR bstr) {  
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));  
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);  
}  
  
#pragma unmanaged  
  
void UnManagedFunc() {  
   BSTR bs = SysAllocString(L"test string");  
   printf_s("(unmanaged) passing BSTR to managed func...\n");  
   ManagedTakesAString(bs);  
}  
  
#pragma managed  
  
int main() {  
   UnManagedFunc();  
}  
```  
  
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)