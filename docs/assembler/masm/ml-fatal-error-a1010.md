---
title: "Неустранимая ошибка ML A1010 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A1010
dev_langs:
- C++
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 553071ff10688f0b49909b16c8c60d95899247d1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ml-fatal-error-a1010"></a>Неустранимая ошибка ML A1010
**вложенность несовпадающие блока:**  
  
 Начало блока не имеет соответствующего конечного или конца блока не имеет сопоставления начало. Может быть задействован одно из следующих:  
  
-   Директиву высокого уровня, такие как [. Если](../../assembler/masm/dot-if.md), [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md), или [. Во время](../../assembler/masm/dot-while.md).  
  
-   Директива условной сборки как [IF](../../assembler/masm/if-masm.md), [ПОВТОРИТЕ](../../assembler/masm/repeat.md), или **при**.  
  
-   Определение структуры или объединения.  
  
-   Определение процедуры.  
  
-   Определение сегмента.  
  
-   Объект [POPCONTEXT](../../assembler/masm/popcontext.md) директивы.  
  
-   Сборке условной директивы, такие как [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md), или **ENDIF** без соответствующего [IF](../../assembler/masm/if-masm.md).  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)