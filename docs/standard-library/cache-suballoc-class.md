---
title: "Класс cache_suballoc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_suballoc
- stdext::cache_suballoc
- cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
dev_langs:
- C++
helpviewer_keywords:
- cache_suballoc class
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
caps.latest.revision: 17
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
ms.openlocfilehash: fa98856bc7e55ca78effb64c806a95cab60a68a5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="cachesuballoc-class"></a>Класс cache_suballoc
Задает [распределитель блоков](../standard-library/allocators-header.md), который выделяет и освобождает блоки памяти одного размера.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <std::size_t Sz, size_t Nelts = 20>  
class cache_suballoc
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Sz`|Число элементов в массиве, которые нужно выделить.|  
  
## <a name="remarks"></a>Примечания  
 Класс cache_suballoc шаблона сохраняет освобожденные блоки памяти в списке свободных неограниченной длины с помощью `freelist<sizeof(Type), max_unbounded>` и распределяет блоки памяти из большего участка памяти, выделенного с помощью `operator new`, когда список свободных пуст.  
  
 Каждый участок памяти содержит `Sz * Nelts` байт свободной памяти и данных, которые требуются `operator new` и `operator delete`. Выделенные участки памяти никогда не будут освобождены.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[cache_suballoc](#cache_suballoc)|Создает объект типа `cache_suballoc`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[allocate](#allocate)|Выделяет блок памяти.|  
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="allocate"></a>  cache_suballoc::allocate  
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
  
##  <a name="cache_suballoc"></a>  cache_suballoc::cache_suballoc  
 Создает объект типа `cache_suballoc`.  
  
```
cache_suballoc();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="deallocate"></a>  cache_suballoc::deallocate  
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




