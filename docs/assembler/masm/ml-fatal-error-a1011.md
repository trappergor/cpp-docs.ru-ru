---
title: Неустранимая ошибка ML A1011
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 5607d6d56e0b3889332dcf2624d519529819b1c9
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318086"
---
# <a name="ml-fatal-error-a1011"></a>Неустранимая ошибка ML A1011

**Директива должна находиться в блоке управления**

Ассемблер обнаружил директиву высокого уровня, где она не ожидалась. Обнаружена одна из следующих директив:

- [. ELSE](dot-else.md) без [. Если](dot-if.md)

- [. ENDIF](dot-endif.md) без [. Если](dot-if.md)

- [. ЕНДВ](dot-endw.md) без [. Во время выполнения](dot-while.md)

- [. УНТИЛККСЗ](dot-untilcxz.md) без [. ПОВТОРИТЬ](dot-repeat.md)

- [. ПРОДОЛЖИТЬ](dot-continue.md) без [. WHILE](dot-while.md) или [. ПОВТОРИТЬ](dot-repeat.md)

- [. Прервать](dot-break.md) без [. WHILE](dot-while.md) или [. ПОВТОРИТЬ](dot-repeat.md)

- [. Далее `.ELSE`](dot-else.md)

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](ml-error-messages.md)
