---
title: Неустранимая ошибка ML A1010
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: b3141f8819a33281c70e34bd7772d4475886e557
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75312590"
---
# <a name="ml-fatal-error-a1010"></a>Неустранимая ошибка ML A1010

**непарное вложение блоков:**

Начало блока не имеет соответствующего конца, или у конца блока нет соответствующего начала. Может потребоваться одна из следующих факторов.

- Общая директива, например [. Если](dot-if.md), [. Повторите](dot-repeat.md)или [. WHILE](dot-while.md).

- Директива условной сборки, например [If](if-masm.md), [Repeat](repeat.md)или **while**.

- Определение структуры или объединения.

- Определение процедуры.

- Определение сегмента.

- Директива [попконтекст](popcontext.md) .

- Директива условной сборки, например [else](else-masm.md), [ELSEIF](elseif-masm.md)или **endif** без соответствующего [If](if-masm.md).

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](ml-error-messages.md)
