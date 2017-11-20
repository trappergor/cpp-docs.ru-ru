---
title: "Целые константы в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 20025ae47491084436864481357125e741ccc486
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="c-integer-constants"></a>Целочисленные константы в C
"Целая константа" является десятичным (основание 10), восьмеричным (основание 8) или шестнадцатеричным (основание 16) числом, представляющим целое значение. Целые константы служат для представления целых значений, которые не могут быть изменены.  
  
## <a name="syntax"></a>Синтаксис  
 *integer-constant*:  
 *decimal-constant integer-suffix* opt  
  
 *octal-constant integer-suffix* opt  
  
 *hexadecimal-constant integer-suffix* opt  
  
 *decimal-constant*:  
 *nonzero-digit*  
  
 *decimal-constant digit*  
  
 *octal-constant*:  
 **0**  
  
 *octal-constant octal-digit*  
  
 *hexadecimal-constant*:  
 **0x**  *hexadecimal-digit*  
  
 **0X**  *hexadecimal-digit*  
  
 *hexadecimal-constant hexadecimal-digit*  
  
 *nonzero-digit*: одна из указанных ниже  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal-digit*: одна из указанных ниже  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal-digit*: одна из указанных ниже  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *integer-suffix*:  
 *unsigned-suffix long-suffix* opt  
  
 *long-suffix unsigned-suffix* opt  
  
 *unsigned-suffix*: one of  
 **u U**  
  
 *long-suffix*: one of  
 **l L**  
  
 *64-bit integer-suffix*:  
 **i64**  
  
 Целые константы имеют положительное значение, если перед ними не указан знак "минус" (**-**). Знак "минус" интерпретируется как унарный арифметический оператор изменения знака. (Сведения об этом операторе см. в статье [Unary Arithmetic Operators](../c-language/unary-arithmetic-operators.md) (Унарные арифметические операторы).  
  
 Если целая константа начинается с символов **0x** или **0X**, она является шестнадцатеричной. Если константа начинается с цифры **0**, она восьмеричная. В противном случае считается, что она десятичная.  
  
 Следующие строки эквивалентны:  
  
```  
0x1C   /* = Hexadecimal representation for decimal 28 */  
034    /* = Octal representation for decimal 28 */  
```  
  
 Пробельные символы между цифрами целой константы не допускаются. В следующих примерах показаны допустимые десятичные, восьмеричные и шестнадцатеричные константы.  
  
```  
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