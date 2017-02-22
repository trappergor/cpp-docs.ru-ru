---
title: "Ошибка компилятора C3168 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3168"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3168"
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3168
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": недопустимый основной тип для перечисления  
  
 Основной тип, указанный для типа `enum`, не является допустимым.  Основной тип должен являться целым типом C\+\+ или соответствующим типом CLR.  
  
 Следующий пример приводит к возникновению ошибки C3168:  
  
```  
// C3168.cpp  
// compile with: /clr /c  
ref class G{};  
  
enum class E : G { e };   // C3168  
enum class F { f };   // OK  
```  
  
 Следующий пример приводит к возникновению ошибки C3168:  
  
```  
// C3168_2.cpp  
// compile with: /clr:oldSyntax /c  
__gc class G {};  
  
__value enum E : G {e};   // C3168  
__value enum F {f};   // OK  
```