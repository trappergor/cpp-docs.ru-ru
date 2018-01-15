---
title: "Класс max_unbounded | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_unbounded
- allocators/stdext::max_unbounded::allocated
- allocators/stdext::max_unbounded::deallocated
- allocators/stdext::max_unbounded::full
- allocators/stdext::max_unbounded::released
- allocators/stdext::max_unbounded::saved
dev_langs: C++
helpviewer_keywords:
- stdext::max_unbounded
- stdext::max_unbounded [C++], allocated
- stdext::max_unbounded [C++], deallocated
- stdext::max_unbounded [C++], full
- stdext::max_unbounded [C++], released
- stdext::max_unbounded [C++], saved
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6a06cc5f05812d662dc22fa7609680e3b5a45c97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="maxunbounded-class"></a>Класс max_unbounded
Описывает объект [max class](../standard-library/allocators-header.md), который не ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```
class max_unbounded
```  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[allocated](#allocated)|Увеличивает счетчик выделенных блоков памяти.|  
|[deallocated](#deallocated)|Уменьшает счетчик выделенных блоков памяти.|  
|[full](#full)|Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.|  
|[released](#released)|Уменьшает количество блоков памяти в свободном списке.|  
|[saved](#saved)|Увеличивает количество блоков памяти в свободном списке.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="allocated"></a>  max_unbounded::allocated  
 Увеличивает счетчик выделенных блоков памяти.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`_Nx`|Значение приращения.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Она вызывается после каждого успешного вызова со стороны `cache_freelist::allocate` оператора `new`. Аргумент `_Nx` представляет число блоков памяти в блоке, выделяемом оператором `new`.  
  
##  <a name="deallocated"></a>  max_unbounded::deallocated  
 Уменьшает счетчик выделенных блоков памяти.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`_Nx`|Значение приращения.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Она вызывается после каждого вызова со стороны `cache_freelist::deallocate` оператора `delete`. Аргумент `_Nx` представляет число блоков памяти в блоке, который освобождается оператором `delete`.  
  
##  <a name="full"></a>  max_unbounded::full  
 Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член всегда возвращает значение `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает `true`, `deallocate` помещает блок памяти в свободный список; если он возвращает false, `deallocate` вызывает оператор `delete` для освобождения блока.  
  
##  <a name="released"></a>  max_unbounded::released  
 Уменьшает количество блоков памяти в свободном списке.  
  
```
void released();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.  
  
##  <a name="saved"></a>  max_unbounded::saved  
 Увеличивает количество блоков памяти в свободном списке.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Вызывается методом `cache_freelist::deallocate` каждый раз, когда он помещает блок памяти свободного списка.  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)



