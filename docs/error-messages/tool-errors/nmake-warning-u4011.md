---
title: "Предупреждение программы NMAKE U4011 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U4011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4011"
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение программы NMAKE U4011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'target' : доступны не все зависимые сборки; построение цели не выполнено  
  
 Зависимая сборка данной цели не существует или устарела, а после выполнения команды обновления возвращен не нулевой код завершения.  Параметр \/K дал указание NMAKE продолжать обработку несвязанных частей построения и вывести код выхода 1 при окончании сеанса NMAKE.  
  
 Этому предупреждению предшествует предупреждение [U4010](../Topic/NMAKE%20Warning%20U4010.md) для каждой зависимости, которую не удалось создать или обновить.