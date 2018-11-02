---
title: Пути поиска для зависимых элементов
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
ms.openlocfilehash: 8856d845d51072d205c84278978c7fbb447aed9b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448806"
---
# <a name="search-paths-for-dependents"></a>Пути поиска для зависимых элементов

Каждый зависимый элемент имеет дополнительный путь поиска, указан следующим образом:

## <a name="syntax"></a>Синтаксис

```
{directory[;directory...]}dependent
```

## <a name="remarks"></a>Примечания

NMAKE ищет зависимые сначала в текущем каталоге, а затем в каталогах в указанном порядке. Макрос можно указать всех или части пути поиска. Заключите имя каталога в фигурные скобки ({}); несколько каталогов разделяются точкой с запятой (;). Разрешены не пробелы или символы табуляции.

## <a name="see-also"></a>См. также

[Зависимые элементы](../build/dependents.md)