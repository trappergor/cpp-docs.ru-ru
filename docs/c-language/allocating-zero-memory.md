---
title: Выделение нулевой памяти (C) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc3b7a92cdc8a05c73f15c7cea917d86a3b6bb46
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085060"
---
# <a name="allocating-zero-memory"></a>Выделение обнуленной памяти

**ANSI 4.10.3** Поведение функции `calloc`, `malloc` или `realloc`, если запрошенный размер равен нулю

Функции `calloc`, `malloc` и `realloc` принимают в качестве аргумента нуль. Фактическая память не распределяется, однако возвращается допустимый указатель, и блок памяти можно изменить впоследствии путем перераспределения.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)