---
title: "Класс sync_per_container | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
dev_langs: C++
helpviewer_keywords: sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7864b6367d716ff7504982c4a8cbbed55f7784c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="syncpercontainer-class"></a>Класс sync_per_container
Описывает [фильтр синхронизации](../standard-library/allocators-header.md), предоставляющий отдельный объект кэша для каждого объекта распределителя.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Cache>  
class sync_per_container
 : public Cache
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`Cache`|Тип кэша, связанный с фильтром синхронизации. Возможные типы: [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[equals](#equals)|Сравнивает два кэша на равенство.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="equals"></a>  sync_per_container::equals  
 Сравнивает два кэша на равенство.  
  
```
bool equals(const sync_per_container<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`Cache`|Объект кэша фильтра синхронизации.|  
|`Other`|Объект кэша для сравнения на равенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член всегда возвращает значение `false`.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)



