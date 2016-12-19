---
title: "Ошибка компилятора C3624 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3624"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3624"
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3624
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': для использования этого типа необходима ссылка на сборку 'assembly'  
  
 Сборка \(ссылка на нее\), необходимая для компиляции кода, не указана; следует передать сборку с помощью директивы [\#using](../../preprocessor/hash-using-directive-cpp.md).  
  
 Следующий пример приводит к возникновению ошибки C3624:  
  
```  
// C3624.cpp  
// compile with: /clr /c  
#using <System.Windows.Forms.dll>  
  
// Uncomment the following 2 lines to resolve.  
// #using <System.dll>  
// #using <System.Drawing.dll>  
  
using namespace System;  
  
public ref class MyForm : public Windows::Forms::Form {};   // C3624  
```  
  
 Следующий пример приводит к возникновению ошибки C3624:  
  
```  
// C3624_b.cpp  
// compile with: /clr:oldSyntax /c  
#using <System.Windows.Forms.dll>  
  
// Uncomment the following 2 lines to resolve.  
// #using <System.dll>  
// #using <System.Drawing.dll>  
  
using namespace System;  
  
public __gc class MyForm : public Windows::Forms::Form {};   // C3624  
```