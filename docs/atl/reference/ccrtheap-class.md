---
title: Класс CCRTHeap
ms.date: 11/04/2016
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
ms.openlocfilehash: b761fc3d9d9874e676fad8c74a82f1f08d714d61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647321"
---
# <a name="ccrtheap-class"></a>Класс CCRTHeap

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функции кучи CRT.

## <a name="syntax"></a>Синтаксис

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCRTHeap::Allocate](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|
|[CCRTHeap::Free](#free)|Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.|
|[CCRTHeap::GetSize](#getsize)|Вызовите этот метод, чтобы получить размер выделенного блока памяти, выделенной данным диспетчером памяти.|
|[CCRTHeap::Reallocate](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|

## <a name="remarks"></a>Примечания

`CCRTHeap` реализует памяти, с помощью CRT функций выделения кучи функций, включая [malloc](../../c-runtime-library/reference/malloc.md), [бесплатный](../../c-runtime-library/reference/free.md), [realloc](../../c-runtime-library/reference/realloc.md), и [_msize](../../c-runtime-library/reference/msize.md).

## <a name="example"></a>Пример

См. в примере [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>Требования

**Заголовок:** atlmem.h

##  <a name="allocate"></a>  CCRTHeap::Allocate

Вызовите этот метод, чтобы выделить блок памяти.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nBytes*<br/>
Запрошенное число байтов в новом блоке памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Вызовите [CCRTHeap::Free](#free) или [CCRTHeap::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью этого метода.

Реализовано с помощью [malloc](../../c-runtime-library/reference/malloc.md).

##  <a name="free"></a>  CCRTHeap::Free

Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти. Значение NULL является допустимым значением и не выполняет никаких действий.

### <a name="remarks"></a>Примечания

Реализовано с помощью [бесплатный](../../c-runtime-library/reference/free.md).

##  <a name="getsize"></a>  CCRTHeap::GetSize

Вызовите этот метод, чтобы получить размер выделенного блока памяти, выделенной данным диспетчером памяти.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер выделенного блока памяти в байтах.

### <a name="remarks"></a>Примечания

Реализовано с помощью [_msize](../../c-runtime-library/reference/msize.md).

##  <a name="reallocate"></a>  CCRTHeap::Reallocate

Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти.

*nBytes*<br/>
Запрошенное число байтов в новом блоке памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Вызовите [CCRTHeap::Free](#free) для освобождения памяти, выделенной с помощью этого метода. Реализовано с помощью [realloc](../../c-runtime-library/reference/realloc.md).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс CComHeap](../../atl/reference/ccomheap-class.md)<br/>
[Класс CWin32Heap](../../atl/reference/cwin32heap-class.md)<br/>
[Класс CLocalHeap](../../atl/reference/clocalheap-class.md)<br/>
[Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)<br/>
[Класс IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)
