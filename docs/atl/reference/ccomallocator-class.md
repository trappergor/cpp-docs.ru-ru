---
title: "Класс CComAllocator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComAllocator
- ATL::CComAllocator
- CComAllocator
dev_langs:
- C++
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: d395d347e81b24462a41de5ae3b9d8791d7f82fd
ms.lasthandoff: 02/24/2017

---
# <a name="ccomallocator-class"></a>Класс CComAllocator
Этот класс предоставляет методы для управления памяти с помощью процедур памятью COM.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComAllocator
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|Вызовите статический метод для выделения памяти.|  
|[CComAllocator::Free](#free)|Вызовите статический метод для освобождения памяти.|  
|[CComAllocator::Reallocate](#reallocate)|Вызовите статический метод для повторного выделения памяти.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) для предоставления памяти COM процедур выделения. Класс аналог [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), предоставляет те же методы, с помощью подпрограммы CRT.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="a-nameallocatea--ccomallocatorallocate"></a><a name="allocate"></a>CComAllocator::Allocate  
 Вызовите эту статическую функция для выделения памяти.  
  
```
static void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Количество байтов, которые необходимо выделить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель void на выделенное пространство или значение NULL, если памяти недостаточно.  
  
### <a name="remarks"></a>Примечания  
 Выделяет память. В разделе [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727) подробнее.  
  
##  <a name="a-namefreea--ccomallocatorfree"></a><a name="free"></a>CComAllocator::Free  
 Эта функция статических освободить выделенную память.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на выделенную область памяти.  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенную память. В разделе [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) подробнее.  
  
##  <a name="a-namereallocatea--ccomallocatorreallocate"></a><a name="reallocate"></a>CComAllocator::Reallocate  
 Вызовите эту статическую функцию для повторного выделения памяти.  
  
```
static void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на выделенную область памяти.  
  
 `nBytes`  
 Количество байтов, которые необходимо выделить повторно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель void распределение места на диске, или значение NULL, если недостаточно памяти  
  
### <a name="remarks"></a>Примечания  
 Изменяет объем выделенной памяти. В разделе [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280) для получения дополнительных сведений.  
  
## <a name="see-also"></a>См. также  
 [Класс CComHeapPtr](../../atl/reference/ccomheapptr-class.md)   
 [Класс CCRTAllocator](../../atl/reference/ccrtallocator-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

