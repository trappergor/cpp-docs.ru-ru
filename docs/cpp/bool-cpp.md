---
title: "bool (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bool_cpp
- bool
- __BOOL_DEFINED
dev_langs:
- C++
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: 9
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: f2437d831ae155f916b69cc6b35d3b586be9819e
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="bool-c"></a>bool (C++)
Это ключевое слово является встроенным типом. Переменная этого типа может принимать значения [true](../cpp/true-cpp.md) и [false](../cpp/false-cpp.md). Условные выражения имеют тип `bool`, и поэтому имеют значения типа `bool`. Например `i!=0` теперь имеет **true** или **false** в зависимости от значения `i`.  

**Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): операнд постфиксный или префиксный инкремента или декремента не может быть типа `bool`. 
  
 Значения **true** и **false** находятся в следующих отношениях:  
  
```  
!false == true  
!true == false  
```  
  
 В следующем операторе  
  
```  
if (condexpr1) statement1;   
```  
  
 Если `condexpr1` — **true**, `statement1` выполняется всегда; Если `condexpr1` — **false**, `statement1` никогда не выполняется.  
  
 Если постфиксный или префиксный `++` оператор применяется к переменной типа `bool`, переменной присваивается **true**. 
**Visual Studio 2017 г 15,3 и более поздних версий**: operator ++ для bool был удален из языка и больше не поддерживается.

Постфиксный или префиксный оператор `--` невозможно применить к переменной этого типа.  
  
 Тип `bool` участвует в восходящем приведении целого типа. R-значение типа `bool` можно преобразовать в r-значение типа `int`, с **false** становится нулем и **true** — единицей. Как отдельный тип `bool` участвует в разрешении перегрузки.  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Базовые типы](../cpp/fundamental-types-cpp.md)
