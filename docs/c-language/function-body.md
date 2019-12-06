---
title: Текст функции
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
ms.openlocfilehash: 2d2e04572de91b161237d999bb95cfda26256c54
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857103"
---
# <a name="function-body"></a>Текст функции

*Тело функции* — это составной оператор, содержащий операторы, которые определяют выполняемые функцией действия.

## <a name="syntax"></a>Синтаксис

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* — это \*, зависящее от Майкрософт /

*compound-statement*: /\* Текст функции \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *declaration-list*<sub>opt</sub> *statement-list*<sub>opt</sub> **}**

Если не указано иное, переменные, объявленные в теле функции (*локальные переменные*), имеют класс хранения **auto**. При вызове функции создается хранилище для локальных переменных и выполняются локальные инициализации. Управление передается первому оператору в составном выражении *compound-statement*. Выполнение будет продолжаться до тех пор, пока не будет выполнен оператор **return** или не достигнут конец тела функции. Затем управление возвращается в точку, из которой вызвана функция.

Если функция должна вернуть значение, должен быть выполнен оператор **return**, который содержит выражение. Если оператор **return** не выполнен или если оператор **return** не содержит выражение, возвращаемое значение функции не будет определено.

## <a name="see-also"></a>См. также:

[Определения функций в C](../c-language/c-function-definitions.md)
