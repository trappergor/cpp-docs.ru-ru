---
title: Класс CCRTAllocator | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bfd7d5a040da4d27838e8045b6c4c64950e515dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054848"
---
# <a name="ccrtallocator-class"></a>Класс CCRTAllocator

Этот класс предоставляет методы для управления памяти с помощью подпрограммы CRT памяти.

## <a name="syntax"></a>Синтаксис

```
class ATL::CCRTAllocator
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCRTAllocator::Allocate](#allocate)|(Статический) Этот метод используется для выделения памяти.|
|[CCRTAllocator::Free](#free)|(Статический) Вызовите этот метод для освобождения памяти.|
|[CCRTAllocator::Reallocate](#reallocate)|(Статический) Этот метод вызывается для повторного выделения памяти.|

## <a name="remarks"></a>Примечания

Этот класс используется [CHeapPtr](../../atl/reference/cheapptr-class.md) для предоставления процедур выделения памяти CRT. Класс какой [CComAllocator](../../atl/reference/ccomallocator-class.md), предоставляет те же методы, с помощью COM-подпрограммы.

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

##  <a name="allocate"></a>  CCRTAllocator::Allocate

Вызовите эту статическую функция для выделения памяти.

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nBytes*<br/>
Количество байтов, которые необходимо выделить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель void на выделенное пространство или значение NULL, если памяти недостаточно.

### <a name="remarks"></a>Примечания

Выделяет память. См. в разделе [malloc](../../c-runtime-library/reference/malloc.md) для получения дополнительных сведений.

##  <a name="free"></a>  CCRTAllocator::Free

Вызовите эту статическую функцию для освобождения памяти.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на выделенную область памяти.

### <a name="remarks"></a>Примечания

Освобождает выделенную память. См. в разделе [бесплатный](../../c-runtime-library/reference/free.md) для получения дополнительных сведений.

##  <a name="reallocate"></a>  CCRTAllocator::Reallocate

Вызовите эту статическую функцию для повторного выделения памяти.

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на выделенную область памяти.

*nBytes*<br/>
Количество байтов, которые необходимо выделить повторно.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель void на выделенное пространство или значение NULL, если памяти недостаточно.

### <a name="remarks"></a>Примечания

Изменяет объем выделенной памяти. См. в разделе [realloc](../../c-runtime-library/reference/realloc.md) для получения дополнительных сведений.

## <a name="see-also"></a>См. также

[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Класс CComAllocator](../../atl/reference/ccomallocator-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
