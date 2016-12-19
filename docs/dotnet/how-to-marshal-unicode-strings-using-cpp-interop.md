---
title: "Практическое руководство. Маршалирование строк Юникода с использованием взаимодействия C++ | Microsoft Docs"
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
  - "маршалинг данных [C++], строки"
  - "взаимодействие [C++], строки"
  - "маршалинг [C++], строки"
  - "Юникод, маршалинг строк"
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Маршалирование строк Юникода с использованием взаимодействия C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе продемонстрирован еще один аспект возможностей взаимодействия Visual C\+\+.  Для получения дополнительной информации см. [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 В следующем примере кода используются директивы \#pragma [managed, unmanaged](../preprocessor/managed-unmanaged.md), которые встраивают управляемые и неуправляемые функции в один файл. Эти функции также взаимодействуют и в случае их распределения в отдельные файлы.  Файлы, содержащие только неуправляемые функции, не требуется компилировать с использованием параметра [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 В этом разделе показано, как можно передать строки Юникода от управляемой к управляемой функции и наоборот.  Дополнительные сведения о взаимодействии с другими строковыми типами см. в следующих разделах:  
  
-   [Практическое руководство. Маршалирование строк ANSI с использованием взаимодействия C\+\+](../Topic/How%20to:%20Marshal%20ANSI%20Strings%20Using%20C++%20Interop.md)  
  
-   [Практическое руководство. Маршалирование строк COM с помощью взаимодействия C\+\+](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
## Пример  
 Для передачи строки Юникода от управляемой функции к неуправляемой можно воспользоваться функцией PtrToStringChars \(объявленной в Vcclr.h\) для доступа к памяти, где хранится управляемая строка.  Поскольку этот адрес будет передан встроенной функции, важно, чтобы память была закреплена с помощью [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md) во избежание перемещения строковых данных в случае запуска цикла сбора мусора во время выполнения неуправляемой функции.  
  
```  
// MarshalUnicode1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const wchar_t* p) {  
   printf_s("(native) received '%S'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("test string");  
   pin_ptr<const wchar_t> str = PtrToStringChars(s);  
  
   Console::WriteLine("(managed) passing string to native func...");  
   NativeTakesAString( str );  
}  
```  
  
## Пример  
 Представленный ниже пример демонстрирует маршалинг данных, необходимый для доступа к строке Юникода в управляемой функции, вызванной неуправляемой функцией.  Управляемая функция, после получения встроенной строки Юникода, преобразует ее в управляемую строку, используя метод <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A>.  
  
```  
// MarshalUnicode2.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(wchar_t* s) {  
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);  
   Console::WriteLine("(managed) received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(unmanaged) calling managed func...\n";  
   ManagedStringFunc(L"test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)