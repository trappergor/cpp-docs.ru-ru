---
title: Неустранимая ошибка ML A1010
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: eb4d77b856e93a8d64ee6c51bec63ceae59b22e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62202069"
---
# <a name="ml-fatal-error-a1010"></a>Неустранимая ошибка ML A1010

**вложенность непарные блок:**

Начало блока не имеет сопоставления конечных или конца блока не имеет сопоставления начало. Может быть задействован один из следующих:

- Директиву высокого уровня, такие как [. Если](../../assembler/masm/dot-if.md), [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md), или [. ХОТЯ](../../assembler/masm/dot-while.md).

- Директива условной сборки как [IF](../../assembler/masm/if-masm.md), [ПОВТОРИТЕ](../../assembler/masm/repeat.md), или **ХОТЯ**.

- Определение структуры или объединения.

- Определение процедуры.

- Определение сегмента.

- Объект [POPCONTEXT](../../assembler/masm/popcontext.md) директива.

- Сборкой условной директивы, такие как [ELSE](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md), или **ENDIF** без соответствующего [IF](../../assembler/masm/if-masm.md).

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>