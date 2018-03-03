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
- __BOOL_DEFINED
dev_langs:
- C++
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 564d2f4849d1725d46d92562e2ce75b2ea2e2d44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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