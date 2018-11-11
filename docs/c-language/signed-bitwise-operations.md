---
title: Битовые операции со знаком
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: d178900a25a5d7a080068fb1919fcba2853bef14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652014"
---
# <a name="signed-bitwise-operations"></a>Битовые операции со знаком

**ANSI 3.3** Результаты выполнения побитовых операций над знаковыми целочисленными значениями

Побитовые операции над знаковыми целочисленными значениями работают так же, как и над беззнаковыми. Например, значение `-16 & 99` можно представить в двоичном виде следующим образом:

```
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

Результат выполнения побитовой операции И будет равен 96.

## <a name="see-also"></a>См. также

[Целые числа](../c-language/integers.md)