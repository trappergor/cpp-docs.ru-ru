---
title: "Неустранимая ошибка C1305 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1305
dev_langs:
- C++
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b32f9e7555ce905323fd6074d35f1876cd999edd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1305"></a>Неустранимая ошибка C1305
База данных профилей «PGD-файл» — для другой архитектуры  
  
 PGD-файл, который был создан из операции/LTCG: PGINSTRUMENT для другой платформы, передаваемых в [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Профильная оптимизация](../../build/reference/profile-guided-optimizations.md) доступны для x86 и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] платформы. Однако PGD-файл, созданный с помощью операции/LTCG: PGINSTRUMENT для одной платформы, не является допустимым в качестве входного для / LTCG: PGOPTIMIZE для разных платформ.  
  
 Чтобы устранить эту ошибку, передайте только PGD-файл, созданный с/LTCG: PGINSTRUMENT для/LTCG: PGOPTIMIZE на той же платформе.