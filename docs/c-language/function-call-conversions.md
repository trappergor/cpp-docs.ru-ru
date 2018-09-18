---
title: Преобразования вызова функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3a1a245511f0ab849c28ab9a03ba76903609643
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065664"
---
# <a name="function-call-conversions"></a>Преобразования вызова функции

Тип преобразования, выполняемого над аргументами в вызове функции, зависит от того, имеется ли для вызываемой функции прототип функции (предварительное объявление) с объявленными типами аргументов.

Если существует прототип функции и в нем объявлены типы аргументов, то компилятор выполняет проверку типа (см. статью [Функции](../c-language/functions-c.md)).

Если прототипа нет, то над аргументами в вызове функции выполняются только обычные арифметические преобразования. Для каждого аргумента в вызове они выполняются отдельно. Иными словами, значение **float** преобразуется в **double**, значение `char` или **short** — в `int`, а значение `unsigned char` или **unsigned short** преобразуется в `unsigned int`.

## <a name="see-also"></a>См. также

[Преобразования типов](../c-language/type-conversions-c.md)