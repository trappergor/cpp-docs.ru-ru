---
title: "Постоянные выражения в C | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0e3323c85ce7668adfe5b4a297ac8bab930c3ae6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

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
