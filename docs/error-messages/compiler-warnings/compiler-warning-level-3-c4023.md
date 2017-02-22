---
title: "Предупреждение компилятора (уровень 3) C4023 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4023"
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 3) C4023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ": относительный указатель передан в функцию без прототипа: номер параметра  
  
 Передача относительного указателя в функцию без прототипа нормализует указатель с непредвиденными результатами.  
  
 Чтобы устранить это предупреждение, используйте функции прототипа, которые передаются относительными указателями.