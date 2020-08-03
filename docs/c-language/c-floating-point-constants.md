---
title: Константы с плавающей запятой в C
ms.date: 11/04/2016
helpviewer_keywords:
- types [C], constants
- floating-point numbers, floating-point constants
- constants, floating-point
- floating-point constants
- floating-point constants, about floating-point constants
- double data type, floating-point constants
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
ms.openlocfilehash: 8777f04b047516ef29ae7bf67ddaf4195e3aaf6e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228028"
---
# <a name="c-floating-point-constants"></a>Константы с плавающей запятой в C

"Константа с плавающей запятой — это десятичное число, которое представляет знаковое вещественное число. Представление знакового вещественного числа включает в себя целочисленную часть, дробную часть и экспоненту. Константы с плавающей запятой служат для представления значений с плавающей запятой, которые не могут быть изменены.

## <a name="syntax"></a>Синтаксис

*floating-point-constant*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*fractional-constant* *exponent-part*<sub>opt</sub> *floating-suffix*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *exponent-part* *floating-suffix*<sub>opt</sub>

*fractional-constant*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence*<sub>opt</sub> **.** *digit-sequence*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence*  **.**

*exponent-part*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**e** *sign*<sub>opt</sub> *digit-sequence*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**E** *sign*<sub>opt</sub> *digit-sequence*

*sign*: один из указанных ниже знаков<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **+ -**

*digit-sequence*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit-sequence* *digit*

*floating-suffix*: один из указанных ниже знаков<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**f l F L**

Можно опустить либо цифры перед десятичной запятой (целочисленная часть значения), либо цифры после десятичной запятой (дробная часть), но не и то и другое. Если включается только экспонента, десятичную запятую можно опустить. Пробельные символы между цифрами или символами константы не допускаются.

В следующих примерах показаны некоторые формы констант и выражений с плавающей запятой.

```C
15.75
1.575E1   /* = 15.75   */
1575e-2   /* = 15.75   */
-2.5e-3   /* = -0.0025 */
25E-4     /* =  0.0025 */
```

Константы с плавающей запятой имеют положительное значение, если перед ними не стоит знак "минус" ( **-** ). А этом случае знак "минус" интерпретируется как унарный арифметический оператор изменения знака. Константы с плавающей запятой относятся к типу **`float`** , **`double`** или **`long double`** .

Константы с плавающей запятой без суффикса **f**, **F**, **l** или **L** относятся к типу **`double`** . Если суффикс представлен буквой **f** или **F**, константа относится к типу **`float`** . Если суффикс представлен буквой **l** или **L**, константа относится к типу **`long double`** . Пример:

```C
10.0L  /* Has type long double  */
10.0F  /* Has type float        */
```

Обратите внимание, что компилятор Майкрософт для C внутренне представляет **`long double`** так же, как и тип **`double`** . Дополнительные сведения о типах **`double`** , **`float`** и **`long double`** см. в статье [Хранилище базовых типов](../c-language/storage-of-basic-types.md).

Целочисленную часть константы с плавающей запятой можно опустить, как показано в следующих примерах. Число .75 можно выразить несколькими способами, включая следующие:

```C
.0075e2
0.075e1
.075e1
75e-2
```

## <a name="see-also"></a>См. также

[Константы в C](../c-language/c-constants.md)
