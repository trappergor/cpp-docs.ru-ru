---
title: Оператор преобразования в символы (#@)
ms.date: 08/29/2019
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: cb2a4e07287edf5ed2d0850ec7d870c8ef307879
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218536"
---
# <a name="charizing-operator-"></a>Оператор преобразования в символы (#@)

**Блок, относящийся только к системам Microsoft**

Оператор образования символа может использоваться только в аргументах макросов. Если `#@` перед формальным параметром в определении макроса, фактический аргумент заключается в одинарные кавычки и обрабатывается как символ при расширении макроса. Например:

```cpp
#define makechar(x)  #@x
```

приводит к разворачиванию оператора

```cpp
a = makechar(b);
```

в выражение

```cpp
a = 'b';
```

Символ одинарной кавычки (`'`) нельзя использовать с оператором преобразования.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Операторы препроцессора](../preprocessor/preprocessor-operators.md)
