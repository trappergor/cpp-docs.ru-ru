---
title: Неустранимая ошибка ML A1011
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 591755a1d7066d8251f61d2a22b9601a9ccb9dcb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178570"
---
# <a name="ml-fatal-error-a1011"></a>Неустранимая ошибка ML A1011

**Директива должна быть в блоке управления**

Ассемблер найти директиву высокого уровня, где не ожидалось только одно. Найдена одна из следующих директив:

- [. ELSE](../../assembler/masm/dot-else.md) без [. IF](../../assembler/masm/dot-if.md)

- [. ENDIF](../../assembler/masm/dot-endif.md) без [. IF](../../assembler/masm/dot-if.md)

- [. ENDW](../../assembler/masm/dot-endw.md) без [. WHILE](../../assembler/masm/dot-while.md)

- [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md) без [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md)

- [. По-ПРЕЖНЕМУ](../../assembler/masm/dot-continue.md) без [. ХОТЯ](../../assembler/masm/dot-while.md) или [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md)

- [. ПРЕРВАТЬ](../../assembler/masm/dot-break.md) без [. ХОТЯ](../../assembler/masm/dot-while.md) или [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md)

- [. ELSE](../../assembler/masm/dot-else.md) ниже `.ELSE`

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>