---
title: "Предупреждение компилятора (уровень 1) C4076 | Microsoft Docs"
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
  - "C4076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4076"
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4076
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"модификатор\_типа": не может использоваться с типом "имя\_типа"  
  
 Модификатор типа, будь он **signed** или `unsigned`, не может использоваться с нецелочисленным типом.***модификатор\_типа*** игнорируется.  
  
## Пример  
 При компиляции следующего примера будет выдано предупреждение C4076:  
  
```  
// C4076.cpp // compile with: /W1 /LD unsigned double x;   // C4076  
```