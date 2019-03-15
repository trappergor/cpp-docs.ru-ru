---
title: Пути поиска для зависимых элементов
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
ms.openlocfilehash: bc2c430c43f408065234c9df50977003eafd3cb1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826703"
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

[Зависимые элементы](dependents.md)
