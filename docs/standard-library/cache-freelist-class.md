---
title: "Класс cache_freelist | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_freelist
- stdext::cache_freelist
- cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- cache_freelist class
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 7d15c40a0116e8d6de2346a7da74045c2a7ee795
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="cachefreelist-class"></a>Класс cache_freelist
Задает [распределитель блоков](../standard-library/allocators-header.md), который выделяет и освобождает блоки памяти одного размера.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <std::size_t Sz, class Max>  
class cache_freelist
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Sz`|Число элементов в массиве, которые нужно выделить.|  
|`Max`|Класс max, представляющий максимальный размер списка свободных блоков. Это может быть класс [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md) или [max_variable_size](../standard-library/max-variable-size-class.md).|  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона cache_freelist ведет список свободных блоков памяти размером `Sz`. При заполнении списка свободных блоков он использует `operator delete` для освобождения блоков памяти. Когда список свободных блоков пустой, он использует `operator new` для выделения новых блоков памяти. Максимальный размер списка свободных блоков определяется классом max, переданным в параметре `Max`.  
  
 Каждый блок памяти содержит `Sz` байт свободной памяти и данных, которые требуются `operator new` и `operator delete`.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[cache_freelist](#cache_freelist)|Создает объект типа `cache_freelist`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[allocate](#allocate)|Выделяет блок памяти.|  
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="allocate"></a>  cache_freelist::allocate  
 Выделяет блок памяти.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`count`|Число элементов в массиве, которые нужно выделить.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на выделяемый объект.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="cache_freelist"></a>  cache_freelist::cache_freelist  
 Создает объект типа `cache_freelist`.  
  
```
cache_freelist();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="deallocate"></a>  cache_freelist::deallocate  
 Освобождает указанное число объектов из памяти, начиная с заданной позиции.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`ptr`|Указатель на первый объект, который необходимо освободить из хранилища.|  
|`count`|Количество объектов для освобождения из хранилища.|  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)




