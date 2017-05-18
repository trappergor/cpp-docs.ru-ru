---
title: "Класс CCRTAllocator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 5154a095409705e96dee6f52c67d7c23b0e6691f
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ccrtallocator-class"></a>Класс CCRTAllocator
Этот класс предоставляет методы для управления памяти с помощью подпрограммы памяти CRT.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ATL::CCRTAllocator
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCRTAllocator::Allocate](#allocate)|(Статический) Этот метод используется для выделения памяти.|  
|[CCRTAllocator::Free](#free)|(Статический) Этот метод используется для освобождения памяти.|  
|[CCRTAllocator::Reallocate](#reallocate)|(Статический) Этот метод вызывается для повторного выделения памяти.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется [CHeapPtr](../../atl/reference/cheapptr-class.md) для предоставления процедур выделения памяти CRT. Класс аналог [CComAllocator](../../atl/reference/ccomallocator-class.md), предоставляет те же методы, с помощью COM-подпрограммы.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="allocate"></a>CCRTAllocator::Allocate  
 Вызовите эту статическую функция для выделения памяти.  
  
```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Количество байтов, которые необходимо выделить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель void на выделенное пространство или значение NULL, если памяти недостаточно.  
  
### <a name="remarks"></a>Примечания  
 Выделяет память. В разделе [malloc](../../c-runtime-library/reference/malloc.md) подробнее.  
  
##  <a name="free"></a>CCRTAllocator::Free  
 Эта функция статических для освобождения памяти.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на выделенную область памяти.  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенную память. В разделе [свободного](../../c-runtime-library/reference/free.md) подробнее.  
  
##  <a name="reallocate"></a>CCRTAllocator::Reallocate  
 Вызовите эту статическую функцию для повторного выделения памяти.  
  
```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на выделенную область памяти.  
  
 `nBytes`  
 Количество байтов, которые необходимо выделить повторно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель void на выделенное пространство или значение NULL, если памяти недостаточно.  
  
### <a name="remarks"></a>Примечания  
 Изменяет объем выделенной памяти. В разделе [realloc](../../c-runtime-library/reference/realloc.md) для получения дополнительных сведений.  
  
## <a name="see-also"></a>См. также  
 [Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Класс CComAllocator](../../atl/reference/ccomallocator-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

