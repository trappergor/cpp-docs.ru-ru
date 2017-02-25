---
title: "Практическое руководство. Маршалинг массивов с помощью службы PInvoke | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "маршалинг данных [C++], массивы"
  - "взаимодействие [C++], массивы"
  - "маршалинг [C++], массивы"
  - "вызов неуправляемого кода [C++], массивы"
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Практическое руководство. Маршалинг массивов с помощью службы PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В данном разделе объясняется, как машинные функции, которые принимают строки в стиле языка С, могут вызываться с помощью строкового типа среды CLR <xref:System.String>, с помощью поддержки службы P\/Invoke .NET Framework.  Программистам Visual C\+\+ рекомендуется использовать возможности взаимодействия C\+\+ \(когда это возможно\), так как вызов P\/Invoke предоставляет мало сведений об ошибках во время компиляции, не является типобезопасным и сложен в реализации.  Если неуправляемый API упакован как библиотека DLL и исходный код не доступен, служба P\/Invoke является единственной доступной возможностью \(в противном случае см. раздел [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)\).  
  
## Пример  
 Т. к. машинные и управляемые массивы по\-разному расположены в памяти, успешная передача их через границу управляемого или неуправляемого кода требует соглашения или маршалинга.  В данном разделе показано, как можно передать массив простых \(не преобразуемых\) элементов от управляемого кода машинным функциям.  
  
 Как и в общем случае маршалинга управляемых и неуправляемых данных, атрибуты класса <xref:System.Runtime.InteropServices.DllImportAttribute> используются для создания управляемой точки входа для каждой машинной функции, которая будет использоваться.  В отношении функций, которые принимают массивы в качестве аргументов, атрибуты класса <xref:System.Runtime.InteropServices.MarshalAsAttribute> должны использоваться также для указания компилятору способа маршалинга данных.  В следующем примере перечисление <xref:System.Runtime.InteropServices.UnmanagedType> используется для указания того, что управляемые массивы будут маршалированы как массивы в стиле С.  
  
 В следующем примере кода представлены неуправляемый и управляемый модули.  Неуправляемый модуль — это библиотека DLL, которая определяет функцию, принимающую массив целых чисел.  Второй модуль является управляемым приложением командной строки, которое импортирует данную функцию, но определяет ее в терминах управляемого массива, и использует атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> для указания того, что массив должен быть конвертирован в машинный массив при вызове.  
  
 Управляемый модуль компилируется с параметром \/clr, также возможна компиляция с \/clr:pure.  
  
```  
// TraditionalDll4.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);  
}  
  
void TakesAnArray(int len, int a[]) {  
   printf_s("[unmanaged]\n");  
   for (int i=0; i<len; i++)  
      printf("%d = %d\n", i, a[i]);  
}  
```  
  
```  
// MarshalBlitArray.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL4.dll")]  
   static public void TakesAnArray(  
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);  
};  
  
int main() {  
   array<int>^ b = gcnew array<int>(3);  
   b[0] = 11;  
   b[1] = 33;  
   b[2] = 55;  
   TraditionalDLL::TakesAnArray(3, b);  
  
   Console::WriteLine("[managed]");  
   for (int i=0; i<3; i++)  
      Console::WriteLine("{0} = {1}", i, b[i]);  
}  
```  
  
 Обратите внимание, что в управляемом коде никакие компоненты библиотеки DLL не предоставляются с помощью стандартной директивы \#include.  Фактически доступ к библиотеке DLL происходит только во время выполнения, поэтому проблем с функциями, импортируемыми с помощью <xref:System.Runtime.InteropServices.DllImportAttribute> во время компиляции не обнаруживаются.  
  
## См. также  
 [Использование явного вызова Pinvoke в C\+\+ \(атрибут DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)