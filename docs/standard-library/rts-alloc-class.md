---
title: "Класс rts_alloc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::rts_alloc
- allocators/stdext::rts_alloc
- rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
dev_langs:
- C++
helpviewer_keywords:
- rts_alloc class
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: fe127f896fa902f4a8cdb44454cf6e4c5f449e79
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="rtsalloc-class"></a>Класс rts_alloc
Класс шаблона rts_alloc описывает [фильтр](../standard-library/allocators-header.md), содержащий массив экземпляров кэша, и определяет, какой экземпляр нужно использовать для выделения и освобождения во время выполнения, а не во время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Cache>  
class rts_alloc
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Cache`|Тип экземпляров кэша, содержащихся в массиве. Возможные типы: [Класс cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## <a name="remarks"></a>Примечания  
 Этот класс шаблона содержит несколько экземпляров распределителей блоков и определяет, какой экземпляр нужно использовать для выделения и освобождения во время выполнения, а не во время компиляции. Он используется с компиляторами, которые не могут скомпилировать повторную привязку.  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[allocate](#allocate)|Выделяет блок памяти.|  
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
|[equals](#equals)|Сравнивает два кэша на равенство.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="allocate"></a>  rts_alloc::allocate  
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
 Функция-член возвращает `caches[_IDX].allocate(count)`, где индекс `_IDX` определяется запрошенным размером блока `count` или возвращает `operator new(count)`, если `count` слишком большой. `cache`, представляющий объект кэша.  
  
##  <a name="deallocate"></a>  rts_alloc::deallocate  
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
 Функция-член вызывает `caches[_IDX].deallocate(ptr, count)`, где индекс `_IDX` определяется запрошенным размером блока `count` или возвращает `operator delete(ptr)`, если `count` слишком большой.  
  
##  <a name="equals"></a>  rts_alloc::equals  
 Сравнивает два кэша на равенство.  
  
```
bool equals(const sync<_Cache>& _Other) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Cache`|Объект кэша, связанный с фильтром.|  
|`_Other`|Объект кэша для сравнения на равенство.|  
  
### <a name="remarks"></a>Примечания  
 Значение `true`, если результат `caches[0].equals(other.caches[0])`; в противном случае — значение `false`. `caches` представляет массив объектов кэша.  
  
## <a name="see-also"></a>См. также  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)   
 [\<allocators>](../standard-library/allocators-header.md)




