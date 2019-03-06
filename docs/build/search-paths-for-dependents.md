---
title: Пути поиска для зависимых элементов
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
ms.openlocfilehash: 9f2251a5fff9d708a783797d04606572e5ebce62
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426463"
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
