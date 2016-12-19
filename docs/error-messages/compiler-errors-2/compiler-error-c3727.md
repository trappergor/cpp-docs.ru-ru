---
title: "Ошибка компилятора C3727 | Microsoft Docs"
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
  - "C3727"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3727"
ms.assetid: 17b9fe7b-ee9e-483f-9c27-1f709255a9e0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3727
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"event": управляемое событие должно быть функцией\-членом или элементом данных, который является указателем на делегата  
  
 События .NET должны быть указателями на тип делегата.  
  
 Следующий пример приводит к возникновению ошибки C3727:  
  
```  
// C3727.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class PseudoDelegate  
{  
};  
  
// use the following declaration to resolve the error.  
// __delegate void PseudoDelegate(int);  
  
__gc class MyAttr  
{  
   __event PseudoDelegate* MyE;  
};   // C3727  
  
int main()  
{  
}  
```