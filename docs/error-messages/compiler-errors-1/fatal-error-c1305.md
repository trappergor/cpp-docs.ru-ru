---
title: "Неустранимая ошибка C1305 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1305"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1305"
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Неустранимая ошибка C1305
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

файл "pgd\_file" базы данных профилей предназначен для другой архитектуры  
  
 PGD\-файл, который был создан из операции \/LTCG:PGINSTRUMENT для другой платформы, был передан [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) .  [Профильные оптимизации](../../build/reference/profile-guided-optimizations.md) доступен для x86 и платформы [!INCLUDE[vcprx64](../Token/vcprx64_md.md)].  Тем не менее PGD\-файл, созданный с помощью операции \/LTCG:PGINSTRUMENT для одной платформы, не является допустимым для ввода в \/LTCG:PGOPTIMIZE для другой платформы.  
  
 Чтобы решить эту ошибку, следует перемещать только PGD\-файл, созданный с помощью \/LTCG:PGINSTRUMENT в \/LTCG:PGOPTIMIZE на одной и той же платформе.