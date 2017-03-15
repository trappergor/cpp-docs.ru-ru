---
title: "Операторы C++, приоритет и ассоциативность | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ассоциативность операторов"
  - "порядок вычисления"
  - "иерархия, оператор"
  - "множественные операторы"
  - "приоритет операторов"
  - "операторы (C++), ассоциативность"
  - "операторы (C++), иерархия"
  - "операторы [C++], приоритет"
  - "приоритет, операторы"
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Операторы C++, приоритет и ассоциативность
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Язык C\+\+ включает все операторы C и еще несколько новых операторов.  Операторы определяют, какое вычисление следует выполнить с одним или несколькими операндами.  
  
 Приоритет операторов определяет порядок операций в выражениях, содержащих более одного оператора.  Ассоциативность оператора определяет, группируется ли операнд в выражении, содержащем несколько операторов с одинаковым приоритетом, с оператором слева от него или справа от него.  В следующей таблице показан приоритет и ассоциативность операторов C\+\+ \(в порядке убывания приоритета\).  Операторы с тем же номером приоритета имеют равный приоритет, если другие связи не заданы явно с помощью круглых скобок.  
  
### Приоритет и ассоциативность операторов C\+\+  
  
|Описание оператора|Оператор|  
|------------------------|--------------|  
|`Group 1 precedence, no associativity`|  
|[Разрешение области](../cpp/scope-resolution-operator.md)|`::`|  
|`Group 2 precedence, left to right associativity`|  
|[Выбор члена для указателей \(объект или указатель\)](../Topic/Member%20Access%20Operators:%20.%20and%20-%3E.md)|`. or –>`|  
|[Нижний индекс массива](../Topic/Subscript%20Operator:.md)|`[ ]`|  
|[Вызов функции](../cpp/function-call-operator-parens.md)|`( )`|  
|[Постфиксный инкремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[Постфиксный декремент](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`––`|  
|[Имя типа](../cpp/typeid-operator.md)|`typeid( )`|  
|[Постоянное преобразование типа](../Topic/const_cast%20Operator.md)|`const_cast`|  
|[Динамическое преобразование типа](../cpp/dynamic-cast-operator.md)|`dynamic_cast`|  
|[Повторно интерпретируемое преобразование типа](../cpp/reinterpret-cast-operator.md)|`reinterpret_cast`|  
|[Статическое преобразование типа](../cpp/static-cast-operator.md)|`static_cast`|  
|`Group 3 precedence, right to left associativity`|  
|[Размер объекта или типа](../cpp/sizeof-operator.md)|`sizeof`|  
|[Префиксный инкремент](../Topic/Prefix%20Increment%20and%20Decrement%20Operators:%20++%20and%20--.md)|`++`|  
|[Префиксный декремент](../Topic/Prefix%20Increment%20and%20Decrement%20Operators:%20++%20and%20--.md)|`––`|  
|[Дополнение до единицы](../cpp/one-s-complement-operator-tilde.md)|`~`|  
|[Логическое НЕ](../cpp/logical-negation-operator-exclpt.md)|`!`|  
|[Унарное отрицание](../misc/unary-negation-operator.md)|`-`|  
|[Унарный плюс](../cpp/unary-plus-and-negation-operators-plus-and.md)|`+`|  
|[Взятие адреса](../Topic/Lvalue%20Reference%20Declarator:%20&.md)|`&`|  
|[Косвенное обращение](../cpp/indirection-operator-star.md)|`*`|  
|[Создание объекта](../cpp/new-operator-cpp.md)|`new`|  
|[Удаление объекта](../cpp/delete-operator-cpp.md)|`delete`|  
|[Cast](../Topic/Cast%20Operator:%20\(\).md)|`Cast: ()`|  
|`Group 4 precedence, left to right associativity`|  
|[Указатель на член \(объекты или указатели\)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|`.* or –>*`|  
|`Group 5 precedence, left to right associativity`|  
|[Умножение](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`*`|  
|[Деление](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`/`|  
|[Модуль](../cpp/multiplicative-operators-and-the-modulus-operator.md)|`%`|  
|`Group 6 precedence, left to right associativity`|  
|[Сложение](../cpp/additive-operators-plus-and.md)|`+`|  
|[Вычитание](../cpp/additive-operators-plus-and.md)|`–`|  
|`Group 7 precedence, left to right associativity`|  
|[Сдвиг влево](../Topic/Left%20Shift%20and%20Right%20Shift%20Operators%20\(%3E%3E%20and%20%3C%3C\).md)|`<<`|  
|[Сдвиг вправо](../Topic/Left%20Shift%20and%20Right%20Shift%20Operators%20\(%3E%3E%20and%20%3C%3C\).md)|`>>`|  
|`Group 8 precedence, left to right associativity`|  
|[Меньше](../cpp/relational-operators-equal-and-equal.md)|`<`|  
|[Больше](../cpp/relational-operators-equal-and-equal.md)|`>`|  
|[Меньше или равно](../cpp/relational-operators-equal-and-equal.md)|`<=`|  
|[Больше или равно](../cpp/relational-operators-equal-and-equal.md)|`>=`|  
|`Group 9 precedence, left to right associativity`|  
|[Равенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`==`|  
|[Неравенство](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|`!=`|  
|`Group 10 precedence left to right associativity`|  
|[Побитовое И](../cpp/bitwise-and-operator-amp.md)|`&`|  
|`Group 11 precedence, left to right associativity`|  
|[Побитовое исключающее ИЛИ](../cpp/bitwise-exclusive-or-operator-hat.md)|`^`|  
|`Group 12 precedence, left to right associativity`|  
|[Побитовое включающее ИЛИ](../cpp/bitwise-inclusive-or-operator-pipe.md)|`&#124;`|  
|`Group 13 precedence, left to right associativity`|  
|[Логическое И](../Topic/Logical%20AND%20Operator:%20&&.md)|`&&`|  
|`Group 14 precedence, left to right associativity`|  
|[Логическое ИЛИ](../cpp/logical-or-operator-pipe-pipe.md)|`&#124;&#124;`|  
|`Group 15 precedence, right to left associativity`|  
|[Условие](../cpp/conditional-operator-q.md)|`? :`|  
|`Group 16 precedence, right to left associativity`|  
|[Присваивание](../cpp/assignment-operators.md)|`=`|  
|[Присваивание умножения](../cpp/assignment-operators.md)|`*=`|  
|[Присваивание деления](../cpp/assignment-operators.md)|`/=`|  
|[Назначение модуля](../cpp/assignment-operators.md)|`%=`|  
|[Присваивание сложения](../cpp/assignment-operators.md)|`+=`|  
|[Присваивание вычитания](../cpp/assignment-operators.md)|`–=`|  
|[Присваивание сдвига влево](../cpp/assignment-operators.md)|`<<=`|  
|[Присваивание сдвига вправо](../cpp/assignment-operators.md)|`>>=`|  
|[Назначение побитового И](../cpp/assignment-operators.md)|`&=`|  
|[Назначение побитового включающего ИЛИ](../cpp/assignment-operators.md)|`&#124;=`|  
|[Назначение побитового исключающего ИЛИ](../cpp/assignment-operators.md)|`^=`|  
|`Group 17 precedence, right to left associativity`|  
|[Выражение Throw](../cpp/try-throw-and-catch-statements-cpp.md)|`throw`|  
|`Group 18 precedence, left to right associativity`|  
|[Comma](../cpp/comma-operator.md)|`,`|  
  
## См. также  
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Перегрузка операторов](../cpp/operator-overloading.md)