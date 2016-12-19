---
title: "Предупреждение компилятора (уровень 1) C4182 | Microsoft Docs"
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
  - "C4182"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4182"
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4182
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Глубина вложения директивы \#include составляет "число"; возможна бесконечная рекурсия  
  
 Компилятору недостаточно места в куче из\-за количества вложенных файлов include. Файл include является вложенным, когда он включается из другого файла include.  
  
 Это сообщение является информационным и предшествует ошибке [C1076](../Topic/Fatal%20Error%20C1076.md).