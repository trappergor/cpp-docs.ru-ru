---
title: Битовые операции со знаком
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: 43f65fd5d1ea14ef5e15f18d9c8516ccf5fb1e08
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147598"
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
