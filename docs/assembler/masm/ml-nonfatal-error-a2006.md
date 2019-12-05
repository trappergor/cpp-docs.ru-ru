---
title: Некритичная ошибка ML A2006
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2006
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
ms.openlocfilehash: 6c55cb66d6eaeaf620aeedc1dd924f6618cbf817
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856787"
---
# <a name="ml-nonfatal-error-a2006"></a>Некритичная ошибка ML A2006

**неопределенный символ: идентификатор**

Предпринята попытка использовать символ, который не был определен.

Возможно, возникла одна из следующих ошибок:

- Символ не был определен.

- Поле не было членом указанной структуры.

- Символ был определен во включаемом файле, который не был включен.

- Внешний символ использовался без директивы [extern](../../assembler/masm/extern-masm.md) или [екстерндеф](../../assembler/masm/externdef.md) .

- Имя символа написано неправильно.

- На метку локального кода имеется ссылка за пределами области.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>