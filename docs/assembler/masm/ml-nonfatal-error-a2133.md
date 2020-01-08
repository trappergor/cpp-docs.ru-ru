---
title: Некритичная ошибка ML A2133
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: 1ffdf5fb6577dbd4e24312b3c57a4186173ddcf6
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75312642"
---
# <a name="ml-nonfatal-error-a2133"></a>Некритичная ошибка ML A2133

**значение регистра, Перезаписанное функцией INVOKE**

Регистр был передан в процедуру в качестве аргумента, но код, созданный функцией [Invoke](invoke.md) для передачи других аргументов, привел к удалению содержимого регистра.

Для преобразования данных ассемблером можно использовать регистры AX, AL, AH, EAX, DX, DL, DH и EDX.

Используйте другой регистр.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](ml-error-messages.md)
