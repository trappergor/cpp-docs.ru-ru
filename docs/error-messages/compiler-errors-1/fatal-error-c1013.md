---
title: "Неустранимая ошибка C1013 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1013"
ms.assetid: 5514a679-efe7-4055-bdd3-5693ca0c332f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка C1013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ограничение компилятора: слишком много открывающих круглых скобок  
  
 Выражение содержит слишком много уровней круглых скобок в одном выражении. Упростите выражение или разбейте его на несколько инструкций.  
  
 До Visual C\+\+ 6.0 с пакетом обновления 3 в одном выражении могло быть не более 59 вложенных круглых скобок. В настоящее время ограничение на количество круглых скобок увеличено до 256.