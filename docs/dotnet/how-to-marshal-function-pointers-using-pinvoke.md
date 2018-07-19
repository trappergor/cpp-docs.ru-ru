---
title: 'Как: указатели функций маршалирования, использующие PInvoke | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1aa8da5e5b6931fb46ff283a5be15da5b2c7325d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132181"
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>Практическое руководство. Указатели функций маршалирования, использующие PInvoke
В этом разделе объясняется, как управляемый делегаты можно использовать вместо указателей функций при взаимодействии с неуправляемыми функциями с помощью функции .NET Framework P/Invoke. Тем не менее программистов Visual C++, рекомендуется использовать возможности взаимодействия C++ (когда это возможно), поскольку P/Invoke предоставляет мало времени компиляции сведений об ошибках, не является строго типизированным и может оказаться трудоемкой для реализации. Если неуправляемый интерфейс API упакован как библиотека DLL и исходный код недоступен, P/Invoke является единственным параметром. В противном случае см. в следующих разделах:  
  
-   [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [Практическое руководство. Маршалинг обратных вызовов и делегатов посредством взаимодействия C++](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 Неуправляемые интерфейсы API, принимающие указатели функций, как аргументы могут быть вызваны из управляемого кода с помощью управляемого делегата собственный указатель функции. Компилятор автоматически маршалирует делегат неуправляемым функциям как указатель функции и вставляет необходимости перехода управляемого и неуправляемого кода.  
  
## <a name="example"></a>Пример  
 Следующий код состоит из неуправляемый и управляемый модуль. Неуправляемый модуль — это библиотека DLL, которая определяет функцию TakesCallback, принимающую указатель на функцию. Этот адрес используется для выполнения функции.  
  
 Управляемый модуль определяет делегат, который маршалируется в машинный код как указатель на функцию и использует <xref:System.Runtime.InteropServices.DllImportAttribute> атрибут для предоставления собственной функции TakesCallback управляемому коду. В функцию main создается и передается функции TakesCallback экземпляр делегата. Выходные данные программы показывает, что эта функция выполняется с собственной функции TakesCallback.  
  
 Управляемая функция подавляет сбора мусора для управляемого делегата, чтобы помешать сбору мусора .NET Framework перемещению делегата во время выполнения собственной функции.  
  
```cpp  
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
  
```cpp  
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
  
 Обратите внимание, что никакие компоненты библиотеки DLL не предоставляются для управляемого кода, с помощью стандартной #include. На самом деле DLL осуществляется во время выполнения, поэтому проблемы с функциями импортированы с <xref:System.Runtime.InteropServices.DllImportAttribute> во время компиляции не обнаруживаются.  
  
## <a name="see-also"></a>См. также  
 [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)