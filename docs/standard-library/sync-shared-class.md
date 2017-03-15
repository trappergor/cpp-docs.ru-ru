---
title: "Класс sync_shared | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sync_shared
- allocators/stdext::sync_shared
- stdext.sync_shared
- stdext::sync_shared
dev_langs:
- C++
helpviewer_keywords:
- sync_shared class
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b510fbe0b93f97222a093007300a3b3d054d1505
ms.lasthandoff: 02/24/2017

---
# <a name="syncshared-class"></a>Класс sync_shared
Описывает [фильтр синхронизации](../standard-library/allocators-header.md), использующий мьютекс для управления доступом к объекту кэша, который является общим для всех распределителей.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Cache>  
class sync_shared
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Cache`|Тип кэша, связанный с фильтром синхронизации. Возможные типы: [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[allocate](#sync_shared__allocate)|Выделяет блок памяти.|  
|[deallocate](#sync_shared__deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
|[equals](#sync_shared__equals)|Сравнивает два кэша на равенство.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="a-namesyncsharedallocatea--syncsharedallocate"></a><a name="sync_shared__allocate"></a>  sync_shared::allocate  
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
 Функция-член блокирует мьютекс, вызывает метод `cache.allocate(count)`, разблокирует мьютекс и возвращает результат более раннего вызова `cache.allocate(count)`. `cache` представляет текущий объект кэша.  
  
##  <a name="a-namesyncshareddeallocatea--syncshareddeallocate"></a><a name="sync_shared__deallocate"></a>  sync_shared::deallocate  
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
 Эта функция-член блокирует мьютекс, вызывает метод `cache.deallocate(ptr, count)`, где `cache` представляет объект кэша, а затем разблокирует мьютекс.  
  
##  <a name="a-namesyncsharedequalsa--syncsharedequals"></a><a name="sync_shared__equals"></a>  sync_shared::equals  
 Сравнивает два кэша на равенство.  
  
```
bool equals(const sync_shared<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Cache`|Тип кэша, связанный с фильтром синхронизации.|  
|`Other`|Кэш для сравнения на равенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true` если результат `cache.equals(Other.cache)`, где `cache` представляет объект кэша, равен `true`; в противном случае — значение `false`.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)




