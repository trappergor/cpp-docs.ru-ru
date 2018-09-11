---
title: Неустранимая ошибка ML A1007 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1007
dev_langs:
- C++
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 539ab431510d5dc721e6531c11069a87e27c287a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693605"
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