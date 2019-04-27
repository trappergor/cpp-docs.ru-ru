---
title: Неустранимая ошибка ML A1007
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: 98933c3a24da22f447174a3b51c4855690aba83e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62177907"
---
# <a name="ml-fatal-error-a1007"></a>Неустранимая ошибка ML A1007

**слишком глубокий уровень вложенности**

Ассемблер достигнут предел вложенности. Это значение равно 20 уровни, за исключением оговоренных.

Одно из следующих были вложены слишком глубоко:

- Директиву высокого уровня, такие как [. Если](../../assembler/masm/dot-if.md), [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md), или [. ХОТЯ](../../assembler/masm/dot-while.md).

- Определение структуры.

- Директива условной сборки.

- Определение процедуры.

- Объект [PUSHCONTEXT](../../assembler/masm/pushcontext.md) директива (предел — 10).

- Определение сегмента.

- Включаемый файл.

- Макрос.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>