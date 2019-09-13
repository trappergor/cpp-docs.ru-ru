---
title: Класс CWin32Heap
ms.date: 11/04/2016
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
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
ms.openlocfilehash: ce3585310198ee3e2d7b2b8b829f4202b1021284
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496205"
---
# <a name="cwin32heap-class"></a>Класс CWin32Heap

Этот класс реализует [иатлмеммгр](../../atl/reference/iatlmemmgr-class.md) с помощью функций выделения кучи Win32.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CWin32Heap:: CWin32Heap](#cwin32heap)|Конструктор.|
|[CWin32Heap:: ~ CWin32Heap](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CWin32Heap:: allocate](#allocate)|Выделяет блок памяти из кучи объекта.|
|[CWin32Heap:: Attach](#attach)|Присоединяет объект кучи к существующей куче.|
|[CWin32Heap::D етач](#detach)|Отсоединяет объект кучи от существующей кучи.|
|[CWin32Heap:: Free](#free)|Освобождает память, выделенную ранее из кучи.|
|[CWin32Heap:: DataSize](#getsize)|Возвращает размер блока памяти, выделенного из объекта кучи.|
|[CWin32Heap:: перераспределение](#reallocate)|Повторно выделяет блок памяти из кучи объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CWin32Heap:: m_bOwnHeap](#m_bownheap)|Флаг, используемый для определения текущего владения маркером кучи.|
|[CWin32Heap:: m_hHeap](#m_hheap)|Обработчик объекта кучи.|

## <a name="remarks"></a>Примечания

`CWin32Heap`реализует методы выделения памяти с помощью функций выделения кучи Win32, включая [хеапаллок](/windows/win32/api/heapapi/nf-heapapi-heapalloc) и [хеапфри](/windows/win32/api/heapapi/nf-heapapi-heapfree). В отличие от других классов кучи `CWin32Heap` , перед выделением памяти необходимо предоставить допустимый обработчик кучи: другие классы по умолчанию используют кучу процесса. Этот обработчик можно передать конструктору или методу [CWin32Heap:: Attach](#attach) . Дополнительные сведения см. в описании метода [CWin32Heap:: CWin32Heap](#cwin32heap) .

## <a name="example"></a>Пример

См. пример для [иатлмеммгр](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>Требования

**Заголовок:** атлмем. h

##  <a name="allocate"></a>CWin32Heap:: allocate

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

Вызовите метод [CWin32Heap:: Free](#free) или [CWin32Heap:: reallocate](#reallocate) , чтобы освободить память, выделенную этим методом.

Реализуется с помощью [хеапаллок](/windows/win32/api/heapapi/nf-heapapi-heapalloc).

##  <a name="attach"></a>CWin32Heap:: Attach

Присоединяет объект кучи к существующей куче.

```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>Параметры

*ххеап*<br/>
Существующий обработчик кучи.

*бтакеовнершип*<br/>
Флаг, указывающий, `CWin32Heap` должен ли объект становиться владельцем ресурсов кучи.

### <a name="remarks"></a>Примечания

Если *бтакеовнершип* имеет значение true, `CWin32Heap` объект отвечает за удаление маркера кучи.

##  <a name="cwin32heap"></a>CWin32Heap:: CWin32Heap

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

*ххеап*<br/>
Существующий объект кучи.

*dwFlags*<br/>
Флаги, используемые при создании кучи.

*нинитиалсизе*<br/>
Начальный размер кучи.

*нмакссизе*<br/>
Максимальный размер кучи.

### <a name="remarks"></a>Примечания

Перед выделением памяти необходимо предоставить объект `CWin32Heap` с действительным дескриптором кучи. Для этого проще всего использовать кучу процесса:

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

Также можно указать в конструкторе дескриптор существующей кучи; в этом случае новый объект не становится владельцем кучи. После удаления объекта `CWin32Heap` исходный дескриптор кучи будет по-прежнему действителен.

Существующую кучу можно также присоединить к новому объекту с помощью [CWin32Heap:: Attach](#attach).

Если куча требуется в ситуации, когда все операции выполняются из единственного потока, лучше всего создать объект следующим образом:

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

Параметр HEAP_NO_SERIALIZE указывает, что взаимное исключение не будет использоваться, когда функции кучи выделяют и освобождают память с учетом увеличения производительности.

Третий параметр по умолчанию равен 0, что обеспечивает рост размера кучи по мере необходимости. Описание размеров и флагов памяти см. в разделе [хеапкреате](/windows/win32/api/heapapi/nf-heapapi-heapcreate) .

##  <a name="dtor"></a>CWin32Heap:: ~ CWin32Heap

Деструктор

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>Примечания

Уничтожает обработчик кучи, если `CWin32Heap` объект владеет кучей.

##  <a name="detach"></a>CWin32Heap::D етач

Отсоединяет объект кучи от существующей кучи.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер для кучи, к которой был ранее присоединен объект.

##  <a name="free"></a>CWin32Heap:: Free

Освобождает память, выделенную ранее из кучи с помощью [CWin32Heap:: allocate](#allocate) или [CWin32Heap:: reallocate](#reallocate).

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на блок памяти для освобождения. Значение NULL является допустимым и не выполняет никаких действий.

##  <a name="getsize"></a>CWin32Heap:: DataSize

Возвращает размер блока памяти, выделенного из объекта кучи.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на блок памяти, размер которого будет получен методом. Это указатель, возвращенный [CWin32Heap:: allocate](#allocate) или [CWin32Heap:: reallocate](#reallocate).

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер выделенного блока памяти в байтах.

##  <a name="m_bownheap"></a>CWin32Heap:: m_bOwnHeap

Флаг, используемый для определения текущего владельца обработчика кучи, хранящегося в [m_hHeap](#m_hheap).

```
bool m_bOwnHeap;
```

##  <a name="m_hheap"></a>CWin32Heap:: m_hHeap

Обработчик объекта кучи.

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>Примечания

Переменная, используемая для хранения маркера в объекте heap.

##  <a name="reallocate"></a>CWin32Heap:: перераспределение

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

Если значение *p* равно null, предполагается, что блок памяти еще не был выделен и вызван метод [CWin32Heap:: allocate](#allocate) с аргументом *nBytes*.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Класс IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)<br/>
[Класс CLocalHeap](../../atl/reference/clocalheap-class.md)<br/>
[Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)<br/>
[Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)<br/>
[Класс CComHeap](../../atl/reference/ccomheap-class.md)
