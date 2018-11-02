---
title: Некритичная ошибка ML A2133
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: 9e13dd48c77b9574229023e3cfc4cc2f2221d153
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586947"
---
# <a name="ml-nonfatal-error-a2133"></a>Некритичная ошибка ML A2133

**значение, перезаписываются INVOKE регистра**

Регистр был передан в качестве аргумента в процедуру, но код, созданный путем [INVOKE](../../assembler/masm/invoke.md) передавать другие аргументы уничтожения содержимое регистра.

Регистры AX, AL, AH, EAX, DX, список Рассылки, Диффи-Хелмана и EDX может использоваться ассемблер, для выполнения преобразования данных.

Используйте другой регистр.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>