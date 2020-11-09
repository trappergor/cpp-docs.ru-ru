---
title: Операторы назначения в C
description: Стандартные операторы присваивания языка C, их синтаксис и значение.
ms.date: 10/30/2020
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
ms.openlocfilehash: 460e18772689de0d28fcfda3295a49b2f8a3c0d7
ms.sourcegitcommit: 4abc6c4c9694f91685cfd77940987e29a51e3143
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93238516"
---
# <a name="c-assignment-operators"></a>Операторы назначения в C

Операция присваивания заключается в том, что значение правого операнда присваивается месту хранения, имя которого обозначено левым операндом. Поэтому левый операнд в операции присваивания должен иметь изменяемое l-значение. После того как присваивание выполнено, выражение присваивания имеет значение левого операнда, но не l-значение.

## <a name="syntax"></a>Синтаксис

*`assignment-expression`* :\
&emsp;*`conditional-expression`*\
&emsp;*`unary-expression`* *`assignment-operator`* *`assignment-expression`*

*`assignment-operator`* : один из<br/>
&emsp;**`=`** **`*=`** **`/=`** **`%=`** **`+=`** **`-=`** **`<<=`** **`>>=`** **`&=`** **`^=`** **`|=`**

Операторы присваивания в языке C позволяют в ходе одной операции выполнить и преобразование, и присваивание значения. В языке C имеются следующие операторы присваивания:

|Оператор|Выполняемая операция|
|--------------|-------------------------|
|**`=`**|Простое присваивание|
|**`*=`**|Присваивание умножения|
|**`/=`**|Присваивание деления|
|**`%=`**|Присваивание остатка|
|**`+=`**|Присваивание сложения|
|**`-=`**|Присваивание вычитания|
|**`<<=`**|Присваивание сдвига влево|
|**`>>=`**|Присваивание сдвига вправо|
|**`&=`**|Присваивание побитового И|
|**`^=`**|Присваивание побитового исключающего ИЛИ|
|**`|=`**|Присваивание побитового включающего ИЛИ|

В ходе присваивания тип значения в правой части преобразуется в тип значения в левой части, а после выполнения операции значение сохраняется в левом операнде. Левый операнд не должен быть массивом, функцией или константой. Путь преобразования, который зависит от двух типов, подробнее описывается в разделе [Преобразования типов](../c-language/type-conversions-c.md).

## <a name="see-also"></a>См. также

- [Операторы присваивания](../cpp/assignment-operators.md)
