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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cf4a9025b8d441ae42b7de7605594fda60dc5603
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1305"></a>Неустранимая ошибка C1305
База данных профилей «PGD-файл» — для другой архитектуры  
  
 PGD-файл, который был создан из операции/LTCG: PGINSTRUMENT для другой платформы, передаваемых в [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Профильная оптимизация](../../build/reference/profile-guided-optimizations.md) доступны для x86 и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] платформы. Однако PGD-файл, созданный с помощью операции/LTCG: PGINSTRUMENT для одной платформы, не является допустимым в качестве входного для / LTCG: PGOPTIMIZE для разных платформ.  
  
 Чтобы устранить эту ошибку, передайте только PGD-файл, созданный с/LTCG: PGINSTRUMENT для/LTCG: PGOPTIMIZE на той же платформе.
