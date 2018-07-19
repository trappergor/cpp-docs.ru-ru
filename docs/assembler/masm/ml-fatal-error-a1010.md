---
title: Неустранимая ошибка ML A1010 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1010
dev_langs:
- C++
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b622595b6994c4c4eaa74ed8f824f28dffe89b1a
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057686"
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