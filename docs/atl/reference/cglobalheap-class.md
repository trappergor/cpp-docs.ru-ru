---
title: "Класс CGlobalHeap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
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
ms.openlocfilehash: f8b4276202a507e2afeb05d10a37fa16565870e8
ms.lasthandoff: 02/24/2017

---
# <a name="cglobalheap-class"></a>Класс CGlobalHeap
Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функций Win32 глобальной кучи.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CGlobalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGlobalHeap::Allocate](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[CGlobalHeap::Free](#free)|Этот метод используется для освобождения блока памяти, выделенный данным диспетчером памяти.|  
|[CGlobalHeap::GetSize](#getsize)|Этот метод используется для получения размера выделенного блока памяти, выделенный данным диспетчером памяти.|  
|[CGlobalHeap::Reallocate](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|  
  
## <a name="remarks"></a>Примечания  
 `CGlobalHeap`реализует функции выделения памяти с помощью функций Win32 глобальной кучи.  
  
> [!NOTE]
>  Функции кучи глобального выполняются медленнее, чем другие функции управления памятью и предоставляет меньше возможностей. Таким образом, новые приложения должны использовать [куча функции](http://msdn.microsoft.com/library/windows/desktop/aa366711). Эти данные доступны в [CWin32Heap](../../atl/reference/cwin32heap-class.md) класса. Глобальные функции по-прежнему используются DDE и функции буфера обмена.  
  
## <a name="example"></a>Пример  
 В примере показано [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlmem.h  
  
##  <a name="allocate"></a>CGlobalHeap::Allocate  
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
 Вызов [CGlobalHeap::Free](#free) или [CGlobalHeap::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью данного метода.  
  
 Реализовано с помощью [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) с параметром флага **GMEM_FIXED**.  
  
##  <a name="free"></a>CGlobalHeap::Free  
 Этот метод используется для освобождения блока памяти, выделенный данным диспетчером памяти.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти. Значение NULL является допустимым значением и не выполняет никаких действий.  
  
### <a name="remarks"></a>Примечания  
 Реализовано с помощью [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579).  
  
##  <a name="getsize"></a>CGlobalHeap::GetSize  
 Этот метод используется для получения размера выделенного блока памяти, выделенный данным диспетчером памяти.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер выделенного блока памяти в байтах.  
  
### <a name="remarks"></a>Примечания  
 Реализовано с помощью [GlobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593).  
  
##  <a name="reallocate"></a>CGlobalHeap::Reallocate  
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
 Вызов [CGlobalHeap::Free](#free) для освобождения памяти, выделенной с помощью данного метода.  
  
 Реализовано с помощью [возможности](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComHeap](../../atl/reference/ccomheap-class.md)   
 [Класс CWin32Heap](../../atl/reference/cwin32heap-class.md)   
 [Класс CLocalHeap](../../atl/reference/clocalheap-class.md)   
 [Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)   
 [Класс IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)

