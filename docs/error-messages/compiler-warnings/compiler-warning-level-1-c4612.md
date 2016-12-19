---
title: "Предупреждение компилятора (уровень 1) C4612 | Microsoft Docs"
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
  - "C4612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4612"
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ошибка в имени включаемого файла  
  
 Это предупреждение возникает с **\#pragma include\_alias**, когда имя файла указано неправильно или отсутствует.  
  
 Аргументы для оператора **\#pragma include\_alias** могут использовать форму с кавычками \(**"***имя\_файла***"**\) или форму с угловыми скобками \(**\<***имя\_файла***\>**\), но оба аргументы должны использовать одну и ту же форму.  
  
## Пример  
  
```  
// C4612.cpp // compile with: /W1 /LD #pragma include_alias("StandardIO", <stdio.h>) // C4612  
```