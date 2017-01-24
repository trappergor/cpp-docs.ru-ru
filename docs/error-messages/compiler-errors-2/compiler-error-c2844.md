---
title: "Ошибка компилятора C2844 | Microsoft Docs"
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
  - "C2844"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2844"
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2844
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член" : не может быть членом интерфейса "интерфейс"  
  
 [interface class](../../windows/interface-class-cpp-component-extensions.md) не может содержать элемент данных, если он не является также и свойством.  
  
 В интерфейсе не допускается наличие чего\-либо кроме свойства или функции\-члена.  Более того, недопустимы также конструкторы, деструкторы и операторы.  
  
 Следующий пример приводит к возникновению ошибки C2844:  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  
  
 Следующий пример приводит к возникновению ошибки C2844:  
  
```  
// C2844b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
__gc __interface IFace {  
   int i;   // C2844  
   // try the following line instead  
   // __property int Size { get; set; };  
};  
```