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

Оператор *приоритет* указывает порядок операций в выражениях, содержащих более одного оператора. Оператор *ассоциативность* указывает ли, в выражении, содержащем несколько операторов с одинаковым приоритетом, операнд группируется слева от него или его на справа от нее. В следующей таблице показан приоритет и ассоциативность операторов C++ (в порядке убывания приоритета). Операторы с тем же номером приоритета имеют равный приоритет, если другие связи не заданы явно с помощью круглых скобок.

### <a name="c-operator-precedence-and-associativity"></a>Приоритет и ассоциативность операторов C++

|Описание оператора|Оператор|
|--------------------------|--------------|
|**Группе приоритет 1, не ассоциативность операторов**|
|[Разрешение области](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**Приоритет группы 2, до правой ассоциативностью**|
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
|**Приоритет группы 3, право на левую ассоциативность**|
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
|[Удалите объект](../cpp/delete-operator-cpp.md)|[delete](../cpp/delete-operator-cpp.md)|
|[Приведение](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**Приоритет группы 4, до правой ассоциативностью**|
|[Указатель на член (объекты или указатели)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[. &#42; или "->"&#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**Приоритет группы 5, до правой ассоциативностью**|
|[Умножение](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Деление](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[модуль](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**Приоритет группы 6, до правой ассоциативностью**|
|[Сложение](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[Вычитание](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**Приоритет группы 7, до правой ассоциативностью**|
|[Сдвиг влево](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[Сдвиг вправо](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**Приоритет группы 8, до правой ассоциативностью**|
|[Меньше](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[Больше](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[Меньше или равно](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[Больше или равно](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**Приоритет группы 9, до правой ассоциативностью**|
|[Равенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[Неравенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[\!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**Приоритет группы 10 правой ассоциативностью слева**|
|[Побитовое И](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**Приоритет группы 11, до правой ассоциативностью**|
|[Побитовое исключающее или](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**Приоритет группы 12, до правой ассоциативностью**|
|[Побитовое включающее или](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**Приоритет группы 13, до правой ассоциативностью**|
|[Логическое И](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**Приоритет группы 14, до правой ассоциативностью**|
|[Логическое ИЛИ](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**Приоритет группы 15, право на левую ассоциативность**|
|[условный](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**Приоритет группы 16, право на левую ассоциативность**|
|[Назначение](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[Присваивание умножения](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[Присваивание деления](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[Назначение модуля](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[Присваивание сложения](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[Присваивание вычитания](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[Присваивания сдвига влево](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[Назначение сдвига вправо](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[Присваивание побитового и](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[Побитовое присваивание включительно или](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[Побитовое исключающее или/присваивание](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**Приоритет группы 17, право на левую ассоциативность**|
|[выражение throw](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**Приоритет группы 18, до правой ассоциативностью**|
|[Запятая](../cpp/comma-operator.md)|[,](../cpp/comma-operator.md)|

## <a name="see-also"></a>См. также

[Перегрузка операторов](operator-overloading.md)