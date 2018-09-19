---
title: 'Унарный плюс "и" отрицание операторы: + и - | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef8cc91f90f92d17ec759c874c7dfd34b4706e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032878"
---
# <a name="unary-plus-and-negation-operators--and--"></a>Унарные операторы «плюс» и «отрицание»: + и -

## <a name="syntax"></a>Синтаксис

```
+ cast-expression
- cast-expression
```

## <a name="-operator"></a>+ - оператор

Результатом унарного оператора сложения (**+**) является значение операнда. Операнд оператора унарного оператора сложения должен иметь арифметический тип.

Над целочисленными операндами выполняется восходящее приведение целого типа. Результирующим типом является тип, до которого повышается уровень операнда. Таким образом, выражение `+ch`, где `ch` имеет тип **char**, в тип **int**; значение не меняется. См. в разделе [стандартные преобразования](standard-conversions.md) Дополнительные сведения о том, как выполняется такое повышение.

## <a name="--operator"></a>- - оператор

Оператор унарного отрицания (**-**) изменяет знак операнда. Операнд оператора унарного отрицания должен быть арифметическим типом.

Над целочисленными операндами выполняется восходящее приведение целого типа, и результирующим типом является тип, до которого повышается уровень операнда. См. в разделе [стандартные преобразования](standard-conversions.md) Дополнительные сведения о том, как выполняется такое повышение.

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Унарное отрицание величин без знака выполняется путем вычитания значения операнда из числа 2^n, где n — количество битов в объекте заданного типа без знака.

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)