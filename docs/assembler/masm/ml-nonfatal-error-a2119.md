---
title: "ML Nonfatal Error A2119 | Microsoft Docs"
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
  - "A2119"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2119"
ms.assetid: 4d4ee6da-3a58-495c-a1da-c3a405c4c18d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2119
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**необходимо указать тип языка**  
  
 Данный прототип процедуры не определению или тип языка.  
  
 Тип языка необходимо объявить в каждом определении или прототипе процедуры, если тип языка по умолчанию не определен.  Тип языка по умолчанию задается с помощью то [.MODEL](../../assembler/masm/dot-model.md) директива,  **ПАРАМЕТР LANG**ML или параметры командной строки  **\/Gc** OR  **\/Gd**.  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)