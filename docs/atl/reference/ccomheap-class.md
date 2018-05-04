---
title: Класс CComHeap | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75bd4ad2f182d2a9f62e82b78f9ee9d0db44fa00
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ccomheap-class"></a>Класс CComHeap
Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функций COM выделения памяти.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComHeap::Allocate](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[CComHeap::Free](#free)|Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.|  
|[CComHeap::GetSize](#getsize)|Этот метод используется для получения размера, выделенного блока памяти, выделенной данным диспетчером памяти.|  
|[CComHeap::Reallocate](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|  
  
## <a name="remarks"></a>Примечания  
 `CComHeap` реализует функции выделения памяти с помощью функции выделения COM, включая [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727), [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722), [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226)и [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280). Максимальный объем памяти, выделяемой равен **INT_MAX** (2147483647) байт.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ATLComMem.h  
  
##  <a name="allocate"></a>  CComHeap::Allocate  
 Вызовите этот метод, чтобы выделить блок памяти.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Запрошенное число байтов в новом блоке памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовите [CComHeap::Free](#free) или [CComHeap::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью данного метода.  
  
 Реализовано с помощью [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727).  
  
##  <a name="free"></a>  CComHeap::Free  
 Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти. Значение NULL является допустимым и не выполняет никаких действий.  
  
### <a name="remarks"></a>Примечания  
 Реализовано с помощью [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722).  
  
##  <a name="getsize"></a>  CComHeap::GetSize  
 Этот метод используется для получения размера, выделенного блока памяти, выделенной данным диспетчером памяти.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер выделенного блока памяти в байтах.  
  
### <a name="remarks"></a>Примечания  
 Реализовано с помощью [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226).  
  
##  <a name="reallocate"></a>  CComHeap::Reallocate  
 Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти.  
  
 `nBytes`  
 Запрошенное число байтов в новом блоке памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовите [CComHeap::Free](#free) для освобождения памяти, выделенной с помощью данного метода.  
  
 Реализовано с помощью [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280).  
  
## <a name="see-also"></a>См. также  
 [Образец DynamicConsumer](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CWin32Heap](../../atl/reference/cwin32heap-class.md)   
 [Класс CLocalHeap](../../atl/reference/clocalheap-class.md)   
 [Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)   
 [Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)   
 [Класс IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)
