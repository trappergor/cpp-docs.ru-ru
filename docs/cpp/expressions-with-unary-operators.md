---
title: Выражения с унарными операторами
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
ms.openlocfilehash: a13b86755a5e309a51a0e2e14faa1157b7e95ea0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183875"
---
# <a name="expressions-with-unary-operators"></a>Выражения с унарными операторами

Унарные операторы действуют только на один операнд в выражении. Ниже приводится список унарных операторов:

- [Оператор косвенного обращения (*)](../cpp/indirection-operator-star.md)

- [Оператор взятия адреса (&)](../cpp/address-of-operator-amp.md)

- [Оператор (+) унарного сложения](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Оператор унарного отрицания (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Оператор логического отрицания (!)](../cpp/logical-negation-operator-exclpt.md)

- [Оператор дополнения (~)](../cpp/one-s-complement-operator-tilde.md)

- [Префиксный оператор инкремента (++)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Оператор префиксного декремента (-)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Оператор CAST)](../cpp/cast-operator-parens.md)

- [оператор sizeof](../cpp/sizeof-operator.md)

- [оператор __uuidof](../cpp/uuidof-operator.md)

- [оператор __alignof](../cpp/alignof-operator.md)

- [оператор New](../cpp/new-operator-cpp.md)

- [оператор delete](../cpp/delete-operator-cpp.md)

Эти операторы имеют ассоциативность справа налево. Обычно синтаксис унарных выражений предшествует синтаксису постфиксных или основных выражений.

Ниже перечислены возможные формы унарных выражений.

- *postfix-expression*

- `++` *Унарное выражение*

- `--` *Унарное выражение*

- *унарный оператор* *выражение приведения*

- **sizeof** *унарное выражение*

- `sizeof(` *Имя типа* `)`

- `decltype(` *Выражение* `)`

- *выражение выделения*

- *освобождение выражение*

Любой *Постфиксное выражение* считается *унарное выражение*, а поскольку любое основное выражение считается *Постфиксное выражение*, — все основные выражения считается *унарное выражение* также. Дополнительные сведения см. в разделе [постфиксные выражения](../cpp/postfix-expressions.md) и [основные выражения](../cpp/primary-expressions.md).

Объект *унарный оператор* состоит из одного или нескольких из следующих символов: `* & + - ! ~`

*Выражение приведения* — это унарное выражение с необязательным приведения, чтобы изменить тип. Дополнительные сведения см. в разделе [оператор Cast: ()](../cpp/cast-operator-parens.md).

*Выражение* может быть любым выражением. Дополнительные сведения см. в разделе [выражения](../cpp/expressions-cpp.md).

*Выражение выделения* ссылается на **новый** оператор. *Освобождение выражение* ссылается на **удалить** оператор. Дополнительные сведения см. по ссылкам, приведенным выше.

## <a name="see-also"></a>См. также

[Типы выражений](../cpp/types-of-expressions.md)