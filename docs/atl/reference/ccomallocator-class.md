---
title: Класс CComAllocator | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94532b40bb44094290eab29a2b8a1f6095a225c5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221105"
---
# <a name="ccomallocator-class"></a>Класс CComAllocator
Этот класс предоставляет методы для управления памяти с помощью COM памяти подпрограммы.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComAllocator
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|Вызовите статический метод для выделения памяти.|  
|[CComAllocator::Free](#free)|Вызовите статический метод для освобождения памяти.|  
|[CComAllocator::Reallocate](#reallocate)|Вызовите статический метод для перераспределения памяти.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс используется [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) для предоставления памяти COM процедур выделения. Класс какой [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), предоставляет те же методы, с помощью подпрограммы CRT.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="allocate"></a>  CComAllocator::Allocate  
 Вызовите эту статическую функция для выделения памяти.  
  
```
static void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *nBytes*  
 Количество байтов, которые необходимо выделить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель void на выделенное пространство или значение NULL, если памяти недостаточно.  
  
### <a name="remarks"></a>Примечания  
 Выделяет память. См. в разделе [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) для получения дополнительных сведений.  
  
##  <a name="free"></a>  CComAllocator::Free  
 Вызовите эту статическую функцию, чтобы освободить выделенную память.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 Указатель на выделенную область памяти.  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенную память. См. в разделе [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree) для получения дополнительных сведений.  
  
##  <a name="reallocate"></a>  CComAllocator::Reallocate  
 Вызовите эту статическую функцию для повторного выделения памяти.  
  
```
static void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 Указатель на выделенную область памяти.  
  
 *nBytes*  
 Количество байтов, которые необходимо выделить повторно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель void на выделенное пространство или значение NULL, если недостаточно памяти  
  
### <a name="remarks"></a>Примечания  
 Изменяет объем выделенной памяти. См. в разделе [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc) для получения дополнительных сведений.  
  
## <a name="see-also"></a>См. также  
 [Класс CComHeapPtr](../../atl/reference/ccomheapptr-class.md)   
 [Класс CCRTAllocator](../../atl/reference/ccrtallocator-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
