---
title: "Ошибка компилятора C3625 | Microsoft Docs"
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
  - "C3625"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3625"
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3625
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

native\_type: неуправляемый тип не может быть производным от типа WinRT type  
  
 Неуправляемый класс не может наследовать от управляемого класса или класса WinRT.  Подробнее см. в разделе [Классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3625:  
  
```  
// C3625.cpp  
// compile with: /clr /c  
ref class B {};  
class D : public B {};   // C3625 cannot inherit from a managed class  
```  
  
 Следующий пример приводит к возникновению ошибки C3625:  
  
```  
// C3625_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class B {};  
class D : public B {};   // C3625  cannot inherit from a managed class  
```