---
title: "Целые константы в C | Документация Майкрософт"
ms.custom: 
ms.date: 02/01/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c23e90d235e1ad2a8cca577c5cfbf2be55b52b6
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
# <a name="c-integer-constants"></a>Целочисленные константы в C

"Целая константа" является десятичным (основание 10), восьмеричным (основание 8) или шестнадцатеричным (основание 16) числом, представляющим целое значение. Целые константы служат для представления целых значений, которые не могут быть изменены.

## <a name="syntax"></a>Синтаксис

*integer-constant*:  
&nbsp;&nbsp;*decimal-constant* *integer-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*octal-constant* *integer-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*hexadecimal-constant* *integer-suffix*<sub>opt</sub>  

*decimal-constant*:  
&nbsp;&nbsp;*nonzero-digit*  
&nbsp;&nbsp;*decimal-constant* *digit*  

*octal-constant*:  
&nbsp;&nbsp;**0**  
&nbsp;&nbsp;*octal-constant* *octal-digit*  

*hexadecimal-constant*:  
&nbsp;&nbsp;**0x**  *hexadecimal-digit*  
&nbsp;&nbsp;**0X**  *hexadecimal-digit*  
&nbsp;&nbsp;*hexadecimal-constant* *hexadecimal-digit*  

*nonzero-digit*: одна из указанных ниже  
&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**  

*octal-digit*: одна из указанных ниже  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7**  

*hexadecimal-digit*: одна из указанных ниже  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**  
&nbsp;&nbsp;**a b c d e f**  
&nbsp;&nbsp;**A B C D E F**  
  
*integer-suffix*:  
&nbsp;&nbsp;*unsigned-suffix* *long-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*long-suffix* *unsigned-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*unsigned-suffix* *64-bit-integer-suffix*<sub>opt</sub>

*unsigned-suffix*: one of  
&nbsp;&nbsp;**u U**  

*long-suffix*: one of  
&nbsp;&nbsp;**l L**  
  
*64-bit-integer-suffix*: один из &nbsp;&nbsp;**i64 I64**  

Целые константы имеют положительное значение, если перед ними не указан знак "минус" (**-**). Знак "минус" интерпретируется как унарный арифметический оператор изменения знака. (Сведения об этом операторе см. в статье [Unary Arithmetic Operators](../c-language/unary-arithmetic-operators.md) (Унарные арифметические операторы).

Если целая константа начинается с символов **0x** или **0X**, она является шестнадцатеричной. Если константа начинается с цифры **0**, она восьмеричная. В противном случае считается, что она десятичная.

Следующие строки эквивалентны:

```C
0x1C   /* = Hexadecimal representation for decimal 28 */
034    /* = Octal representation for decimal 28 */
```

Пробельные символы между цифрами целой константы не допускаются. В следующих примерах показаны допустимые десятичные, восьмеричные и шестнадцатеричные константы.

```C
/* Decimal Constants */
10
132
32179

/* Octal Constants */
012
0204
076663

/* Hexadecimal Constants */
0xa or 0xA
0x84
0x7dB3 or 0X7DB3
```

## <a name="see-also"></a>См. также

[Константы в C](../c-language/c-constants.md)  
