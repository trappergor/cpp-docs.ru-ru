---
title: "Ошибка компилятора C3385 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3385"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3385"
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3385
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс::функция": функция с пользовательским аргументом DllImport не может возвращать экземпляр класса  
  
 Функция, определенная как находящаяся в DLL\-файле, указанная с атрибутом `DllImport`, не может возвращать экземпляр класса.  
  
 В следующем примере возникает ошибка C3385:  
  
```  
// C3385.cpp // compile with: /clr /c using namespace System; using namespace System::Runtime::InteropServices; struct SomeStruct1 {}; public ref struct Wrap { [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ] static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385 };  
```  
  
 В следующем примере возникает ошибка C3385:  
  
```  
// C3385_2.cpp // compile with: /clr:oldSyntax /c using namespace System; using namespace System::Runtime::InteropServices; struct SomeStruct1 {}; public __gc struct Wrap { [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ] static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385 };  
```