---
title: Постоянные выражения в C
ms.date: 06/14/2018
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
ms.openlocfilehash: f6984c47ef8acde462a8e92e01b72ef26a61eddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490536"
---
# <a name="c-constant-expressions"></a>Постоянные выражения в C

Константное выражение вычисляется во время компиляции, а не во время выполнения, и может использоваться в любом месте, в котором возможно использование константы. При вычислении константного выражения должна получаться константа со значением в диапазоне представимых значений для этого типа. Операнды константного выражения могут быть целыми константами, символьными константами, константами с плавающей запятой, константами перечисления, приведениями типов, выражениями **sizeof** и другими константными выражениями.

## <a name="syntax"></a>Синтаксис

*constant-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*conditional-expression*

*conditional-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-OR-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*logical-OR-expression* **?** *expression* **:** *conditional-expression*

*expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*assignment-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*expression* **,** *assignment-expression*

*assignment-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*conditional-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*unary-expression* *assignment-operator* *assignment-expression*

*assignment-operator*: один из следующих операторов:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**=** **&#42;=** **/=** **%=** **+=** **-=** **\<\<=** **>>=** **&=** **^=** **&#124;=**

Нетерминальные слова для декларатора структуры, перечислителя, прямого декларатора, прямого абстрактного декларатора и оператора с меткой содержат нетерминальное *константное выражение*.

Для определения размера члена битового поля структуры, значения константы перечисления, размера массива или значения константы **case** должно использоваться целочисленное константное выражение.

На константные выражения, используемые в директивах препроцессора, накладываются дополнительные ограничения. Поэтому они называются "ограниченными константными выражениями". Ограниченное константное выражение не может содержать выражения **sizeof**, константы перечисления, приведения типов к любому типу или константы типа с плавающей запятой. Но оно тоже может содержать специальное константное выражение **defined (** _identifier_ **)**.

## <a name="see-also"></a>См. также

- [Операнды и выражения](../c-language/operands-and-expressions.md)
