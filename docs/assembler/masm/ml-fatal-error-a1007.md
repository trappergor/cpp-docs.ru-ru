---
title: Неустранимая ошибка ML A1007
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: c9527769e0d9397de90f49cbce98b2cca42bed50
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317127"
---
# <a name="ml-fatal-error-a1007"></a>Неустранимая ошибка ML A1007

**уровень вложенности слишком глубокий**

Для ассемблера достигнуто ограничение вложенности. Ограничение составляет 20 уровней, за исключением случаев, где указано иное.

Один из следующих элементов был вложен слишком глубоким:

- Общая директива, например [. Если](dot-if.md), [. Повторите](dot-repeat.md)или [. WHILE](dot-while.md).

- Определение структуры.

- Директива условной сборки.

- Определение процедуры.

- Директива [пушконтекст](pushcontext.md) (ограничение — 10).

- Определение сегмента.

- Включаемый файл.

- Макрос.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](ml-error-messages.md)
