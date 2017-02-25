---
title: "Предупреждение компилятора (уровень&#160;4) C4960 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4960"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4960"
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень&#160;4) C4960
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция" слишком велика для профилирования  
  
 При использовании параметра [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) компилятор обнаружил, что входной модуль содержит более 65 535 инструкций. Профильная оптимизация столь крупных функций невозможна.  
  
 Чтобы устранить это предупреждение, уменьшите размер функции.