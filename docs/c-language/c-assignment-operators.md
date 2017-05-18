---
title: "Операторы присваивания в C | Документы Майкрософт"
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
caps.latest.revision: 8
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
ms.openlocfilehash: 0e65a64dffc4a9c03f2075bcd9eee87b18ad2e77
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="c-assignment-operators"></a>Операторы назначения в C
Операция присваивания заключается в том, что значение правого операнда присваивается месту хранения, имя которого обозначено левым операндом. Поэтому левый операнд в операции присваивания должен иметь изменяемое l-значение. После того как присваивание выполнено, выражение присваивания имеет значение левого операнда, но не l-значение.  
  
 **Синтаксис**  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: один из следующих операторов:  
 **= \*=** `/=` `%=` `+=` **-= <\<= >>= &=** `^=` `|=`  
  
 Операторы присваивания в языке C позволяют в ходе одной операции выполнить и преобразование, и присваивание значения. В языке C имеются следующие операторы присваивания:  
  
|Оператор|Выполняемая операция|  
|--------------|-------------------------|  
|**=**|Простое присваивание|  
|**\*=**|Присваивание умножения|  
|`/=`|Присваивание деления|  
|`%=`|Присваивание остатка|  
|`+=`|Присваивание сложения|  
|**-=**|Присваивание вычитания|  
|**<\<=**|Присваивание сдвига влево|  
|**>>=**|Присваивание сдвига вправо|  
|**&=**|Присваивание побитового И|  
|`^=`|Присваивание побитового исключающего ИЛИ|  
|`&#124;=`|Присваивание побитового включающего ИЛИ|  
  
 В ходе присваивания тип значения в правой части преобразуется в тип значения в левой части, а после выполнения операции значение сохраняется в левом операнде. Левый операнд не должен быть массивом, функцией или константой. Путь преобразования, который зависит от двух типов, подробнее описывается в разделе [Преобразования типов](../c-language/type-conversions-c.md).  
  
## <a name="see-also"></a>См. также  
 [Операторы присваивания](../cpp/assignment-operators.md)
