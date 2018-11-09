---
title: Преобразования вызова функции
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
ms.openlocfilehash: 9fdc9ef467980a079198ca06360766d84a85923f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441149"
---
# <a name="function-call-conversions"></a>Преобразования вызова функции

Тип преобразования, выполняемого над аргументами в вызове функции, зависит от того, имеется ли для вызываемой функции прототип функции (предварительное объявление) с объявленными типами аргументов.

Если существует прототип функции и в нем объявлены типы аргументов, то компилятор выполняет проверку типа (см. статью [Функции](../c-language/functions-c.md)).

Если прототипа нет, то над аргументами в вызове функции выполняются только обычные арифметические преобразования. Для каждого аргумента в вызове они выполняются отдельно. Иными словами, значение **float** преобразуется в **double**, значение `char` или **short** — в `int`, а значение `unsigned char` или **unsigned short** преобразуется в `unsigned int`.

## <a name="see-also"></a>См. также

[Преобразования типов](../c-language/type-conversions-c.md)