---
title: "Класс max_fixed_size | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 50c33d1ea29053ab3c5e76c5c02c22d799e06c6e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="maxfixedsize-class"></a>Класс max_fixed_size
Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) определенным значением.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <std::size_t Max>  
class max_fixed_size
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Max`|Класс max, который определяет максимальное количество элементов для хранения в `freelist`.|  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[max_fixed_size](#max_fixed_size)|Создает объект типа `max_fixed_size`.|  
  
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
  
##  <a name="allocated"></a>  max_fixed_size::allocated  
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
  
##  <a name="deallocated"></a>  max_fixed_size::deallocated  
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
  
##  <a name="full"></a>  max_fixed_size::full  
 Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` если `Max <= _Nblocks`. В противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает `true`, `deallocate` помещает блок памяти в свободный список; если он возвращает false, `deallocate` вызывает оператор `delete` для освобождения блока.  
  
##  <a name="max_fixed_size"></a>  max_fixed_size::max_fixed_size  
 Создает объект типа `max_fixed_size`.  
  
```
max_fixed_size();
```  
  
### <a name="remarks"></a>Примечания  
 Конструктор инициализирует сохраненное значение `_Nblocks` нулем.  
  
##  <a name="released"></a>  max_fixed_size::released  
 Уменьшает количество блоков памяти в свободном списке.  
  
```
void released();
```  
  
### <a name="remarks"></a>Примечания  
 Уменьшает хранимое значение `_Nblocks`. Функция-член `released` текущего класса [max](../standard-library/allocators-header.md) вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.  
  
##  <a name="saved"></a>  max_fixed_size::saved  
 Увеличивает количество блоков памяти в свободном списке.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член увеличивает хранимое значение `_Nblocks`. Она вызывается `cache_freelist::deallocate` каждый раз при помещении блока памяти в свободный список.  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)




