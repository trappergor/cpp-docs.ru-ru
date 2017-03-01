---
title: "Структура atomic_flag | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- atomic/std::atomic_flag
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
caps.latest.revision: 14
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
ms.openlocfilehash: d51596a70b0b79d39fee3095fc2b28fdd7c697f3
ms.lasthandoff: 02/24/2017

---
# <a name="atomicflag-structure"></a>Структура atomic_flag
Описывает объект, который автоматически устанавливает и очищает флаг `bool`. Операции с атомарными флагами всегда неблокирующие.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct atomic_flag;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод atomic_flag::clear](#atomic_flag__clear_method)|Устанавливает сохраненный флаг в значение `false`.|  
|[Метод atomic_flag::test_and_set](#atomic_flag__test_and_set_method)|Устанавливает сохраненный флаг в значение `true` и возвращает начальное значение флага.|  
  
## <a name="remarks"></a>Примечания  
 Объекты `atomic_flag` могут передаваться в функции [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear_function), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit_function), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set_function) и [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit_function), которые не являются функциями-членами. Их можно инициализировать с помощью значения `ATOMIC_FLAG_INIT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atomic  
  
 **Пространство имен:** std  
  
##  <a name="a-nameatomicflagclearmethoda--atomicflagclear-method"></a><a name="atomic_flag__clear_method"></a>Метод atomic_flag::clear  
 Устанавливает флаг `bool`, хранящийся в объекте `*this``false` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="a-nameatomicflagtestandsetmethoda--atomicflagtestandset-method"></a><a name="atomic_flag__test_and_set_method"></a>Метод atomic_flag::test_and_set  
 Устанавливает флаг `bool`, хранящийся в объекте `*this``true` с соблюдением указанных ограничений [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Order`  
 Перечисление [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Начальное значение флага, который хранится в `*this`.  
  
## <a name="see-also"></a>См. также  
 [\<atomic>](../standard-library/atomic.md)




