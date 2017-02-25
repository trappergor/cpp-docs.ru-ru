---
title: "Неустранимая ошибка C1014 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1014"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1014"
ms.assetid: 4c01ef70-e765-4d07-a3fe-a11c19fb610b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка C1014
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком много включаемых файлов: глубина \= уровень  
  
 Вложение директив `#include` является слишком глубоким. Вложенные директивы могут включать открытые файлы. Исходный файл, содержащий директиву, подсчитывается как один из файлов.