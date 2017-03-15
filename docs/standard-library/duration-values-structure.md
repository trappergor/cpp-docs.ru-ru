---
title: "Структура duration_values | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration_values
dev_langs:
- C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8b0c02d4edc3a460f166cb65b312ef78337d403f
ms.lasthandoff: 02/24/2017

---
# <a name="durationvalues-structure"></a>Структура duration_values
Предоставляет конкретные значения для параметра-шаблона [длительности](../standard-library/duration-class.md) `Rep`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Rep>  
struct duration_values;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[duration_values::max](#duration_values__max_method)|Статический. Указывает верхний предел для значения типа `Rep`.|  
|[duration_values::min](#duration_values__min_method)|Статический. Указывает нижний предел для значения типа `Rep`.|  
|[duration_values::zero](#duration_values__zero_method)|Статический. Возвращает `Rep(0)`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** chrono  
  
 **Пространство имен:** std::chrono  
  
##  <a name="a-namedurationvaluesmaxmethoda--durationvaluesmax"></a><a name="duration_values__max_method"></a>  duration_values::max  
 Статический метод, который возвращает верхнюю границу значений типа `Ref`.  
  
```  
static constexpr Rep max();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Фактически возвращает `numeric_limits<Rep>::max()`.  
  
### <a name="remarks"></a>Примечания  
 Если `Rep` является пользовательским типом, возвращаемое значение должно быть больше [duration_values::zero](#duration_values__zero_method).  
  
##  <a name="a-namedurationvaluesminmethoda--durationvaluesmin"></a><a name="duration_values__min_method"></a>  duration_values::min  
 Статический метод, который возвращает нижнюю границу для значений типа `Ref`.  
  
```  
static constexpr Rep min();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Фактически возвращает `numeric_limits<Rep>::lowest()`.  
  
### <a name="remarks"></a>Примечания  
 Если `Rep` является пользовательским типом, возвращаемое значение должно быть меньше или равно [duration_values::zero](#duration_values__zero_method).  
  
##  <a name="a-namedurationvalueszeromethoda--durationvalueszero"></a><a name="duration_values__zero_method"></a>  duration_values::zero  
 Возвращает `Rep(0)`.  
  
```  
static constexpr Rep zero();
```  
  
### <a name="remarks"></a>Примечания  
 Если `Rep` является пользовательским типом, возвращаемое значение должно представлять аддитивную бесконечность.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


