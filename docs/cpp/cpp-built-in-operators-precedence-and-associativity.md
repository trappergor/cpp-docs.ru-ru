---
title: C++Встроенные операторы, приоритет и ассоциативность
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
ms.openlocfilehash: 36e7ce77e24366be10b75f5bb4f8830363594301
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180411"
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++Встроенные операторы, приоритет и ассоциативность

Язык C++ включает все операторы C и еще несколько новых операторов. Операторы определяют, какое вычисление следует выполнить с одним или несколькими операндами.

*Приоритет* операторов задает порядок операций в выражениях, содержащих более одного оператора. *Ассоциативность* операторов указывает, будет ли операнд в выражении, содержащем несколько операторов с одинаковым приоритетом, группироваться по левому краю или по правому. В следующей таблице показан приоритет и ассоциативность операторов C++ (в порядке убывания приоритета). Операторы с тем же номером приоритета имеют равный приоритет, если другие связи не заданы явно с помощью круглых скобок.

### <a name="c-operator-precedence-and-associativity"></a>Приоритет и ассоциативность операторов C++

|Описание оператора|Оператор|
|--------------------------|--------------|
|**Приоритет группы 1, без ассоциативности**|
|[Разрешение области](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**Приоритет группы 2, ассоциативность слева направо**|
|[Выбор элементов (объект или указатель)](../cpp/member-access-operators-dot-and.md)|[. или->](../cpp/member-access-operators-dot-and.md)|
|[Индекс массива](../cpp/subscript-operator.md)|[&#91;&#93;](../cpp/subscript-operator.md)|
|[Вызов функции](../cpp/function-call-operator-parens.md)|[()](../cpp/function-call-operator-parens.md)|
|[Постфиксный инкремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Постфиксное уменьшение](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Имя типа](../cpp/typeid-operator.md)|[typeid](../cpp/typeid-operator.md)|
|[Преобразование типов констант](../cpp/const-cast-operator.md)|[const_cast](../cpp/const-cast-operator.md)|
|[Динамическое преобразование типов](../cpp/dynamic-cast-operator.md)|[dynamic_cast](../cpp/dynamic-cast-operator.md)|
|[Преобразование повторно интерпретируемого типа](../cpp/reinterpret-cast-operator.md)|[reinterpret_cast](../cpp/reinterpret-cast-operator.md)|
|[Преобразование статического типа](../cpp/static-cast-operator.md)|[static_cast](../cpp/static-cast-operator.md)|
|**Приоритет группы 3, ассоциативность справа налево**|
|[Размер объекта или типа](../cpp/sizeof-operator.md)|[sizeof](../cpp/sizeof-operator.md)|
|[Приращение префикса](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Декремента префикса](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Дополнение одного](../cpp/one-s-complement-operator-tilde.md)|[~](../cpp/one-s-complement-operator-tilde.md)|
|[Логическое не](../cpp/logical-negation-operator-exclpt.md)|[!](../cpp/logical-negation-operator-exclpt.md)|
|[Унарное отрицание](../cpp/unary-plus-and-negation-operators-plus-and.md)|[-](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Унарный плюс](../cpp/unary-plus-and-negation-operators-plus-and.md)|[+](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Адрес-из](../cpp/address-of-operator-amp.md)|[&amp;](../cpp/address-of-operator-amp.md)|
|[Косвенного обращения](../cpp/indirection-operator-star.md)|[&#42;](../cpp/indirection-operator-star.md)|
|[Создание объекта](../cpp/new-operator-cpp.md)|[новую](../cpp/new-operator-cpp.md)|
|[Уничтожить объект](../cpp/delete-operator-cpp.md)|[delete](../cpp/delete-operator-cpp.md)|
|[Cast](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**Приоритет группы 4, ассоциативность слева направо**|
|[Указатель на член (объекты или указатели)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[. &#42; или->&#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**Приоритет группы 5, ассоциативность слева направо**|
|[Умножение](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Деление](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Модул](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**Приоритет группы 6, ассоциативность слева направо**|
|[Сложение](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[Вычитание](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**Приоритет группы 7, ассоциативность слева направо**|
|[Сдвиг влево](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[Сдвиг вправо](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**Приоритет группы 8, ассоциативность слева направо**|
|[Меньше чем](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[Больше чем](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[Меньше или равно](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[Больше или равно](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**Приоритет группы 9, ассоциативность слева направо**|
|[Равенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[Неравенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**Группа 10 приоритета с ассоциативностью слева направо**|
|[Побитовое И](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**Приоритет группы 11, ассоциативность слева направо**|
|[Побитовое исключающее или](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**Приоритет группы 12, ассоциативность слева направо**|
|[Побитовое инклюзивное или](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**Приоритет группы 13, ассоциативность слева направо**|
|[Логическое И](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**Приоритет группы 14, ассоциативность слева направо**|
|[Логическое ИЛИ](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**Группирование с приоритетом 15, с ассоциативностью справа налево**|
|[Условие](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**Группирование с приоритетом 16, справа налево ассоциативность**|
|[Присваивание](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[Присваивание умножения](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[Присваивание деления](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[Присваивание модуля](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[Назначение сложения](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[Назначение вычитания](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[Присваивание сдвига влево](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[Присваивание сдвига вправо](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[Присваивание побитового и](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[Побитовое инклюзивное или присваивание](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[Побитовое исключающее или](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**Приоритет группы 17, ассоциативность справа налево**|
|[выражение Throw](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**Приоритет группы 18, ассоциативность слева направо**|
|[Запятая](../cpp/comma-operator.md)|[,](../cpp/comma-operator.md)|

## <a name="see-also"></a>См. также раздел

[Перегрузка операторов](operator-overloading.md)
