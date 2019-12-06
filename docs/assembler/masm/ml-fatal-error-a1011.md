---
title: Неустранимая ошибка ML A1011
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 0d8d3896f7788aa3f51605651ee1b728b0e1d60a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856856"
---
# <a name="ml-fatal-error-a1011"></a>Неустранимая ошибка ML A1011

**Директива должна находиться в блоке управления**

Ассемблер обнаружил директиву высокого уровня, где она не ожидалась. Обнаружена одна из следующих директив:

- [. ELSE](../../assembler/masm/dot-else.md) без [. Если](../../assembler/masm/dot-if.md)

- [. ENDIF](../../assembler/masm/dot-endif.md) без [. Если](../../assembler/masm/dot-if.md)

- [. ЕНДВ](../../assembler/masm/dot-endw.md) без [. Во время выполнения](../../assembler/masm/dot-while.md)

- [. УНТИЛККСЗ](../../assembler/masm/dot-untilcxz.md) без [. ПОВТОРИТЬ](../../assembler/masm/dot-repeat.md)

- [. ПРОДОЛЖИТЬ](../../assembler/masm/dot-continue.md) без [. WHILE](../../assembler/masm/dot-while.md) или [. ПОВТОРИТЬ](../../assembler/masm/dot-repeat.md)

- [. Прервать](../../assembler/masm/dot-break.md) без [. WHILE](../../assembler/masm/dot-while.md) или [. ПОВТОРИТЬ](../../assembler/masm/dot-repeat.md)

- [. Далее `.ELSE`](../../assembler/masm/dot-else.md)

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>