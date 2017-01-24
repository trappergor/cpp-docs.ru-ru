---
title: "Ошибка компилятора C3531 | Microsoft Docs"
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
  - "C3531"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3531"
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3531
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ": символ, тип которого содержит "auto", должен иметь инициализатор  
  
 Указанная переменная не имеет выражения инициализатора.  
  
### Исправление этой ошибки  
  
1.  При объявлении переменной укажите выражение инициализатора, например простое присвоение, использующее синтаксис со знаком равенства.  
  
## Пример  
 Следующий пример вызывает ошибку C3531, поскольку переменные `x1`, `y1, y2, y3` и `z2` не инициализированы.  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)