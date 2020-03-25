---
title: Выражения с унарными операторами
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
ms.openlocfilehash: 26aad64e5b9c7a496c2e6bb131b82740c06abe07
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188978"
---
# <a name="expressions-with-unary-operators"></a>Выражения с унарными операторами

Унарные операторы действуют только на один операнд в выражении. Ниже приводится список унарных операторов:

- [Оператор косвенного обращения (*)](../cpp/indirection-operator-star.md)

- [Оператор взятия адреса (&)](../cpp/address-of-operator-amp.md)

- [Оператор унарного плюса (+)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Унарный оператор отрицания (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Оператор логического отрицания (!)](../cpp/logical-negation-operator-exclpt.md)

- [Оператор дополнения до единицы (~)](../cpp/one-s-complement-operator-tilde.md)

- [Оператор префиксного инкремента (+ +)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Оператор префикса декремента (--)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Оператор CAST ()](../cpp/cast-operator-parens.md)

- [Оператор sizeof](../cpp/sizeof-operator.md)

- [Оператор __uuidof](../cpp/uuidof-operator.md)

- [Оператор __alignof](../cpp/alignof-operator.md)

- [Оператор New](../cpp/new-operator-cpp.md)

- [Delete, оператор](../cpp/delete-operator-cpp.md)

Эти операторы имеют ассоциативность справа налево. Обычно синтаксис унарных выражений предшествует синтаксису постфиксных или основных выражений.

Ниже перечислены возможные формы унарных выражений.

- *postfix-expression*

- `++` *унарное выражение*

- `--` *унарное выражение*

- приведение *унарных операторов* *-выражение*

- **sizeof** *унарное выражение* sizeof

- *имя типа* `sizeof(` `)`

- `)` `decltype(` *выражение*

- *выражение выделения*

- *unallocation — выражение*

Любое *постфиксное* выражение считается *унарным выражением*, а так как любое первичное выражение считается *постфиксным выражением*, любые первичные выражения считаются также *унарным выражением* . Дополнительные сведения см. в разделе [постфиксные выражения](../cpp/postfix-expressions.md) и [Первичные выражения](../cpp/primary-expressions.md).

*Унарный оператор* состоит из одного или нескольких следующих символов: `* & + - ! ~`

*Выражение CAST-Expression* является унарным выражением с необязательным приведением для изменения типа. Дополнительные сведения см. в разделе [оператор CAST: ()](../cpp/cast-operator-parens.md).

*Выражение* может быть любым выражением. Дополнительные сведения см. в разделе [выражения](../cpp/expressions-cpp.md).

*Выражение выделения* ссылается на **Новый** оператор. *Выражение unallocation —* это ссылка на оператор **Delete** . Дополнительные сведения см. по ссылкам, приведенным выше.

## <a name="see-also"></a>См. также раздел

[Типы выражений](../cpp/types-of-expressions.md)
