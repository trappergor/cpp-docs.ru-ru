---
title: "Класс sync_none | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
dev_langs: C++
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf0d71bc517e97a99db79dfc905935fba81faed0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="syncnone-class"></a>Класс sync_none
Описывает [фильтр синхронизации](../standard-library/allocators-header.md), который не предоставляет синхронизацию.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Cache>  
class sync_none
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`Cache`|Тип кэша, связанный с фильтром синхронизации. Возможные типы: [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[allocate](#allocate)|Выделяет блок памяти.|  
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
|[equals](#equals)|Сравнивает два кэша на равенство.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="allocate"></a>  sync_none::allocate  
 Выделяет блок памяти.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`count`|Число элементов в массиве, которые нужно выделить.|  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает `cache.allocate(count)`, где `cache` — объект кэша.  
  
##  <a name="deallocate"></a>  sync_none::deallocate  
 Освобождает указанное число объектов из памяти, начиная с заданной позиции.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`ptr`|Указатель на первый объект, который необходимо освободить из хранилища.|  
|`count`|Количество объектов для освобождения из хранилища.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывает `cache.deallocate(ptr, count)`, где `cache` представляет объект кэша.  
  
##  <a name="equals"></a>  sync_none::equals  
 Сравнивает два кэша на равенство.  
  
```
bool equals(const sync<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`Cache`|Объект кэша фильтра синхронизации.|  
|`Other`|Объект кэша для сравнения на равенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член всегда возвращает значение `true`.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)



