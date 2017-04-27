---
title: "Использование операторов сложения | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 7
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 04e23f9694193a05d48b7fcdff717d06e448e877
ms.lasthandoff: 04/01/2017

---
# <a name="using-the-additive-operators"></a>Использование операторов сложения
В следующих примерах, иллюстрирующих операторы сложения и вычитания, используются следующие объявления.  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 Эти операторы эквивалентны.  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 Значение `i` умножается на длину типа **float** и добавляется к `&x[4]`. Результирующее значение указателя является адресом `x[8]`.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 В этом примере адрес третьего элемента `x` (заданного `x[i-2]`) вычитается из адреса пятого элемента `x` (заданного `x[i]`). Разница делится на длину типа **float**; результатом является целочисленное значение 2.  
  
## <a name="see-also"></a>См. также  
 [Аддитивные операторы в C](../c-language/c-additive-operators.md)
