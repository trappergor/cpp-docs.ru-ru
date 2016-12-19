---
title: "Предупреждение компилятора (уровень&#160;2) C4396 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4396"
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;2) C4396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имя": если дружественное объявление ссылается на специализацию функции\-шаблона, встроенный спецификатор использовать невозможно  
  
 В специализации шаблона функции нельзя указывать спецификаторы [inline](../../misc/inline-inline-forceinline.md). В этом случае при компиляции возникает предупреждение C4396, а спецификатор inline пропускается.  
  
### Исправление ошибки  
  
-   Удалите спецификатор `inline`, `__inline` или `__forceinline` из объявления дружественной функции.  
  
## Пример  
 В приведенном ниже примере показано недопустимое объявление дружественной функции со спецификатором `inline`.  
  
```  
// C4396.cpp // compile with: /W2 /c class X; template<class T> void Func(T t, int i); class X { friend inline void Func<char>(char t, int i);  //C4396 // try the following line instead //    friend void Func<char>(char t, int i); int i; };  
```