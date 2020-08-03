---
title: Вызов функций (C)
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
ms.openlocfilehash: 23531f25128fc267caa3a3cad5f2c52e603a2cc6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229692"
---
# <a name="function-call-c"></a>Вызов функций (C)

*Вызов функции* — это выражение, которое содержит имя вызываемой функции или значение указателя на функцию и, при необходимости, аргументы, передаваемые в эту функцию.

## <a name="syntax"></a>Синтаксис

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **(**  *argument-expression-list*<sub>opt</sub> **)**

*argument-expression-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*assignment-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*argument-expression-list* **,** *assignment-expression*

Выражение *postfix-expression* должно вычислять адрес функции (например, идентификатор функции или значение указателя функции), а *argument-expression-list* содержит список выражений (разделенных запятыми), значения которых (аргументы) передаются функции. Аргумент *argument-expression-list* может быть пустым.

Выражение вызова функции имеет значение и тип возвращаемого значения функции. Функция не может возвращать объект типа массива. Если возвращаемый тип функции — **`void`** (то есть объявлено, что функция никогда не возвращает значение), выражение вызова функции также имеет тип **`void`** . (Дополнительные сведения см. в разделе [Вызовы функций](../c-language/function-calls.md).)

## <a name="see-also"></a>См. также

[Оператор вызова функции: ()](../cpp/function-call-operator-parens.md)
