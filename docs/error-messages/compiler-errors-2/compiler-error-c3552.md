---
title: "Ошибка компилятора C3552 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3552"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3552"
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Ошибка компилятора C3552
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имя\_типа": тип возвращаемого значения с поздним заданием не может содержать "auto"  
  
 Если вы используете ключевое слово `auto` для типа возвращаемого значения функции, необходимо использовать тип возвращаемого значения с поздним заданием. Однако нельзя использовать другое ключевое слово `auto` для указания типа возвращаемого значения с поздним заданием. Например, представленный ниже фрагмент кода приводит к возникновению ошибки C3552.  
  
 `auto myFunction->auto; // C3552`