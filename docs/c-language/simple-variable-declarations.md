---
title: Простые объявления переменных
ms.date: 11/04/2016
helpviewer_keywords:
- untyped variables
- declaring variables, simple
ms.assetid: b07adf9d-9e79-4b64-8a34-e6fe1c7eccec
ms.openlocfilehash: 27710dabe512332564ee557a9d022457d9fddc5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158240"
---
# <a name="simple-variable-declarations"></a>Простые объявления переменных

Объявление обычной переменной, простейшей формы прямого декларатора, указывает имя и тип переменной. Оно также указывает класс хранения и тип данных переменной.

Классы хранения или типы (или и то, и другое) требуются в объявлениях переменных. Нетипизированные переменные (например, `var;`) создают предупреждения.

## <a name="syntax"></a>Синтаксис

*declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<sub>opt</sub> *direct-declarator*

*direct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*

*identifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*nondigit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier* *nondigit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier* *digit*

В случае арифметического типа, типа структуры, типа объединения, типа void и типов, представляемых именами `typedef`, простые деклараторы можно использовать в объявлении, поскольку описатель предоставляет всю вводимую информацию. Для типов указателя, массива и функций требуются более сложные деклараторы.

Чтобы указать несколько переменных в одном объявлении, можно использовать список идентификаторов, разделенных запятыми ( **,** ). Все переменные, определенные в объявлении, имеют один и тот же базовый тип. Пример:

```C
int x, y;        /* Declares two simple variables of type int */
int const z = 1; /* Declares a constant value of type int */
```

Переменные `x` и `y` могут содержать любое значение в наборе, определенном типом `int` для конкретной реализации. Простой объект `z` инициализируется значением 1 и не может быть изменен.

Если бы объявление `z` было выполнено для неинициализированной статической переменной или в области видимости файла, было бы получено начальное значение 0, которое было бы неизменяемым.

```C
unsigned long reply, flag; /* Declares two variables
                              named reply and flag     */
```

В этом примере обе переменные `reply` и `flag` имеют тип `unsigned long` и содержат целочисленные значения без знака.

## <a name="see-also"></a>См. также

[Деклараторы и объявления переменных](../c-language/declarators-and-variable-declarations.md)
