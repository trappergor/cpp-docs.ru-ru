---
title: Оператор преобразования в символы (#@)
ms.date: 11/04/2016
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: 7259487a3289173bc77517c8c616638c370041c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568350"
---
# <a name="charizing-operator-"></a>Оператор преобразования в символы (#@)
**Блок, относящийся только к системам Microsoft**

Оператор образования символа может использоваться только в аргументах макросов. Если `#@` стоит перед формальным параметром в определении макроса, фактический аргумент заключены в одинарные кавычки и рассматривается как символ, при разворачивании макроса. Пример:

```
#define makechar(x)  #@x
```

приводит к разворачиванию оператора

```
a = makechar(b);
```

в выражение

```
a = 'b';
```

В операторе образования символа не допускается использовать одинарные кавычки.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Операторы препроцессора](../preprocessor/preprocessor-operators.md)