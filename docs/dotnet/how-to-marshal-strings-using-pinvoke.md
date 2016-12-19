---
title: "Практическое руководство. Маршалирование строк с помощью PInvoke | Microsoft Docs"
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
  - "маршалинг данных [C++], строки"
  - "взаимодействие [C++], строки"
  - "маршалинг [C++], строки"
  - "вызов неуправляемого кода [C++], строки"
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Маршалирование строк с помощью PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе описывается, как можно вызывать неуправляемые функции, принимающие строки, характерные для языка C, с помощью строкового типа среды CLR System::String, используя поддержку вызова неуправляемого кода платформы .NET Framework.  Программистам Visual C\+\+ рекомендуется использовать возможности взаимодействия C\+\+ \(когда это возможно\), так как вызов P\/Invoke предоставляет мало сведений об ошибках во время компиляции, не является типобезопасным и сложен в реализации.  Если неуправляемый интерфейс API упакован в виде библиотеки DLL, а исходный код недоступен, то использование P\/Invoke является единственным возможным вариантом, в противном случае см. раздел [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Управляемые и неуправляемые строки по\-разному хранятся в памяти, поэтому для передачи строк из управляемых функций в неуправляемые требуется атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute>, чтобы компилятор вставлял необходимые механизмы преобразования для безопасного и корректного маршалинга строковых данных.  
  
 Как и в случае функций, использующих только встроенные типы данных, атрибут <xref:System.Runtime.InteropServices.DllImportAttribute> используется для объявления управляемых точек входа в неуправляемые функции, но для передачи строк вместо объявления этих точек входа, принимающих строки, характерные для языка C, можно использовать дескриптор типа <xref:System.String>.  В этом случае компилятор вставляет код, выполняющий соответствующие преобразования.  Для каждого аргумента неуправляемой функции, принимающей строку, атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> следует использовать для обозначения того, что объект String необходимо маршалировать в неуправляемую функцию в виде строки, характерной для языка C.  
  
## Пример  
 Следующий код состоит из неуправляемого и управляемого модулей.  Неуправляемый модуль — это библиотека DLL, в которой определена функция TakesAString, принимающая строку ANSI, характерную для языка C, в форме типа char\*.  Управляемый модуль — это приложение командной строки, импортирующее функцию TakesAString, однако здесь эта функция определена как принимающая объект типа System.String, а не char\*.  Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> используется для обозначения того, как управляемую строку следует маршалировать при вызове функции TakesAString.  
  
 Управляемый модуль компилируется с параметром \/clr, также возможна компиляция с \/clr:pure.  
  
```  
// TraditionalDll2.cpp  
// compile with: /LD /EHsc  
#include <windows.h>  
#include <stdio.h>  
#include <iostream>  
  
using namespace std;  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAString(char*);  
}  
  
void TakesAString(char* p) {  
   printf_s("[unmanaged] %s\n", p);  
}  
```  
  
```  
// MarshalString.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL  
{  
   [DllImport("TraditionalDLL2.dll")]  
      static public void   
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);  
};  
  
int main() {  
   String^ s = gcnew String("sample string");  
    Console::WriteLine("[managed] passing managed string to unmanaged function...");  
   TraditionalDLL::TakesAString(s);  
   Console::WriteLine("[managed] {0}", s);  
}  
```  
  
 При этом в неуправляемой куче создается копия строки, поэтому изменения строки, выполненный неуправляемой функцией, не отражаются в управляемой копии строки.  
  
 Обратите внимание, что DLL недоступна управляемому код через директиву \#include.  Обращение к DLL идет только во время выполнения, поэтому проблемы с функциями, импортируемыми с помощью `DllImport`, во время компиляции не обнаруживаются.  
  
## См. также  
 [Использование явного вызова Pinvoke в C\+\+ \(атрибут DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)