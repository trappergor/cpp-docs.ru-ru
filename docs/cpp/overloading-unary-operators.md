---
title: Перегрузка унарных операторов
ms.date: 11/04/2016
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
ms.openlocfilehash: 971ef08c5e79f851c502ea872c541517065797c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372031"
---
# <a name="overloading-unary-operators"></a>Перегрузка унарных операторов

Перегрузке могут быть подвергнуты следующие унарные операторы.

1. `!`(логично[НЕ)](../cpp/logical-negation-operator-exclpt.md)

1. `&`[(адрес))](../cpp/address-of-operator-amp.md)

1. `~`(свое[дополнение)](../cpp/one-s-complement-operator-tilde.md)

1. `*`[(указатель dereference](../cpp/indirection-operator-star.md))

1. `+`[(неари плюс)](../cpp/additive-operators-plus-and.md)

1. `-`[(Неарфляек отрицание)](../cpp/additive-operators-plus-and.md)

1. `++`[(приращение)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

1. `--`([decrement](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. операторы преобразования

Постфикс приращения и`++` decrement операторов (и `--`) рассматриваются отдельно при [приращении и decrement](../cpp/increment-and-decrement-operator-overloading-cpp.md).

Операторы конверсии также обсуждаются в отдельной теме; см. [Конверсии типа, определяемые пользователем.](../cpp/user-defined-type-conversions-cpp.md)

Следующие правила распространяются на все остальные унарные операторы. Чтобы объявить функцию унарного оператора как нестатический член, необходимо объявить ее в форме

> *оператор рет-типа* **operator** *()* **()**

где *рет-тип* является типом возврата, а *op* является одним из операторов, перечисленных в предыдущей таблице.

Чтобы объявить функцию унарного оператора как глобальную функцию, необходимо объявить ее в форме

> *оператор рет-типа* **operator** *op* **(arg** *arg* **)**

где *ret-тип* и *op* как описаны для функций оператора члена и *arg* аргумент типа типа типа на котором работать.

> [!NOTE]
> Не существует ограничения на типы возвращаемого значения унарных операторов. Например, логическому НЕ (`!`) имеет смысл возвращать целочисленное значение, однако это не реализовано принудительно.

## <a name="see-also"></a>См. также раздел

[Перегрузка оператора](../cpp/operator-overloading.md)
