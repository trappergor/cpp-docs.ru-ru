---
title: "Ошибка компилятора C2410 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2410"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2410"
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C2410
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

идентификатор: неоднозначное имя члена в "контекст"  
  
 Идентификатор является членом более чем одной структуры или объединения в этом контексте.  
  
 Используйте структуру или объединенный спецификатор операнда, который вызывает ошибку.  Структура или спецификатор объединения является идентификатором типа `struct` или `union` \(именем `typedef` или переменной того же типа, что и у структуры или объединения, на которые ссылаются\).  Спецификатор должен быть левым операндом первого оператора выбора члена \(.\), чтобы использовать операнд.