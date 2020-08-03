---
title: Преобразования вызова функции
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
ms.openlocfilehash: e4e84c9d4e1f25a56c0bcabcec99e5e75fcaa321
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229679"
---
# <a name="function-call-conversions"></a>Преобразования вызова функции

Тип преобразования, выполняемого над аргументами в вызове функции, зависит от того, имеется ли для вызываемой функции прототип функции (предварительное объявление) с объявленными типами аргументов.

Если существует прототип функции и в нем объявлены типы аргументов, то компилятор выполняет проверку типа (см. статью [Функции](../c-language/functions-c.md)).

Если прототипа нет, то над аргументами в вызове функции выполняются только обычные арифметические преобразования. Для каждого аргумента в вызове они выполняются отдельно. Иными словами, значение типа **`float`** преобразуется в **`double`** ; значение типа **`char`** или **`short`**  — в **`int`** ; а **`unsigned char`** или **`unsigned short`**  — в **`unsigned int`** .

## <a name="see-also"></a>См. также

[Преобразования типов](../c-language/type-conversions-c.md)
