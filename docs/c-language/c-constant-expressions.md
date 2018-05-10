---
title: Постоянные выражения в C | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aaeb7ab79777d247f0bc0b2e6d749d8df5a7f8e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="c-constant-expressions"></a>Постоянные выражения в C
Константное выражение вычисляется во время компиляции, а не во время выполнения, и может использоваться в любом месте, в котором возможно использование константы. При вычислении константного выражения должна получаться константа со значением в диапазоне представимых значений для этого типа. Операнды константного выражения могут быть целыми константами, символьными константами, константами с плавающей запятой, константами перечисления, приведениями типов, выражениями `sizeof` и другими константными выражениями.  
  
## <a name="syntax"></a>Синтаксис  
 *constant-expression*:  
 *conditional-expression*  
  
 *conditional-expression*:  
 *logical-OR-expression*  
  
 *logical-OR-expression* **?**  *expression* **:**  *conditional-expression*  
  
 *expression*:  
 *assignment-expression*  
  
 *expression* **,**  *assignment-expression*  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: один из следующих операторов:  
 **= \*= /= %= += -= <\<= >>= &= ^= &#124;=**  
  
 Нетерминальные слова для декларатора структуры, перечислителя, прямого декларатора, прямого абстрактного декларатора и оператора с меткой содержат нетерминальное *константное выражение*.  
  
 Для определения размера члена битового поля структуры, значения константы перечисления, размера массива или значения константы **case** должно использоваться целочисленное константное выражение.  
  
 На константные выражения, используемые в директивах препроцессора, накладываются дополнительные ограничения. Поэтому они называются "ограниченными константными выражениями". Ограниченное константное выражение не может содержать выражения `sizeof`, константы перечисления, приведения типов к любому типу или константы типа с плавающей запятой. Но оно может содержать специальное константное выражение `defined (`*identifier*`)`.  
  
## <a name="see-also"></a>См. также  
 [Операнды и выражения](../c-language/operands-and-expressions.md)