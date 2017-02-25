---
title: "Практическое руководство. Определение выходного параметра | Microsoft Docs"
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
  - "параметры функции"
  - "параметры вывода"
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Практическое руководство. Определение выходного параметра
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом примере описывается порядок определения выходного параметра функции и вызова такой функции в программе C\#.  
  
 В Visual C\+\+ выходной параметр определяется с помощью атрибута <xref:System.Runtime.InteropServices.OutAttribute>.  
  
## Пример  
 В первой части примера представлена библиотека DLL Visual C\+\+, в которой определяется тип, содержащий функцию с выходным параметром.  
  
```  
// cpp_out_param.cpp  
// compile with: /LD /clr:safe  
using namespace System;  
public value struct TestStruct {  
   static void Test([Runtime::InteropServices::Out] String^ %s) {  
      s = "a string";  
   }  
};  
```  
  
## Пример  
 Здесь описывается клиент C\#, использующий компонент Visual C\+\+, созданный в предыдущем примере.  
  
```  
// cpp_out_param_2.cs  
// compile with: /reference:cpp_out_param.dll  
using System;  
class TestClass {  
   public static void Main() {  
      String t;  
      TestStruct.Test(out t);  
      System.Console.WriteLine(t);  
   }  
}  
```  
  
  **строка**   
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)