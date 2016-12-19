---
title: "STACKSIZE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "STACKSIZE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STACKSIZE - оператор DEF-файла"
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# STACKSIZE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает размер стека \(в байтах\).  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## Заметки  
 Также можно задать стек с помощью [Выделение стека](../../build/reference/stack-stack-allocations.md) \(\/STACK\).  Подробные сведения об аргументах *reserve* и `commit` см. в описании параметра.  
  
 Данный параметр не влияет на библиотеки DLL.  
  
## См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)