---
title: "EXTERNDEF | Microsoft Docs"
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
  - "EXTERNDEF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXTERNDEF directive"
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EXTERNDEF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает один или более внешние переменные, метки или вызываемых символы Имя чей тип `type`.  
  
## Синтаксис  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## Заметки  
 If Имя определяет, рассматривается как в модуле [ОТКРЫТЫЙ](../Topic/PUBLIC%20\(MASM\).md).  If Имя ссылающийся на модуль, в нем рассматривается как EXTERN.  If *Имя* не ссылается на он пропускается.  `type` может быть  [ABS](../../assembler/masm/operator-abs.md), который будет импортировать Имя в качестве константы.  Обычно используется внутри включаемых файлов.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)