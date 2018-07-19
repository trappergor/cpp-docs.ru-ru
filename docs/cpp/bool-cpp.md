---
title: bool (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3bd43c9ceb4f0a0f73b86e3a4ecf4d851d504b3
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939316"
---
# <a name="bool-c"></a>bool (C++)

Это ключевое слово является встроенным типом. Переменная этого типа может принимать значения [true](../cpp/true-cpp.md) и [false](../cpp/false-cpp.md). Условные выражения имеют тип **bool** и поэтому имеют значения типа **bool**. Например `i!=0` теперь имеет значение TRUE или FALSE в зависимости от значения `i`.  

**Visual Studio 2017 версии 15.3 и более поздние версии** (состав [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): операнд постфиксный или префиксный инкремента или декремента не может быть типа **bool**. Другими словами, заданной переменной `b` типа **bool**, больше не допускаются следующие выражения:

```cpp
    b++;
    ++b;
    b--;
    --b;
```
  
Значения TRUE и FALSE имеют следующие связи:  
  
```cpp  
!false == true  
!true == false  
```  
  
В следующем операторе  
  
```cpp  
if (condexpr1) statement1;   
```  
  
Если `condexpr1` имеет значение TRUE, `statement1` выполняется всегда; Если `condexpr1` имеет значение FALSE, `statement1` никогда не выполняется.  
  
Если постфиксный или префиксный **++** оператор применяется к переменной типа **bool**, переменная имеет значение TRUE. 
**Visual Studio 2017 версии 15.3 и более поздние версии**: operator ++ для **bool** было удалено из языка и больше не поддерживается.

Постфиксный или префиксный **--** оператор не может применяться к переменной этого типа.  
  
 **Bool** тип участвует в восходящее приведение целочисленных типов. R-значение типа **bool** может быть преобразован в правостороннего значения типа **int**, с FALSE стать нуль и TRUE единицей. В качестве уникального типа **bool** участвует в разрешении перегрузки.  
  
## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Фундаментальные типы](../cpp/fundamental-types-cpp.md)<br/>
