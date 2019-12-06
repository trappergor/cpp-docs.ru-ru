---
title: Неустранимая ошибка ML A1007
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: 01633b4fa084b7d5e14af5a5c6e51e3dca684d2a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856921"
---
# <a name="ml-fatal-error-a1007"></a>Неустранимая ошибка ML A1007

**уровень вложенности слишком глубокий**

Для ассемблера достигнуто ограничение вложенности. Ограничение составляет 20 уровней, за исключением случаев, где указано иное.

Один из следующих элементов был вложен слишком глубоким:

- Общая директива, например [. Если](../../assembler/masm/dot-if.md), [. Повторите](../../assembler/masm/dot-repeat.md)или [. WHILE](../../assembler/masm/dot-while.md).

- Определение структуры.

- Директива условной сборки.

- Определение процедуры.

- Директива [пушконтекст](../../assembler/masm/pushcontext.md) (ограничение — 10).

- Определение сегмента.

- Включаемый файл.

- Макрос.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>