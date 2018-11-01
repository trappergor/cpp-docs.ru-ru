---
title: Класс CLocalHeap
ms.date: 11/04/2016
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
ms.openlocfilehash: 7f4fa6b6035b9f0dda35a8e989192505ccf126d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515470"
---
# <a name="clocalheap-class"></a>Класс CLocalHeap

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функций Win32 локальной куче.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CLocalHeap::Allocate](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|
|[CLocalHeap::Free](#free)|Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.|
|[CLocalHeap::GetSize](#getsize)|Вызовите этот метод, чтобы получить размер выделенного блока памяти, выделенной данным диспетчером памяти.|
|[CLocalHeap::Reallocate](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|

## <a name="remarks"></a>Примечания

`CLocalHeap` реализует функции выделения памяти, с помощью функций Win32 локальной куче.

> [!NOTE]
>  Локальная куча функции выполняются медленнее, чем другими функциями управления памятью и не предоставляют меньше возможностей. Таким образом, новые приложения должны использовать [функции кучи](/windows/desktop/Memory/heap-functions). Они доступны в [CWin32Heap](../../atl/reference/cwin32heap-class.md) класса.

## <a name="example"></a>Пример

См. в примере [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>Требования

**Заголовок:** atlmem.h

##  <a name="allocate"></a>  CLocalHeap::Allocate

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

Вызовите [CLocalHeap::Free](#free) или [CLocalHeap::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью этого метода.

Реализовано с помощью [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc) с параметром флага LMEM_FIXED.

##  <a name="free"></a>  CLocalHeap::Free

Вызовите этот метод для освобождения блока памяти, выделенной данным диспетчером памяти.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти. Значение NULL является допустимым значением и не выполняет никаких действий.

### <a name="remarks"></a>Примечания

Реализовано с помощью [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree).

##  <a name="getsize"></a>  CLocalHeap::GetSize

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

Реализовано с помощью [LocalSize](/windows/desktop/api/winbase/nf-winbase-localsize).

##  <a name="reallocate"></a>  CLocalHeap::Reallocate

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

Вызовите [CLocalHeap::Free](#free) для освобождения памяти, выделенной с помощью этого метода.

Реализовано с помощью [LocalReAlloc](/windows/desktop/api/winbase/nf-winbase-localrealloc).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс CComHeap](../../atl/reference/ccomheap-class.md)<br/>
[Класс CWin32Heap](../../atl/reference/cwin32heap-class.md)<br/>
[Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)<br/>
[Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)<br/>
[Класс IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)
