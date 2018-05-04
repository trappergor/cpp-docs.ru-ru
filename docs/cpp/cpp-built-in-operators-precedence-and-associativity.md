---
title: Встроенный C++ операторы, приоритет и ассоциативность операторов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4d2bb339d4147e6ea82c713d83a046e0e9780bb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>Встроенный C++ операторы, приоритет и ассоциативность операторов

Язык C++ включает все операторы C и еще несколько новых операторов. Операторы определяют, какое вычисление следует выполнить с одним или несколькими операндами.

Оператор *приоритет* указывает порядок операций в выражениях, содержащих более одного оператора. Оператор *ассоциативность* указывает, в выражении, содержащем несколько операторов с одинаковым приоритетом, группируется ли операнд с оператором слева от него или справа. В следующей таблице показан приоритет и ассоциативность операторов C++ (в порядке убывания приоритета). Операторы с тем же номером приоритета имеют равный приоритет, если другие связи не заданы явно с помощью круглых скобок.

### <a name="c-operator-precedence-and-associativity"></a>Приоритет и ассоциативность операторов C++

|Описание оператора|Оператор|
|--------------------------|--------------|
|**Группировать приоритет 1, не ассоциативность операторов**|
|[Разрешение области](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**Группа 2 приоритета, левый правой ассоциативностью**|
|[Выбор элемента (объект или указатель)](../cpp/member-access-operators-dot-and.md)|[. или "->"](../cpp/member-access-operators-dot-and.md)|
|[Нижний индекс массива](../cpp/subscript-operator.md)|[&#91;&#93;](../cpp/subscript-operator.md)|
|[Вызов функции](../cpp/function-call-operator-parens.md)|[()](../cpp/function-call-operator-parens.md)|
|[Постфиксный инкремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Постфиксный декремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Имя типа](../cpp/typeid-operator.md)|[typeid](../cpp/typeid-operator.md)|
|[Постоянное преобразование типа](../cpp/const-cast-operator.md)|[const_cast](../cpp/const-cast-operator.md)|
|[Динамическое преобразование типа](../cpp/dynamic-cast-operator.md)|[dynamic_cast](../cpp/dynamic-cast-operator.md)|
|[Повторно интерпретируемое преобразование типа](../cpp/reinterpret-cast-operator.md)|[reinterpret_cast](../cpp/reinterpret-cast-operator.md)|
|[Статическое преобразование типа](../cpp/static-cast-operator.md)|[static_cast](../cpp/static-cast-operator.md)|
|**Группа 3 приоритета, право ассоциативность слева**|
|[Размер объекта или типа](../cpp/sizeof-operator.md)|[sizeof](../cpp/sizeof-operator.md)|
|[Префиксный инкремент](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Префиксный декремент](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Дополнение до единицы](../cpp/one-s-complement-operator-tilde.md)|[~](../cpp/one-s-complement-operator-tilde.md)|
|[Логическое не](../cpp/logical-negation-operator-exclpt.md)|[!](../cpp/logical-negation-operator-exclpt.md)|
|[Унарное отрицание](../cpp/unary-plus-and-negation-operators-plus-and.md)|[-](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Унарный плюс](../cpp/unary-plus-and-negation-operators-plus-and.md)|[+](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Взятия адреса](../cpp/address-of-operator-amp.md)|[&amp;](../cpp/address-of-operator-amp.md)|
|[Косвенное обращение](../cpp/indirection-operator-star.md)|[&#42;](../cpp/indirection-operator-star.md)|
|[Создание объекта](../cpp/new-operator-cpp.md)|[new](../cpp/new-operator-cpp.md)|
|[Удаление объекта](../cpp/delete-operator-cpp.md)|[delete](../cpp/delete-operator-cpp.md)|
|[Приведение типов](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**Приоритет группы 4, левый правой ассоциативностью**|
|[Указатель на член (объекты или указатели)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[. &#42; или "->"&#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**Приоритет группы 5, левый правой ассоциативностью**|
|[Умножение](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Деление](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Остатка от деления](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**Приоритет группы 6, левый правой ассоциативностью**|
|[Сложение](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[Вычитание](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**Приоритет группы 7, левый правой ассоциативностью**|
|[Сдвиг влево](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[Сдвиг вправо](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**Приоритет группы 8, левый правой ассоциативностью**|
|[Меньше](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[Больше](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[Меньше или равно](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[Больше или равно](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**Приоритет группы 9, левый правой ассоциативностью**|
|[Равенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[Неравенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**Приоритет группы 10 правой ассоциативностью слева**|
|[Побитовое И](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**Приоритет группы 11, левый правой ассоциативностью**|
|[Побитовое исключающее или](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**Приоритет группы 12, левый правой ассоциативностью**|
|[Побитовое включающее или](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**Приоритет группы 13, левый правой ассоциативностью**|
|[Логическое И](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**Приоритет группы 14, левый правой ассоциативностью**|
|[Логическое ИЛИ](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**Приоритет группы 15, право ассоциативность слева**|
|[Условный](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**Приоритет группы 16, право ассоциативность слева**|
|[Назначение](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[Присваивание умножения](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[Присваивание деления](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[Назначение модуля](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[Присваивание сложения](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[Присваивание вычитания](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[Присваивания сдвига влево](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[Назначение сдвига вправо](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[Назначение побитового и](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[Побитовое назначение включительно или](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[Побитовое исключающее или/присваивание](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**Приоритет группы 17, право ассоциативность слева**|
|[выражение throw](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**Приоритет группы 18, левый правой ассоциативностью**|
|[Запятая](../cpp/comma-operator.md)|[,](../cpp/comma-operator.md)|

## <a name="see-also"></a>См. также

[Перегрузка операторов](operator-overloading.md)


