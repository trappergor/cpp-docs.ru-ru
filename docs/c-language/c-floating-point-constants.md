---
title: "Константы с плавающей запятой в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- types [C], constants
- floating-point numbers, floating-point constants
- constants, floating-point
- floating-point constants
- floating-point constants, about floating-point constants
- double data type, floating-point constants
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7bd4bd3e0dc2dcd1388c7e8db5c9fcf209a9b47c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="c-floating-point-constants"></a>Константы с плавающей запятой в C
"Константа с плавающей запятой — это десятичное число, которое представляет знаковое вещественное число. Представление знакового вещественного числа включает в себя целочисленную часть, дробную часть и экспоненту. Константы с плавающей запятой служат для представления значений с плавающей запятой, которые не могут быть изменены.  
  
## <a name="syntax"></a>Синтаксис  
 *floating-point-constant*:  
 &nbsp;&nbsp; *fractional-constant exponent-part*<sub>opt</sub> *floating-suffix*<sub>opt</sub>  
 &nbsp;&nbsp; *digit-sequence exponent-part floating-suffix*<sub>opt</sub>  
  
 *fractional-constant*:  
 &nbsp;&nbsp; *digit-sequence*<sub>opt</sub> **.** *digit-sequence*  
 &nbsp;&nbsp; *digit-sequence*  **.**  
  
 *exponent-part*:  
 &nbsp;&nbsp; **e**  *sign*<sub>opt</sub> *digit-sequence*  
 &nbsp;&nbsp; **E**  *sign*<sub>opt</sub> *digit-sequence*  
  
 *sign* : один из указанных ниже знаков  
 &nbsp;&nbsp; **+ -**  
  
 *digit-sequence*:  
 &nbsp;&nbsp; *digit*  
 &nbsp;&nbsp; *digit-sequence digit*  
  
 *floating-suffix* : одно из указанных ниже значений  
 &nbsp;&nbsp; **f l F L**  
  
 Можно опустить либо цифры перед десятичной запятой (целочисленная часть значения), либо цифры после десятичной запятой (дробная часть), но не и то и другое. Если включается только экспонента, десятичную запятую можно опустить. Пробельные символы между цифрами или символами константы не допускаются.  
  
 В следующих примерах показаны некоторые формы констант и выражений с плавающей запятой.  
  
```  
15.75  
1.575E1   /* = 15.75   */  
1575e-2   /* = 15.75   */  
-2.5e-3   /* = -0.0025 */  
25E-4     /* =  0.0025 */  
```  
  
 Константы с плавающей запятой имеют положительное значение, если перед ними не стоит знак "минус" (**-**). А этом случае знак "минус" интерпретируется как унарный арифметический оператор изменения знака. Константы с плавающей запятой относятся к типу `float`, `double` или `long double`.  
  
 Константы с плавающей запятой без суффикса **f**, **F**, **l** или **L** относятся к типу `double`. Если суффикс представлен буквой **f** или **F**, константа относится к типу `float`. Если суффикс представлен буквой **l** или **L**, константа относится к типу `long double`. Пример:  
  
```  
100L  /* Has type long double  */  
100F  /* Has type float        */  
```  
  
 Обратите внимание, что компилятор Майкрософт для C внутренне представляет `long double` так же, как и тип `double`. Дополнительные сведения о типах `double`, `float` и `long double` см. в статье [Storage of Basic Types](../c-language/storage-of-basic-types.md) (Хранилище базовых типов).  
  
 Целочисленную часть константы с плавающей запятой можно опустить, как показано в следующих примерах. Число .75 можно выразить несколькими способами, включая следующие:  
  
```  
.0075e2  
0.075e1  
.075e1  
75e-2  
```  
  
## <a name="see-also"></a>См. также  
 [Константы в C](../c-language/c-constants.md)