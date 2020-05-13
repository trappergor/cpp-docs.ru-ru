---
title: Операторы назначения в C
ms.date: 06/14/2018
helpviewer_keywords:
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
ms.openlocfilehash: e8ada96daaec249a05882aceae9b7d9e86b92065
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168803"
---
# <a name="c-assignment-operators"></a>Операторы назначения в C

Операция присваивания заключается в том, что значение правого операнда присваивается месту хранения, имя которого обозначено левым операндом. Поэтому левый операнд в операции присваивания должен иметь изменяемое l-значение. После того как присваивание выполнено, выражение присваивания имеет значение левого операнда, но не l-значение.

## <a name="syntax"></a>Синтаксис

*assignment-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*conditional-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;присваивания *унарного выражения* *—* *выражение назначения* оператора

*assignment-operator*: один из следующих операторов:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **=** **\*=** **/=** **%=** **+=** **-=** **\<\<=** **>>=** **&=** **^=** **|=**

Операторы присваивания в языке C позволяют в ходе одной операции выполнить и преобразование, и присваивание значения. В языке C имеются следующие операторы присваивания:

|Оператор|Выполняемая операция|
|--------------|-------------------------|
|**=**|Простое присваивание|
|**&#42;=**|Присваивание умножения|
|**/=**|Присваивание деления|
|**%=**|Присваивание остатка|
|**+=**|Присваивание сложения|
|**-=**|Присваивание вычитания|
|**<\<=**|Присваивание сдвига влево|
|**>>=**|Присваивание сдвига вправо|
|**&=**|Присваивание побитового И|
|**^=**|Присваивание побитового исключающего ИЛИ|
|**&#124;=**|Присваивание побитового включающего ИЛИ|

В ходе присваивания тип значения в правой части преобразуется в тип значения в левой части, а после выполнения операции значение сохраняется в левом операнде. Левый операнд не должен быть массивом, функцией или константой. Путь преобразования, который зависит от двух типов, подробнее описывается в разделе [Преобразования типов](../c-language/type-conversions-c.md).

## <a name="see-also"></a>См. также раздел

- [Операторы присваивания](../cpp/assignment-operators.md)
