---
title: Пути поиска для зависимых элементов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1fd407f99abb98fb949b6d5bcc45b10c6ff9121
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706315"
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