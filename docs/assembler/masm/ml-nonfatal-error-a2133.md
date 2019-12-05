---
title: Некритичная ошибка ML A2133
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: c2d13aefe02543129340bcc307771a1026776d61
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854619"
---
# <a name="ml-nonfatal-error-a2133"></a>Некритичная ошибка ML A2133

**значение регистра, Перезаписанное функцией INVOKE**

Регистр был передан в процедуру в качестве аргумента, но код, созданный функцией [Invoke](../../assembler/masm/invoke.md) для передачи других аргументов, привел к удалению содержимого регистра.

Для преобразования данных ассемблером можно использовать регистры AX, AL, AH, EAX, DX, DL, DH и EDX.

Используйте другой регистр.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>