---
title: Класс CHeapPtrBase
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
ms.openlocfilehash: f183bb21d6a23b4e8ac4284894cfa2fcc7bb1dfd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538163"
---
# <a name="cheapptrbase-class"></a>Класс CHeapPtrBase

Этот класс — это основа для нескольких классов кучи смарт-указатель.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта для сохранения в куче.

*Распределитель*<br/>
Класс выделения памяти для использования. По умолчанию для подпрограммы CRT используются для выделения и освобождения памяти.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Этот метод используется для выделения памяти.|
|[CHeapPtrBase::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|
|[CHeapPtrBase::Detach](#detach)|Вызовите этот метод для освобождения владения указатель.|
|[CHeapPtrBase::Free](#free)|Вызовите этот метод, чтобы удалить объект, на которые указывают `CHeapPtrBase`.|
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|Этот метод вызывается для повторного выделения памяти.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrBase::operator T *](#operator_t_star)|Оператор приведения типов.|
|[CHeapPtrBase::operator &](#operator_amp)|& Оператор.|
|[CHeapPtrBase::operator "->"](#operator_ptr)|Оператор указателя на член.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CHeapPtrBase::m_pData](#m_pdata)|Указатель данных переменная-член.|

## <a name="remarks"></a>Примечания

Этот класс — это основа для нескольких классов кучи смарт-указатель. Производные классы, например, [CHeapPtr](../../atl/reference/cheapptr-class.md) и [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), добавить свои собственные конструкторы и операторы. См. в статье эти классы примеры реализации.

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

##  <a name="allocatebytes"></a>  CHeapPtrBase::AllocateBytes

Этот метод используется для выделения памяти.

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nBytes*<br/>
Число байтов памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если память успешно выделения false в противном случае.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет сбой утверждения, если [CHeapPtrBase::m_pData](#m_pdata) переменную-член в текущий момент направлен к существующему значению; то есть не равно NULL.

##  <a name="attach"></a>  CHeapPtrBase::Attach

Вызовите этот метод, чтобы стать владельцем существующего указателя.

```
void Attach(T* pData) throw();
```

### <a name="parameters"></a>Параметры

*pData*<br/>
`CHeapPtrBase` Объект будет стать владельцем этого указателя.

### <a name="remarks"></a>Примечания

Когда `CHeapPtrBase` объект принимает владение указатель, оно автоматически удалит указатель и все выделенные данные при его выходит за пределы области.

В отладочных сборках, произойдет сбой утверждения, если [CHeapPtrBase::m_pData](#m_pdata) переменную-член в текущий момент направлен к существующему значению; то есть не равно NULL.

##  <a name="dtor"></a>  CHeapPtrBase:: ~ CHeapPtrBase

Деструктор

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="detach"></a>  CHeapPtrBase::Detach

Вызовите этот метод для освобождения владения указатель.

```
T* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию указателя.

### <a name="remarks"></a>Примечания

Освобождает права владения указателем, задает [CHeapPtrBase::m_pData](#m_pdata) переменную-член NULL и возвращает копию указателя.

##  <a name="free"></a>  CHeapPtrBase::Free

Вызовите этот метод, чтобы удалить объект, на которые указывают `CHeapPtrBase`.

```
void Free() throw();
```

### <a name="remarks"></a>Примечания

Объект, на который указывает `CHeapPtrBase` освобождается и [CHeapPtrBase::m_pData](#m_pdata) переменной-члена имеет значение NULL.

##  <a name="m_pdata"></a>  CHeapPtrBase::m_pData

Указатель данных переменная-член.

```
T* m_pData;
```

### <a name="remarks"></a>Примечания

Эта переменная-член содержит информацию об указателях.

##  <a name="operator_amp"></a>  CHeapPtrBase::operator &amp;

& Оператор.

```
T** operator&() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес объекта, на которые указывают `CHeapPtrBase` объекта.

##  <a name="operator_ptr"></a>  CHeapPtrBase::operator-&gt;

Оператор указателя на член.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение [CHeapPtrBase::m_pData](#m_pdata) переменной-члена.

### <a name="remarks"></a>Примечания

Этот оператор используется для вызова метода в классе, на которые указывают `CHeapPtrBase` объекта. В отладочных сборках, произойдет сбой утверждения, если `CHeapPtrBase` указывает на значение NULL.

##  <a name="operator_t_star"></a>  CHeapPtrBase::operator T *

Оператор приведения типов.

```
operator T*() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает [CHeapPtrBase::m_pData](#m_pdata).

##  <a name="reallocatebytes"></a>  CHeapPtrBase::ReallocateBytes

Этот метод вызывается для повторного выделения памяти.

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nBytes*<br/>
Новый объем памяти, выделенной в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если память успешно выделения false в противном случае.

## <a name="see-also"></a>См. также

[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Класс CComHeapPtr](../../atl/reference/ccomheapptr-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
