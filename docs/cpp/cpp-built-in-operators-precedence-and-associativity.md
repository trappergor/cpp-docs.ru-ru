---
title: Встроенные операторы, приоритет и ассоциативность C++
ms.date: 07/23/2020
helpviewer_keywords:
- operators (C++), hierarchy
- operator precedence
- precedence, operators
- operators (C++), associativity
- multiple operators [C++]
- associativity of operators [C++]
- operators [C++], precedence
- evaluation order
- hierarchy, operator
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
ms.openlocfilehash: 10c9e5db569ba211ed8d42386816b4f6bb71ee29
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221774"
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>Встроенные операторы, приоритет и ассоциативность C++

Язык C++ включает все операторы C и еще несколько новых операторов. Операторы определяют, какое вычисление следует выполнить с одним или несколькими операндами.

## <a name="precedence-and-associativity"></a>Приоритет и ассоциативность

*Приоритет* операторов задает порядок операций в выражениях, содержащих более одного оператора. *Ассоциативность* операторов указывает, будет ли операнд в выражении, содержащем несколько операторов с одинаковым приоритетом, группироваться по левому краю или по правому.

## <a name="alternative-spellings"></a>Альтернативные слова

C++ указывает альтернативные слова для некоторых операторов. В языке C альтернативное написание предоставляется в виде макросов в \<iso646.h> заголовке. В C++ эти альтернативы являются ключевыми словами, использование \<iso646.h> или эквивалент C++ \<ciso646> не рекомендуется. В Microsoft C++ [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора или необходим для включения альтернативного написания.

## <a name="c-operator-precedence-and-associativity-table"></a>Приоритет операторов C++ и таблица ассоциативных данных

В следующей таблице показан приоритет и ассоциативность операторов C++ (в порядке убывания приоритета). Операторы с тем же номером приоритета имеют равный приоритет, если другие связи не заданы явно с помощью круглых скобок.

| Описание оператора | Оператор | Альтернатива |
|--|--|--|
| **Приоритет группы 1, без ассоциативности** |
| [Разрешение области](../cpp/scope-resolution-operator.md) | [`::`](../cpp/scope-resolution-operator.md) |
| **Приоритет группы 2, ассоциативность слева направо** |
| [Выбор члена для указателей (объект или указатель)](../cpp/member-access-operators-dot-and.md) | [`.`ни`->`](../cpp/member-access-operators-dot-and.md) |
| [Индекс массива](../cpp/subscript-operator.md) | [`[]`](../cpp/subscript-operator.md) |
| [Вызов функции](../cpp/function-call-operator-parens.md) | [`()`](../cpp/function-call-operator-parens.md) |
| [Постфиксный инкремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) | [`++`](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) |
| [Постфиксный декремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) | [`--`](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) |
| [Имя типа](../cpp/typeid-operator.md) | [`typeid`](../cpp/typeid-operator.md) |
| [Постоянное преобразование типа](../cpp/const-cast-operator.md) | [`const_cast`](../cpp/const-cast-operator.md) |
| [Динамическое преобразование типа](../cpp/dynamic-cast-operator.md) | [`dynamic_cast`](../cpp/dynamic-cast-operator.md) |
| [Повторно интерпретируемое преобразование типа](../cpp/reinterpret-cast-operator.md) | [`reinterpret_cast`](../cpp/reinterpret-cast-operator.md) |
| [Статическое преобразование типа](../cpp/static-cast-operator.md) | [`static_cast`](../cpp/static-cast-operator.md) |
| **Приоритет группы 3, ассоциативность справа налево** |
| [Размер объекта или типа](../cpp/sizeof-operator.md) | [`sizeof`](../cpp/sizeof-operator.md) |
| [Префиксный инкремент](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) | [`++`](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) |
| [Префиксный декремент](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) | [`--`](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) |
| [Дополнение одного](../cpp/one-s-complement-operator-tilde.md) | [`~`](../cpp/one-s-complement-operator-tilde.md) | **`compl`** |
| [Логическое не](../cpp/logical-negation-operator-exclpt.md) | [`!`](../cpp/logical-negation-operator-exclpt.md) | **`not`** |
| [Унарное отрицание](../cpp/unary-plus-and-negation-operators-plus-and.md) | [`-`](../cpp/unary-plus-and-negation-operators-plus-and.md) |
| [Унарный плюс](../cpp/unary-plus-and-negation-operators-plus-and.md) | [`+`](../cpp/unary-plus-and-negation-operators-plus-and.md) |
| [Взятие адреса](../cpp/address-of-operator-amp.md) | [`&`](../cpp/address-of-operator-amp.md) |
| [Косвенное обращение](../cpp/indirection-operator-star.md) | [`*`](../cpp/indirection-operator-star.md) |
| [Создать объект](../cpp/new-operator-cpp.md) | [`new`](../cpp/new-operator-cpp.md) |
| [Уничтожение объекта](../cpp/delete-operator-cpp.md) | [`delete`](../cpp/delete-operator-cpp.md) |
| [Приведение](../cpp/cast-operator-parens.md) | [`()`](../cpp/cast-operator-parens.md) |
| **Приоритет группы 4, ассоциативность слева направо** |
| [Указатель на член (объекты или указатели)](../cpp/pointer-to-member-operators-dot-star-and-star.md) | [`.*`ни`->*`](../cpp/pointer-to-member-operators-dot-star-and-star.md) |
| **Приоритет группы 5, ассоциативность слева направо** |
| [Умножение](../cpp/multiplicative-operators-and-the-modulus-operator.md) | [`*`](../cpp/multiplicative-operators-and-the-modulus-operator.md) |
| [Отдел](../cpp/multiplicative-operators-and-the-modulus-operator.md) | [`/`](../cpp/multiplicative-operators-and-the-modulus-operator.md) |
| [Modulus](../cpp/multiplicative-operators-and-the-modulus-operator.md) | [`%`](../cpp/multiplicative-operators-and-the-modulus-operator.md) |
| **Приоритет группы 6, ассоциативность слева направо** |
| [Сложение](../cpp/additive-operators-plus-and.md) | [`+`](../cpp/additive-operators-plus-and.md) |
| [Вычитание](../cpp/additive-operators-plus-and.md) | [`-`](../cpp/additive-operators-plus-and.md) |
| **Приоритет группы 7, ассоциативность слева направо** |
| [Сдвиг влево](../cpp/left-shift-and-right-shift-operators-input-and-output.md) | [`<<`](../cpp/left-shift-and-right-shift-operators-input-and-output.md) |
| [Сдвиг вправо](../cpp/left-shift-and-right-shift-operators-input-and-output.md) | [`>>`](../cpp/left-shift-and-right-shift-operators-input-and-output.md) |
| **Приоритет группы 8, ассоциативность слева направо** |
| [Меньше чем](../cpp/relational-operators-equal-and-equal.md) | [`<`](../cpp/relational-operators-equal-and-equal.md) |
| [Больше чем](../cpp/relational-operators-equal-and-equal.md) | [`>`](../cpp/relational-operators-equal-and-equal.md) |
| [Меньше или равно](../cpp/relational-operators-equal-and-equal.md) | [`<=`](../cpp/relational-operators-equal-and-equal.md) |
| [Больше или равно](../cpp/relational-operators-equal-and-equal.md) | [`>=`](../cpp/relational-operators-equal-and-equal.md) |
| **Приоритет группы 9, ассоциативность слева направо** |
| [Равенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) | [`==`](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) |
| [Неравенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) | [`!=`](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) | **`not_eq`** |
| **Группа 10 приоритета с ассоциативностью слева направо** |
| [Побитовое И](../cpp/bitwise-and-operator-amp.md) | [`&`](../cpp/bitwise-and-operator-amp.md) | **`bitand`** |
| **Приоритет группы 11, ассоциативность слева направо** |
| [Побитовое исключающее ИЛИ](../cpp/bitwise-exclusive-or-operator-hat.md) | [`^`](../cpp/bitwise-exclusive-or-operator-hat.md) | **`xor`** |
| **Приоритет группы 12, ассоциативность слева направо** |
| [Побитовое ИЛИ](../cpp/bitwise-inclusive-or-operator-pipe.md) | [`|`](../cpp/bitwise-inclusive-or-operator-pipe.md) | **`bitor`** |
| **Приоритет группы 13, ассоциативность слева направо** |
| [Логическое И](../cpp/logical-and-operator-amp-amp.md) | [`&&`](../cpp/logical-and-operator-amp-amp.md) | **`and`** |
| **Приоритет группы 14, ассоциативность слева направо** |
| [Логическое ИЛИ](../cpp/logical-or-operator-pipe-pipe.md) | [`||`](../cpp/logical-or-operator-pipe-pipe.md) | **`or`** |
| **Группирование с приоритетом 15, с ассоциативностью справа налево** |
| [Условная логика](../cpp/conditional-operator-q.md) | [`? :`](../cpp/conditional-operator-q.md) |
| **Группирование с приоритетом 16, справа налево ассоциативность** |
| [Назначение](../cpp/assignment-operators.md) | [`=`](../cpp/assignment-operators.md) |
| [Присваивание умножения](../cpp/assignment-operators.md) | [`*=`](../cpp/assignment-operators.md) |
| [Присваивание деления](../cpp/assignment-operators.md) | [`/=`](../cpp/assignment-operators.md) |
| [Назначение модуля](../cpp/assignment-operators.md) | [`%=`](../cpp/assignment-operators.md) |
| [Присваивание сложения](../cpp/assignment-operators.md) | [`+=`](../cpp/assignment-operators.md) |
| [Присваивание вычитания](../cpp/assignment-operators.md) | [`-=`](../cpp/assignment-operators.md) |
| [Присваивание сдвига влево](../cpp/assignment-operators.md) | [`<<=`](../cpp/assignment-operators.md) |
| [Присваивание сдвига вправо](../cpp/assignment-operators.md) | [`>>=`](../cpp/assignment-operators.md) |
| [Назначение побитового И](../cpp/assignment-operators.md) | [`&=`](../cpp/assignment-operators.md) | **`and_eq`** |
| [Назначение побитового включающего ИЛИ](../cpp/assignment-operators.md) | [`|=`](../cpp/assignment-operators.md) | **`or_eq`** |
| [Назначение побитового исключающего ИЛИ](../cpp/assignment-operators.md) | [`^=`](../cpp/assignment-operators.md) | **`xor_eq`** |
| **Приоритет группы 17, ассоциативность справа налево** |
| [Выражение Throw](../cpp/try-throw-and-catch-statements-cpp.md) | [`throw`](../cpp/try-throw-and-catch-statements-cpp.md) |
| **Приоритет группы 18, ассоциативность слева направо** |
| [Символа](../cpp/comma-operator.md) | [,](../cpp/comma-operator.md) |

## <a name="see-also"></a>См. также раздел

[Перегрузка операторов](operator-overloading.md)
