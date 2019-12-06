---
title: Неустранимая ошибка ML A1010
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: 6ec82f7f6d559d977a9aa039ed91689a0ef4d49a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856882"
---
# <a name="ml-fatal-error-a1010"></a>Неустранимая ошибка ML A1010

**непарное вложение блоков:**

Начало блока не имеет соответствующего конца, или у конца блока нет соответствующего начала. Может потребоваться одна из следующих факторов.

- Общая директива, например [. Если](../../assembler/masm/dot-if.md), [. Повторите](../../assembler/masm/dot-repeat.md)или [. WHILE](../../assembler/masm/dot-while.md).

- Директива условной сборки, например [If](../../assembler/masm/if-masm.md), [Repeat](../../assembler/masm/repeat.md)или **while**.

- Определение структуры или объединения.

- Определение процедуры.

- Определение сегмента.

- Директива [попконтекст](../../assembler/masm/popcontext.md) .

- Директива условной сборки, например [else](../../assembler/masm/else-masm.md), [ELSEIF](../../assembler/masm/elseif-masm.md)или **endif** без соответствующего [If](../../assembler/masm/if-masm.md).

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>