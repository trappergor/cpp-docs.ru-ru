---
title: "Класс CCRTHeap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
dev_langs: C++
helpviewer_keywords: CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7de92517a70fa094459b6a626802e2e6f4c1ddd6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ccrtheap-class"></a>Класс CCRTHeap
Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функций кучи CRT.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CCRTHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCRTHeap::Allocate](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[CCRTHeap::Free](#free)|Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.|  
|[CCRTHeap::GetSize](#getsize)|Этот метод используется для получения размера, выделенного блока памяти, выделенной данным диспетчером памяти.|  
|[CCRTHeap::Reallocate](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|  
  
## <a name="remarks"></a>Примечания  
 `CCRTHeap`реализует функции, включая кучи CRT с помощью функции выделения памяти [malloc](../../c-runtime-library/reference/malloc.md), [свободного](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md), и [_msize](../../c-runtime-library/reference/msize.md).  
  
## <a name="example"></a>Пример  
 Далее приведен пример [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlmem.h  
  
##  <a name="allocate"></a>CCRTHeap::Allocate  
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
 Вызовите [CCRTHeap::Free](#free) или [CCRTHeap::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью данного метода.  
  
 Реализовано с помощью [malloc](../../c-runtime-library/reference/malloc.md).  
  
##  <a name="free"></a>CCRTHeap::Free  
 Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти. Значение NULL является допустимым и не выполняет никаких действий.  
  
### <a name="remarks"></a>Примечания  
 Реализовано с помощью [свободного](../../c-runtime-library/reference/free.md).  
  
##  <a name="getsize"></a>CCRTHeap::GetSize  
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
 Реализовано с помощью [_msize](../../c-runtime-library/reference/msize.md).  
  
##  <a name="reallocate"></a>CCRTHeap::Reallocate  
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
 Вызовите [CCRTHeap::Free](#free) для освобождения памяти, выделенной с помощью данного метода. Реализовано с помощью [realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComHeap](../../atl/reference/ccomheap-class.md)   
 [Класс CWin32Heap](../../atl/reference/cwin32heap-class.md)   
 [Класс CLocalHeap](../../atl/reference/clocalheap-class.md)   
 [Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)   
 [Класс IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)
