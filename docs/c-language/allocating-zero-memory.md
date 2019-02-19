---
title: Выделение обнуленной памяти
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: 40f21c0fa9a2a4068cb2592c49ccefed82176a35
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147468"
---
# <a name="allocating-zero-memory"></a>Выделение обнуленной памяти

**ANSI 4.10.3** Поведение функции `calloc`, `malloc` или `realloc`, если запрошенный размер равен нулю

Функции `calloc`, `malloc` и `realloc` принимают в качестве аргумента нуль. Фактическая память не распределяется, однако возвращается допустимый указатель, и блок памяти можно изменить впоследствии путем перераспределения.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)
