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
ms.openlocfilehash: c9acc9b9872e096cd441b950632c341e975fecb8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034339"
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