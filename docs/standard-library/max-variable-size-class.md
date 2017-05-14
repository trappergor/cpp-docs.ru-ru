---
title: "Класс max_variable_size | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::max_variable_size
- allocators/stdext::max_variable_size
- max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
dev_langs:
- C++
helpviewer_keywords:
- max_variable_size class
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: 18
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
ms.openlocfilehash: dbb2405313f9b58bc6c5634410a5c378e0f0abca
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="maxvariablesize-class"></a>Класс max_variable_size
Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) до значения, приблизительно пропорционального количеству выделенных блоков памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class max_variable_size
```  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[max_variable_size](#max_variable_size)|Создает объект типа `max_variable_size`.|  
  
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
  
##  <a name="allocated"></a>  max_variable_size::allocated  
 Увеличивает счетчик выделенных блоков памяти.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Nx`|Значение приращения.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член добавляет `_Nx` к сохраненному значению `_Nallocs`. Она вызывается после каждого успешного вызова со стороны `cache_freelist::allocate` оператора `new`. Аргумент `_Nx` представляет число блоков памяти в блоке, выделяемом оператором `new`.  
  
##  <a name="deallocated"></a>  max_variable_size::deallocated  
 Уменьшает счетчик выделенных блоков памяти.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Nx`|Значение приращения.|  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вычитает `_Nx` из сохраненного значения `_Nallocs`. Она вызывается после каждого вызова со стороны `cache_freelist::deallocate` оператора `delete`. Аргумент `_Nx` представляет число блоков памяти в блоке, который освобождается оператором `delete`.  
  
##  <a name="full"></a>  max_variable_size::full  
 Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` если `_Nallocs / 16 + 16 <= _Nblocks`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает `true`, `deallocate` помещает блок памяти в свободный список; если он возвращает false, `deallocate` вызывает оператор `delete` для освобождения блока.  
  
##  <a name="max_variable_size"></a>  max_variable_size::max_variable_size  
 Создает объект типа `max_variable_size`.  
  
```
max_variable_size();
```  
  
### <a name="remarks"></a>Примечания  
 Конструктор инициализирует сохраненные значения `_Nblocks` и `_Nallocs` нулями.  
  
##  <a name="released"></a>  max_variable_size::released  
 Уменьшает количество блоков памяти в свободном списке.  
  
```
void released();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член уменьшает хранимое значение `_Nblocks`. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.  
  
##  <a name="saved"></a>  max_variable_size::saved  
 Увеличивает количество блоков памяти в свободном списке.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член увеличивает хранимое значение `_Nblocks`. Она вызывается `cache_freelist::deallocate` каждый раз при помещении блока памяти в свободный список.  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)




