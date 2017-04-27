---
title: "Класс max_none | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- max_none
- stdext::max_none
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs:
- C++
helpviewer_keywords:
- max_none class
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
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
ms.openlocfilehash: 522e950aa9f7a33ee6210d3b40effd2a1760daf3
ms.lasthandoff: 02/24/2017

---
# <a name="maxnone-class"></a>Класс max_none
Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) нулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <std::size_t Max>  
class max_none
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Max`|Класс max, который определяет максимальное количество элементов для хранения в `freelist`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[allocated](#max_none__allocated)|Увеличивает счетчик выделенных блоков памяти.|  
|[deallocated](#max_none__deallocated)|Уменьшает счетчик выделенных блоков памяти.|  
|[full](#max_none__full)|Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.|  
|[released](#max_none__released)|Уменьшает количество блоков памяти в свободном списке.|  
|[saved](#max_none__saved)|Увеличивает количество блоков памяти в свободном списке.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="max_none__allocated"></a>  max_none::allocated  
 Увеличивает счетчик выделенных блоков памяти.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Nx`|Значение приращения.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Она вызывается после каждого успешного вызова со стороны `cache_freelist::allocate` оператора `new`. Аргумент `_Nx` представляет число блоков памяти в блоке, выделяемом оператором `new`.  
  
##  <a name="max_none__deallocated"></a>  max_none::deallocated  
 Уменьшает счетчик выделенных блоков памяти.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Nx`|Значение приращения.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Она вызывается после каждого вызова со стороны `cache_freelist::deallocate` оператора `delete`. Аргумент `_Nx` представляет число блоков памяти в блоке, который освобождается оператором `delete`.  
  
##  <a name="max_none__full"></a>  max_none::full  
 Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член всегда возвращает значение `true`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает `true`, `deallocate` помещает блок памяти в свободный список; если он возвращает false, `deallocate` вызывает оператор `delete` для освобождения блока.  
  
##  <a name="max_none__released"></a>  max_none::released  
 Уменьшает количество блоков памяти в свободном списке.  
  
```
void released();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.  
  
##  <a name="max_none__saved"></a>  max_none::saved  
 Увеличивает количество блоков памяти в свободном списке.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член ничего не делает. Вызывается методом `cache_freelist::deallocate` каждый раз, когда он помещает блок памяти свободного списка.  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)




