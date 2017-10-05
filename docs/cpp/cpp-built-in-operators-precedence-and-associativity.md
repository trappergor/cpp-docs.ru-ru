---
title: "Встроенный C++ операторы, приоритет и ассоциативность операторов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators (C++), hierarchy
- operator precedence
- precedence, operators
- operators (C++), associativity
- multiple operators
- associativity of operators
- operators [C++], precedence
- evaluation order
- hierarchy, operator
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6c45b0d3ff2aaee6763b73949727dcde5ee744bc
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="c-built-in-operators-precedence-and-associativity"></a>Встроенный C++ операторы, приоритет и ассоциативность операторов
Язык C++ включает все операторы C и еще несколько новых операторов. Операторы определяют, какое вычисление следует выполнить с одним или несколькими операндами.  
  
 Приоритет операторов определяет порядок операций в выражениях, содержащих более одного оператора. Ассоциативность оператора определяет, группируется ли операнд в выражении, содержащем несколько операторов с одинаковым приоритетом, с оператором слева от него или справа от него. В следующей таблице показан приоритет и ассоциативность операторов C++ (в порядке убывания приоритета). Операторы с тем же номером приоритета имеют равный приоритет, если другие связи не заданы явно с помощью круглых скобок.  
  
### <a name="c-operator-precedence-and-associativity"></a>Приоритет и ассоциативность операторов C++  
  
|Описание оператора|Оператор|  
|--------------------------|--------------|  
|`Group 1 precedence, no associativity`|  
|[Разрешение области](../cpp/scope-resolution-operator.md)|`::`|  
|`Group 2 precedence, left to right associativity`|  
|[Выбор элемента (объект или указатель)](../cpp/member-access-operators-dot-and.md)|`. or ->`|  
|[Нижний индекс массива](../cpp/subscript-operator.md)|`[ ]`|  
|[Вызов функции](../cpp/function-call-operator-parens.md)|`( )`|  
|[Постфиксный инкремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Постфиксный декремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`--`|  
|[Имя типа](../cpp/typeid-operator.md)|`typeid( )`|  
|[Постоянное преобразование типа](../cpp/const-cast-operator.md)|`const_cast`|  
|[Динамическое преобразование типа](../cpp/dynamic-cast-operator.md)|`dynamic_cast`|  
|[Повторно интерпретируемое преобразование типа](../cpp/reinterpret-cast-operator.md)|`reinterpret_cast`|  
|[Статическое преобразование типа](../cpp/static-cast-operator.md)|`static_cast`|  
|`Group 3 precedence, right to left associativity`|  
|[Размер объекта или типа](../cpp/sizeof-operator.md)|`sizeof`|  
|[Префиксный инкремент](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Префиксный декремент](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|`--`|  
|[Дополнение до единицы](../cpp/one-s-complement-operator-tilde.md)|`~`|  
|[Логическое не](../cpp/logical-negation-operator-exclpt.md)|`!`|  
|[Унарное отрицание](../cpp/unary-plus-and-negation-operators-plus-and.md)|`-`|  
|[Унарный плюс](../cpp/unary-plus-and-negation-operators-plus-and.md)|`+`|  
|[Взятия адреса](../cpp/lvalue-reference-declarator-amp.md)|`&`|  
|[Косвенное обращение](../cpp/indirection-operator-star.md)|`*`|  
|[Создание объекта](../cpp/new-operator-cpp.md)|`new`|  
|[Удаление объекта](../cpp/delete-operator-cpp.md)|`delete`|  
|[Приведение типов](../cpp/cast-operator-parens.md)|`Cast: ()`|  
|`Group 4 precedence, left to right associativity`|  
|[Указатель на член (объекты или указатели)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|`.* or ->*`|  
|`Group 5 precedence, left to right associativity`|  
|[Умножение](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`*`|  
|[Деления](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`/`|  
|[Остатка от деления](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`%`|  
|`Group 6 precedence, left to right associativity`|  
|[Добавление](../cpp/additive-operators-plus-and.md)|`+`|  
|[Вычитание](../cpp/additive-operators-plus-and.md)|`-`|  
|`Group 7 precedence, left to right associativity`|  
|[Сдвиг влево](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|`<<`|  
|[Сдвиг вправо](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|`>>`|  
|`Group 8 precedence, left to right associativity`|  
|[Меньше](../cpp/relational-operators-equal-and-equal.md)|`<`|  
|[Больше](../cpp/relational-operators-equal-and-equal.md)|`>`|  
|[Меньше или равно](../cpp/relational-operators-equal-and-equal.md)|`<=`|  
|[Больше или равно](../cpp/relational-operators-equal-and-equal.md)|`>=`|  
|`Group 9 precedence, left to right associativity`|  
|[Равенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`==`|  
|[Неравенства](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`!=`|  
|`Group 10 precedence left to right associativity`|  
|[Побитовое и](../cpp/bitwise-and-operator-amp.md)|`&`|  
|`Group 11 precedence, left to right associativity`|  
|[Побитовое исключающее или](../cpp/bitwise-exclusive-or-operator-hat.md)|`^`|  
|`Group 12 precedence, left to right associativity`|  
|[Побитовое включающее или](../cpp/bitwise-inclusive-or-operator-pipe.md)|`&#124;`|  
|`Group 13 precedence, left to right associativity`|  
|[Логическое и](../cpp/logical-and-operator-amp-amp.md)|`&&`|  
|`Group 14 precedence, left to right associativity`|  
|[Логическое или](../cpp/logical-or-operator-pipe-pipe.md)|`&#124;&#124;`|  
|`Group 15 precedence, right to left associativity`|  
|[Условный](../cpp/conditional-operator-q.md)|`? :`|  
|`Group 16 precedence, right to left associativity`|  
|[Назначение](../cpp/assignment-operators.md)|`=`|  
|[Присваивание умножения](../cpp/assignment-operators.md)|`*=`|  
|[Присваивание деления](../cpp/assignment-operators.md)|`/=`|  
|[Назначение модуля](../cpp/assignment-operators.md)|`%=`|  
|[Присваивание сложения](../cpp/assignment-operators.md)|`+=`|  
|[Присваивание вычитания](../cpp/assignment-operators.md)|`-=`|  
|[Присваивания сдвига влево](../cpp/assignment-operators.md)|`<<=`|  
|[Назначение сдвига вправо](../cpp/assignment-operators.md)|`>>=`|  
|[Назначение побитового и](../cpp/assignment-operators.md)|`&=`|  
|[Побитовое назначение включительно или](../cpp/assignment-operators.md)|`&#124;=`|  
|[Побитовое исключающее или/присваивание](../cpp/assignment-operators.md)|`^=`|  
|`Group 17 precedence, right to left associativity`|  
|[выражение throw](../cpp/try-throw-and-catch-statements-cpp.md)|`throw`|  
|`Group 18 precedence, left to right associativity`|  
|[Запятая](../cpp/comma-operator.md)|`,`|  
  
## <a name="see-also"></a>См. также  
[Перегрузка операторов](operator-overloading.md)



