---
title: Выделение обнуленной памяти
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: c7d5f307a38fff938c94cf2e1660cec99262a10a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447311"
---
# <a name="allocating-zero-memory"></a>Выделение обнуленной памяти

**ANSI 4.10.3** Поведение функции `calloc`, `malloc` или `realloc`, если запрошенный размер равен нулю

Функции `calloc`, `malloc` и `realloc` принимают в качестве аргумента нуль. Фактическая память не распределяется, однако возвращается допустимый указатель, и блок памяти можно изменить впоследствии путем перераспределения.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)