---
title: "Члены структур и объединений | Документы Майкрософт"
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
- member-selection operators
- structure members, referencing
- -> operator, structure and union members
- dot operator (.)
- referencing structure members
- . operator
- operators [C], member selection
- structure member selection
ms.assetid: bb1fe304-af49-4f98-808d-afdc99b3e319
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
ms.openlocfilehash: 31118df209db98435a3b9cfb0c38e17dbd818d01
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="structure-and-union-members"></a>Члены структур и объединений
Выражение выбора члена ссылается на члены структур и объединений. Такое выражение имеет значение и тип выбранного члена.  
  
```  
  
postfix-expression  
.  
identifier  
postfix-expression  
->  
identifier  
  
```  
  
 В следующем списке приводится описание двух форм выражений выбора члена.  
  
1.  В первой форме *postfix-expression* представляет значение типа `struct` или **union**, а *identifier* именует член указанной структуры или объединения. Значение операции совпадает с *identifier* и является l-значением, если *postfix-expression* является l-значением. Дополнительные сведения см. в разделе [Выражения l-значений и r-значений](../c-language/l-value-and-r-value-expressions.md).  
  
2.  Во второй форме *postfix-expression* представляет указатель на структуру или объединение, а *identifier* именует член указанной структуры или объединения. Это значение совпадает с *identifier* и является l-значением.  
  
 Две формы выражений выбора члена оказывают аналогичное влияние.  
  
 Фактически выражение, включающее оператор выбора члена (**->**), — это сокращенная версия выражения, использующего точку (**.**), если выражение перед точкой включает оператор косвенного обращения (**\***), примененный к значению указателя. Поэтому  
  
```  
  
expression  
->  
identifier  
  
```  
  
 эквивалентно  
  
```  
  
(*  
expression  
) .  
identifier  
  
```  
  
 если *expression* — значение указателя.  
  
## <a name="examples"></a>Примеры  
 Данное объявление структуры представлено в следующих примерах. Дополнительные сведения об операторе косвенного обращения (**\***), используемом в этих примерах, см. в разделе [Операторы косвенного обращения и определения адреса](../c-language/indirection-and-address-of-operators.md).  
  
```  
struct pair   
{  
    int a;  
    int b;  
    struct pair *sp;  
} item, list[10];  
```  
  
 Выражение выбора члена для структуры `item` выглядит следующим образом.  
  
```  
item.sp = &item;  
```  
  
 В приведенном выше примере адрес структуры `item` присваивается члену `sp` структуры. Это означает, что `item` содержит указатель на себя.  
  
```  
(item.sp)->a = 24;  
```  
  
 В этом примере выражение указателя `item.sp` используется с оператором выбора члена (**->**) для присвоения значения члену `a`.  
  
```  
list[8].b = 12;  
```  
  
 На примере этого оператора показано, как выбрать отдельный член структуры из массива структур.  
  
## <a name="see-also"></a>См. также  
 [Операторы для доступа к членам: . и ->](../cpp/member-access-operators-dot-and.md)
