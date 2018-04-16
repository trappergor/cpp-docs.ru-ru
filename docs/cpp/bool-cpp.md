---
title: bool (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d5a8a86cfcc64b70e4910079461513c34fc7d0d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2018
---
# <a name="bool-c"></a>bool (C++)

Это ключевое слово является встроенным типом. Переменная этого типа может принимать значения [true](../cpp/true-cpp.md) и [false](../cpp/false-cpp.md). Условные выражения имеют тип `bool`, и поэтому имеют значения типа `bool`. Например `i!=0` теперь имеет **true** или **false** в зависимости от значения `i`.  

**Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): операнд постфиксный или префиксный инкремента или декремента не может быть типа **bool**. Другими словами, заданной переменной **b** типа **bool**, больше не допускаются следующие выражения:

```cpp
    b++;
    ++b;
    b--;
    --b;
```
  
Значения **true** и **false** находятся в следующих отношениях:  
  
```cpp  
!false == true  
!true == false  
```  
  
В следующем операторе  
  
```cpp  
if (condexpr1) statement1;   
```  
  
Если `condexpr1` — **true**, `statement1` выполняется всегда; Если `condexpr1` — **false**, `statement1` никогда не выполняется.  
  
Если постфиксный или префиксный **++** оператор применяется к переменной типа **bool**, переменной присваивается **true**. 
**Visual Studio 2017 г 15,3 и более поздних версий**: operator ++ для **bool** был удален из языка и больше не поддерживается.

Постфиксный или префиксный **--** оператор не может применяться к переменной этого типа.  
  
 **Bool** тип участвует в восходящее приведение целочисленных типов. R-значение типа **bool** можно преобразовать в r-значение типа **int**, с **false** становится нулем и **true** — единицей. Как отдельный тип **bool** участвует в разрешении перегрузки.  
  
## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Фундаментальные типы](../cpp/fundamental-types-cpp.md)<br/>
