---
title: "Предупреждение компилятора (уровни 2 и 3) C4008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4008"
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровни 2 и 3) C4008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": атрибут "атрибут" игнорируется  
  
 Компилятор игнорировал атрибут `__fastcall`, **static** или **inline** для функции \(предупреждение уровня 3\) или данных \(предупреждение уровня 2\).  
  
### Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Атрибут `__fastcall` с данными.  
  
2.  Атрибут **static** или **inline** с функцией **main**.