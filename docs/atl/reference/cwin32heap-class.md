---
title: Класс CWin32Heap | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWin32Heap
- ATLMEM/ATL::CWin32Heap
- ATLMEM/ATL::CWin32Heap::CWin32Heap
- ATLMEM/ATL::CWin32Heap::Allocate
- ATLMEM/ATL::CWin32Heap::Attach
- ATLMEM/ATL::CWin32Heap::Detach
- ATLMEM/ATL::CWin32Heap::Free
- ATLMEM/ATL::CWin32Heap::GetSize
- ATLMEM/ATL::CWin32Heap::Reallocate
- ATLMEM/ATL::CWin32Heap::m_bOwnHeap
- ATLMEM/ATL::CWin32Heap::m_hHeap
dev_langs:
- C++
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3b10648a3251a705085e31559a98b6ee4957c72
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088479"
---
# <a name="cwin32heap-class"></a>Класс CWin32Heap

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с помощью функций выделения кучи Win32.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWin32Heap::CWin32Heap](#cwin32heap)|Конструктор.|
|[CWin32Heap:: ~ CWin32Heap](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWin32Heap::Allocate](#allocate)|Выделяет блок памяти из кучи объекта.|
|[CWin32Heap::Attach](#attach)|Присоединяет объект кучи в существующую кучу.|
|[CWin32Heap::Detach](#detach)|Отсоединяет объект кучи в существующую кучу.|
|[CWin32Heap::Free](#free)|Освобождает память, выделенную ранее из кучи.|
|[CWin32Heap::GetSize](#getsize)|Возвращает размер блока памяти, выделенной из кучи объекта.|
|[CWin32Heap::Reallocate](#reallocate)|Повторно выделяет блок памяти из кучи объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|Флаг, используемый для определения текущего владельца дескриптора кучи.|
|[CWin32Heap::m_hHeap](#m_hheap)|Дескриптор объекта кучи.|

## <a name="remarks"></a>Примечания

`CWin32Heap` реализует методы распределения памяти, с помощью функций выделения кучи Win32, включая [HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc) и [HeapFree](/windows/desktop/api/heapapi/nf-heapapi-heapfree). В отличие от других классов кучи `CWin32Heap` требует действительным дескриптором кучи предоставляться до выделения памяти: другие классы по умолчанию используют кучу процесса. Дескриптор может предоставляться конструктору, или к [CWin32Heap::Attach](#attach) метод. См. в разделе [CWin32Heap::CWin32Heap](#cwin32heap) метод для получения дополнительных сведений.

## <a name="example"></a>Пример

См. в примере [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>Требования

**Заголовок:** atlmem.h

##  <a name="allocate"></a>  CWin32Heap::Allocate

Выделяет блок памяти из кучи объекта.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nBytes*<br/>
Запрошенное число байтов в новом блоке памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Вызовите [CWin32Heap::Free](#free) или [CWin32Heap::Reallocate](#reallocate) для освобождения памяти, выделенной с помощью этого метода.

Реализовано с помощью [HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc).

##  <a name="attach"></a>  CWin32Heap::Attach

Присоединяет объект кучи в существующую кучу.

```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>Параметры

*hHeap*<br/>
Дескриптор существующей кучи.

*bTakeOwnership*<br/>
Флаг, указывающий, в том случае, если `CWin32Heap` объект является владельцем по отношению к ресурсам кучи.

### <a name="remarks"></a>Примечания

Если *bTakeOwnership* имеет значение TRUE, `CWin32Heap` объект отвечает за удаление дескриптор кучи.

##  <a name="cwin32heap"></a>  CWin32Heap::CWin32Heap

Конструктор.

```
CWin32Heap() throw();
CWin32Heap( HANDLE  hHeap) throw();
CWin32Heap(
    DWORD  dwFlags,
    size_t nInitialSize,
    size_t nMaxSize = 0);
```

### <a name="parameters"></a>Параметры

*hHeap*<br/>
Существующий объект кучи.

*dwFlags*<br/>
Флаги, используемые при создании кучи.

*nInitialSize*<br/>
Начальный размер кучи.

*nMaxSize*<br/>
Максимальный размер кучи.

### <a name="remarks"></a>Примечания

Перед выделением памяти необходимо предоставить объект `CWin32Heap` с действительным дескриптором кучи. Для этого проще всего использовать кучу процесса:

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

Также можно указать в конструкторе дескриптор существующей кучи; в этом случае новый объект не становится владельцем кучи. После удаления объекта `CWin32Heap` исходный дескриптор кучи будет по-прежнему действителен.

Существующую кучу можно также прикреплять к новому объекта, использование [CWin32Heap::Attach](#attach).

Если куча требуется в ситуации, когда все операции выполняются из единственного потока, лучше всего создать объект следующим образом:

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

Параметр HEAP_NO_SERIALIZE указывает, что взаимное исключение не будет использоваться, когда функции кучи выделяют и освобождают память, с соответствующим увеличением производительности.

Третий параметр по умолчанию равен 0, что обеспечивает рост размера кучи по мере необходимости. См. в разделе [HeapCreate](/windows/desktop/api/heapapi/nf-heapapi-heapcreate) объяснение объемы памяти и флаги.

##  <a name="dtor"></a>  CWin32Heap:: ~ CWin32Heap

Деструктор

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>Примечания

Уничтожает дескриптор кучи, если `CWin32Heap` объект имеет становится владельцем кучи.

##  <a name="detach"></a>  CWin32Heap::Detach

Отсоединяет объект кучи в существующую кучу.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор кучи, к которому был ранее подключен объект.

##  <a name="free"></a>  CWin32Heap::Free

Освобождает память, выделенную ранее из кучи, [CWin32Heap::Allocate](#allocate) или [CWin32Heap::Reallocate](#reallocate).

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на блок памяти, который необходимо освободить. Значение NULL является допустимым значением и не выполняет никаких действий.

##  <a name="getsize"></a>  CWin32Heap::GetSize

Возвращает размер блока памяти, выделенной из кучи объекта.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на блок памяти, размер которого будет получать метод. Это является указателем, возвращенным [CWin32Heap::Allocate](#allocate) или [CWin32Heap::Reallocate](#reallocate).

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер в байтах, выделенный блок памяти.

##  <a name="m_bownheap"></a>  CWin32Heap::m_bOwnHeap

Флаг, используемый для определения текущего владельца дескриптора кучи, хранящиеся в [m_hHeap](#m_hheap).

```
bool m_bOwnHeap;
```

##  <a name="m_hheap"></a>  CWin32Heap::m_hHeap

Дескриптор объекта кучи.

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>Примечания

Переменная, используемая для хранения дескриптора кучи объекта.

##  <a name="reallocate"></a>  CWin32Heap::Reallocate

Повторно выделяет блок памяти из кучи объекта.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на блок памяти для перераспределения.

*nBytes*<br/>
Новый размер выделенного блока в байтах. Блок можно увеличить или уменьшить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Если *p* имеет значение NULL, предполагается, что блок памяти еще не был выделен и [CWin32Heap::Allocate](#allocate) вызывается с аргументом *nBytes*.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)<br/>
[Класс CLocalHeap](../../atl/reference/clocalheap-class.md)<br/>
[Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)<br/>
[Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)<br/>
[Класс CComHeap](../../atl/reference/ccomheap-class.md)
