---
title: Класс CComHeap | Документация Майкрософт
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
ms.openlocfilehash: cf09696f6a13c11fbb37fa6e89ccb9b1241cadd0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751547"
---
# <a name="ccomheap-class"></a>Класс CComHeap

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функции выделения памяти COM.

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
|[CComHeap::GetSize](#getsize)|Вызовите этот метод, чтобы получить размер выделенного блока памяти, выделенной данным диспетчером памяти.|
|[CComHeap::Reallocate](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|

## <a name="remarks"></a>Примечания

`CComHeap` реализует функции выделения памяти, с помощью функции выделения COM, включая [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc), [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree), [IMalloc::GetSize](/windows/desktop/api/objidlbase/nf-objidlbase-imalloc-getsize)и [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc). Максимальный объем памяти, выделяемой равно INT_MAX (2147483647) байт.

## <a name="example"></a>Пример

См. в примере [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

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

*nBytes*  
Запрошенное число байтов в новом блоке памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Вызовите [CComHeap::Free](#free) или [CComHeap::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью этого метода.

Реализовано с помощью [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc).

##  <a name="free"></a>  CComHeap::Free

Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*p*  
Указатель на область памяти, выделенную ранее данным диспетчером памяти. Значение NULL является допустимым значением и не выполняет никаких действий.

### <a name="remarks"></a>Примечания

Реализовано с помощью [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree).

##  <a name="getsize"></a>  CComHeap::GetSize

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

Реализовано с помощью [IMalloc::GetSize](/windows/desktop/api/objidlbase/nf-objidlbase-imalloc-getsize).

##  <a name="reallocate"></a>  CComHeap::Reallocate

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

Вызовите [CComHeap::Free](#free) для освобождения памяти, выделенной с помощью этого метода.

Реализовано с помощью [CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc).

## <a name="see-also"></a>См. также

[Образец DynamicConsumer](../../visual-cpp-samples.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)   
[Класс CWin32Heap](../../atl/reference/cwin32heap-class.md)   
[Класс CLocalHeap](../../atl/reference/clocalheap-class.md)   
[Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)   
[Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)   
[Класс IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)
