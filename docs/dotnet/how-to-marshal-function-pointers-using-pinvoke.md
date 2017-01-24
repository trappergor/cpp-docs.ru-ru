---
title: "Практическое руководство. Указатели функций маршалирования, использующие PInvoke | Microsoft Docs"
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
  - "маршалинг данных [C++], обратные вызовы и делегаты"
  - "взаимодействие [C++], обратные вызовы и делегаты"
  - "маршалинг [C++], обратные вызовы и делегаты"
  - "вызов неуправляемого кода [C++], обратные вызовы и делегаты"
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Указатели функций маршалирования, использующие PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе объясняется, как использовать управляемые делегаты вместо указателей функций при взаимодействии с неуправляемыми функциями, которые используют возможности .NET Framework P\/Invoke.  Однако программистам Visual C\+\+ рекомендуется вместо этого использовать функции C\+\+ Interop \(где это возможно\), поскольку P\/Invoke предоставляет довольно короткий отчет об ошибках во время выполнения, не является типобезопасным и может потребовать много усилий при реализации.  Если неуправляемый интерфейс API упакован в виде библиотеки DLL, а исходный код недоступен, единственным вариантом является использование вызова P\/Invoke.  Дополнительные сведения по другим случаям см. в следующих разделах.  
  
-   [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [Практическое руководство. Маршалинг обратных вызовов и делегатов посредством C\+\+ Interop](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 Неуправляемые интерфейсы API, принимающие указатели функций в качестве аргументов, могут быть вызваны из управляемого кода с помощью управляемого делегата, а не собственно указателя.  Компилятор автоматически маршалирует делегат неуправляемым функциям как указатель функции и вставляет необходимый управляемый или неуправляемый код переноса.  
  
## Пример  
 В следующем примере кода представлены неуправляемый и управляемый модули.  Неуправляемый модуль — это библиотека DLL, которая определяет функцию TakesCallback, принимающую указатель функции.  Этот адрес используется для выполнения функции.  
  
 Управляемый модуль определяет делегат, который маршалируется машинному коду как указатель функции, и использует атрибут <xref:System.Runtime.InteropServices.DllImportAttribute> для предоставления собственной функции TakesCallback управляемому коду.  В главной функции создается экземпляр делегата, который затем передается функции TakesCallback.  В выходных данных программы видно, что эта функция выполняется собственной функцией TakesCallback.  
  
 Управляемая функция подавляет сбор мусора для управляемого делегата, чтобы воспрепятствовать перемещению делегата при сборе мусора .NET Framework во время выполнения собственной функции.  
  
 Управляемый модуль компилируется с параметром \/clr, также возможна компиляция с \/clr:pure.  
  
```  
// TraditionalDll5.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   /* Declare an unmanaged function type that takes two int arguments  
      Note the use of __stdcall for compatibility with managed code */  
   typedef int (__stdcall *CALLBACK)(int);  
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);  
}  
  
int TakesCallback(CALLBACK fp, int n) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n);  
}  
```  
  
```  
// MarshalDelegate.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
public delegate int GetTheAnswerDelegate(int);  
public value struct TraditionalDLL {  
   [DllImport("TraditionalDLL5.dll")]  
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);  
};  
  
int GetNumber(int n) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
   return x + n;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TraditionalDLL::TakesCallback(fp, 42);  
}  
```  
  
 Обратите внимание, что в управляемом коде никакие компоненты библиотеки DLL не предоставляются с помощью стандартной директивы \#include.  Фактически доступ к библиотеке DLL происходит только во время выполнения, поэтому проблемы с функциями, импортируемыми с помощью <xref:System.Runtime.InteropServices.DllImportAttribute> не обнаруживаются во время компиляции.  
  
## См. также  
 [Использование явного вызова Pinvoke в C\+\+ \(атрибут DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)