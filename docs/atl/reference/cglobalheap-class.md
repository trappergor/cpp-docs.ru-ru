---
title: Класс CGlobalHeap | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f3113cf4176c3f582a210e89e732d5e0d92b62d
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882836"
---
# <a name="cglobalheap-class"></a>Класс CGlobalHeap
Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функции глобального кучи Win32.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CGlobalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CGlobalHeap::Allocate](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|  
|[CGlobalHeap::Free](#free)|Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.|  
|[CGlobalHeap::GetSize](#getsize)|Вызовите этот метод, чтобы получить размер выделенного блока памяти, выделенной данным диспетчером памяти.|  
|[CGlobalHeap::Reallocate](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|  
  
## <a name="remarks"></a>Примечания  
 `CGlobalHeap` реализует функции выделения памяти, с помощью функции глобального кучи Win32.  
  
> [!NOTE]
>  Функции глобального кучи выполняются медленнее, чем другими функциями управления памятью и не предоставляют меньше возможностей. Таким образом, новые приложения должны использовать [функции кучи](http://msdn.microsoft.com/library/windows/desktop/aa366711). Они доступны в [CWin32Heap](../../atl/reference/cwin32heap-class.md) класса. Глобальные функции по-прежнему используются DDE и функций, буфер обмена.  
  
## <a name="example"></a>Пример  
 См. в примере [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlmem.h  
  
##  <a name="allocate"></a>  CGlobalHeap::Allocate  
 Вызовите этот метод, чтобы выделить блок памяти.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *nBytes*  
 Запрошенное число байтов в новом блоке памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовите [CGlobalHeap::Free](#free) или [CGlobalHeap::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью этого метода.  
  
 Реализовано с помощью [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) с параметром флага GMEM_FIXED.  
  
##  <a name="free"></a>  CGlobalHeap::Free  
 Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти. Значение NULL является допустимым значением и не выполняет никаких действий.  
  
### <a name="remarks"></a>Примечания  
 Реализовано с помощью [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579).  
  
##  <a name="getsize"></a>  CGlobalHeap::GetSize  
 Вызовите этот метод, чтобы получить размер выделенного блока памяти, выделенной данным диспетчером памяти.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер выделенного блока памяти в байтах.  
  
### <a name="remarks"></a>Примечания  
 Реализовано с помощью [GlobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593).  
  
##  <a name="reallocate"></a>  CGlobalHeap::Reallocate  
 Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *p*  
 Указатель на область памяти, выделенную ранее данным диспетчером памяти.  
  
 *nBytes*  
 Запрошенное число байтов в новом блоке памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на начало выделенного блока памяти.  
  
### <a name="remarks"></a>Примечания  
 Вызовите [CGlobalHeap::Free](#free) для освобождения памяти, выделенной с помощью этого метода.  
  
 Реализовано с помощью [GlobalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366590).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComHeap](../../atl/reference/ccomheap-class.md)   
 [Класс CWin32Heap](../../atl/reference/cwin32heap-class.md)   
 [Класс CLocalHeap](../../atl/reference/clocalheap-class.md)   
 [Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)   
 [Класс IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)
