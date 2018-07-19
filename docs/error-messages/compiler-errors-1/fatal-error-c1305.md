---
title: Неустранимая ошибка C1305 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1305
dev_langs:
- C++
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3cb1cf19d0fc4152fbb458d684972bb5a4418f37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227151"
---
# <a name="fatal-error-c1305"></a>Неустранимая ошибка C1305
База данных профилей «PGD-файл» — для другой архитектуры  
  
 PGD-файл, который был создан из операции/LTCG: PGINSTRUMENT для другой платформы, передаваемых в [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Профильная оптимизация](../../build/reference/profile-guided-optimizations.md) доступны для x86 и [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] платформы. Однако PGD-файл, созданный с помощью операции/LTCG: PGINSTRUMENT для одной платформы, не является допустимым в качестве входного для / LTCG: PGOPTIMIZE для разных платформ.  
  
 Чтобы устранить эту ошибку, передайте только PGD-файл, созданный с/LTCG: PGINSTRUMENT для/LTCG: PGOPTIMIZE на той же платформе.