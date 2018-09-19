---
title: Вызов функций в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ec4e92774cdec75e47c07407ee72444a7486f7f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751339"
---
# <a name="function-call-c"></a>Вызов функций (C)

*Вызов функции* — это выражение, которое содержит имя вызываемой функции или значение указателя на функцию и, при необходимости, аргументы, передаваемые в эту функцию.  
  
## <a name="syntax"></a>Синтаксис

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **(**  *argument-expression-list*<sub>opt</sub> **)**  
  
*argument-expression-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*assignment-expression*<br/> &nbsp;&nbsp;&nbsp;&nbsp;*argument-expression-list* **,** *assignment-expression*  
  
Выражение *postfix-expression* должно вычислять адрес функции (например, идентификатор функции или значение указателя функции), а *argument-expression-list* содержит список выражений (разделенных запятыми), значения которых (аргументы) передаются функции. Аргумент *argument-expression-list* может быть пустым.  
  
Выражение вызова функции имеет значение и тип возвращаемого значения функции. Функция не может возвращать объект типа массива. Если тип возвращаемого значения функции — `void` (то есть объявлено, что функция никогда не возвращает значение), выражение вызова функции также имеет тип `void`. (Дополнительные сведения см. в разделе [Вызовы функций](../c-language/function-calls.md).)  
  
## <a name="see-also"></a>См. также

[Оператор вызова функции: ()](../cpp/function-call-operator-parens.md)