---
title: Встроенные операторы C++, приоритет и ассоциативность операторов
ms.date: 11/04/2016
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
ms.openlocfilehash: 0b560913deb57393a8547f0831e0d987eed41ab7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574061"
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>Встроенные операторы C++, приоритет и ассоциативность операторов

Язык C++ включает все операторы C и еще несколько новых операторов. Операторы определяют, какое вычисление следует выполнить с одним или несколькими операндами.

*Приоритет* оператора указывает порядок операций в выражениях, содержащих более одного оператора. *Ассоциативность* оператора указывает, группируется ли операнд с операндом слева или справа от него в выражении, содержащем несколько операторов с одинаковым приоритетом. В следующей таблице показан приоритет и ассоциативность операторов C++ (в порядке убывания приоритета). Операторы с тем же номером приоритета имеют равный приоритет, если другие связи не заданы явно с помощью круглых скобок.

### <a name="c-operator-precedence-and-associativity"></a>Приоритет и ассоциативность операторов C++

|Описание оператора|Оператор|
|--------------------------|--------------|
|**Группа с приоритетом 1, нет ассоциативности**|
|[Разрешение области](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**Группа с приоритетом 2, ассоциативность слева направо**|
|[Выбор члена (объект или указатель)](../cpp/member-access-operators-dot-and.md)|[. или "->"](../cpp/member-access-operators-dot-and.md)|
|[Индекс массива](../cpp/subscript-operator.md)|[&#91;&#93;](../cpp/subscript-operator.md)|
|[Вызов функции](../cpp/function-call-operator-parens.md)|[()](../cpp/function-call-operator-parens.md)|
|[Постфиксный инкремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Постфиксный декремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Имя типа](../cpp/typeid-operator.md)|[typeid](../cpp/typeid-operator.md)|
|[Постоянное преобразование типа](../cpp/const-cast-operator.md)|[const_cast](../cpp/const-cast-operator.md)|
|[Динамическое преобразование типа](../cpp/dynamic-cast-operator.md)|[dynamic_cast](../cpp/dynamic-cast-operator.md)|
|[Повторно интерпретируемое преобразование типа](../cpp/reinterpret-cast-operator.md)|[reinterpret_cast](../cpp/reinterpret-cast-operator.md)|
|[Статическое преобразование типа](../cpp/static-cast-operator.md)|[static_cast](../cpp/static-cast-operator.md)|
|**Группа с приоритетом 3, ассоциативность справа налево**|
|[Размер объекта или типа](../cpp/sizeof-operator.md)|[sizeof](../cpp/sizeof-operator.md)|
|[Префиксный инкремент](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Префиксный декремент](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Дополнение до единицы](../cpp/one-s-complement-operator-tilde.md)|[~](../cpp/one-s-complement-operator-tilde.md)|
|[Логическое не](../cpp/logical-negation-operator-exclpt.md)|[\!](../cpp/logical-negation-operator-exclpt.md)|
|[Унарное отрицание](../cpp/unary-plus-and-negation-operators-plus-and.md)|[-](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Унарный плюс](../cpp/unary-plus-and-negation-operators-plus-and.md)|[+](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Address-of-](../cpp/address-of-operator-amp.md)|[&amp;](../cpp/address-of-operator-amp.md)|
|[Косвенное обращение](../cpp/indirection-operator-star.md)|[&#42;](../cpp/indirection-operator-star.md)|
|[Создание объекта](../cpp/new-operator-cpp.md)|[new](../cpp/new-operator-cpp.md)|
|[Удаление объекта](../cpp/delete-operator-cpp.md)|[delete](../cpp/delete-operator-cpp.md)|
|[Приведение](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**Группа с приоритетом 4, ассоциативность слева направо**|
|[Указатель на член (объекты или указатели)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[. &#42; или "->"&#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**Группа с приоритетом 5, ассоциативность слева направо**|
|[Умножение](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Деление](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Остаток](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**Группа с приоритетом 6, ассоциативность слева направо**|
|[Сложение](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[Вычитание](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**Группа с приоритетом 7, ассоциативность слева направо**|
|[Сдвиг влево](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[Сдвиг вправо](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**Группа с приоритетом 8, ассоциативность слева направо**|
|[Меньше](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[Больше](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[Меньше или равно](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[Больше или равно](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**Группа с приоритетом 9, ассоциативность слева направо**|
|[Равенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[Неравенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[\!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**Группа с приоритетом 10, ассоциативность слева направо**|
|[Побитовое И](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**Группа с приоритетом 11, ассоциативность слева направо**|
|[Побитовое исключающее или](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**Группа с приоритетом 12, ассоциативность слева направо**|
|[Побитовое включающее или](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**Группа с приоритетом 13, ассоциативность слева направо**|
|[Логическое И](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**Группа с приоритетом 14, ассоциативность слева направо**|
|[Логическое ИЛИ](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**Группа с приоритетом 15, ассоциативность справа налево**|
|[Условный](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**Группа с приоритетом 16, ассоциативность справа налево**|
|[Присваивание](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[Умножение с присваиванием](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[Деление с присваиванием](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[Присваивание остатка](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[Сложение с присваиванием](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[Вычитание с присваиванием](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[Сдвиг влево с присваиванием](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[Сдвиг вправо с присваиванием](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[Побитовое и с присваиванием](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[Включающее или с присваиванием](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[Побитовое исключающее или с присваиванием](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**Группа с приоритетом 17, ассоциативность справа налево**|
|[Выражение throw](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**Группа с приоритетом 18, ассоциативность слева направо**|
|[Запятая](../cpp/comma-operator.md)|[,](../cpp/comma-operator.md)|

## <a name="see-also"></a>См. также

[Перегрузка операторов](operator-overloading.md)