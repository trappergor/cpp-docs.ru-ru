---
title: "Предупреждение средств компоновщика LNK4010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4010"
ms.assetid: 2824cf99-4174-4b60-a6e2-c01e9f1ee52d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение средств компоновщика LNK4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимый номер версии подсистемы "номер"; принята версия подсистемы по умолчанию  
  
 Можно задать используемую образом версию подсистемы \(параметр [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)\).  К версии каждой подсистемы предъявляются определенные минимальные требования.  Если указанный номер версии меньше минимальной, то появится это предупреждение, и компоновщик будет использовать подсистему по умолчанию.