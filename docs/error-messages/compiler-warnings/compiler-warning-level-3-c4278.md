---
title: "Предупреждение компилятора (уровень 3) C4278 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4278"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4278"
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 3) C4278
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": идентификатор в библиотеке типов "TLB" уже является макроопределением; следует использовать квалификатор "rename"  
  
 При использовании директивы [\#import](../Topic/%23import%20Directive%20\(C++\).md) идентификатор в импортируемой библиотеке типов пытается объявить идентификатор ***идентификатор***.  Однако этот символ уже является допустимым.  
  
 Следует использовать атрибут `#import` **rename**, чтобы назначить псевдоним для символа в библиотеке типа.