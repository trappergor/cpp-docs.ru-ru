---
title: Класс CAutoVectorPtr
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
ms.openlocfilehash: 8485f13b91c72d12c2084d2714f2acfa6dda7f01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478759"
---
# <a name="cautovectorptr-class"></a>Класс CAutoVectorPtr

Этот класс представляет объект интеллектуального указателя с помощью вектора новый и удалять операторов.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CAutoVectorPtr
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|Конструктор.|
|[CAutoVectorPtr:: ~ CAutoVectorPtr](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtr::Allocate](#allocate)|Вызовите этот метод для выделения памяти, необходимый массив объектов, указываемых `CAutoVectorPtr`.|
|[CAutoVectorPtr::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|
|[CAutoVectorPtr::Detach](#detach)|Вызовите этот метод для освобождения владения указатель.|
|[CAutoVectorPtr::Free](#free)|Вызовите этот метод, чтобы удалить объект, на которые указывают `CAutoVectorPtr`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtr::operator T *](#operator_t__star)|Оператор приведения типов.|
|[CAutoVectorPtr::operator =](#operator_eq)|Оператор присваивания.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAutoVectorPtr::m_p](#m_p)|Указатель данных переменная-член.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы для создания и управления смарт-указатель, который поможет защититься от утечки памяти, автоматически освобождение ресурсов, когда оно выпадает из области. `CAutoVectorPtr` аналогичен `CAutoPtr`, единственное отличие —, `CAutoVectorPtr` использует [вектор new&#91; &#93; ](../../standard-library/new-operators.md#op_new_arr) и [вектор delete&#91; &#93; ](../../standard-library/new-operators.md#op_delete_arr) для выделения и освобождения памяти вместо C++ **новый** и **удалить** операторы. См. в разделе [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) если коллекцию классов `CAutoVectorPtr` являются обязательными.

См. в разделе [CAutoPtr](../../atl/reference/cautoptr-class.md) пример использования класса смарт-указатель.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="allocate"></a>  CAutoVectorPtr::Allocate

Вызовите этот метод для выделения памяти, необходимый массив объектов, указываемых `CAutoVectorPtr`.

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>Параметры

*nElements*<br/>
Количество элементов в массиве.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если память успешно выделен, значение false в случае сбоя.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет сбой утверждения, если [CAutoVectorPtr::m_p](#m_p) переменную-член в текущий момент направлен к существующему значению; то есть не равно NULL.

##  <a name="attach"></a>  CAutoVectorPtr::Attach

Вызовите этот метод, чтобы стать владельцем существующего указателя.

```
void Attach(T* p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
`CAutoVectorPtr` Объект будет стать владельцем этого указателя.

### <a name="remarks"></a>Примечания

Когда `CAutoVectorPtr` объект принимает владение указатель, оно автоматически удалит указатель и все выделенные данные при его выходит за пределы области. Если [CAutoVectorPtr::Detach](#detach) — вызывается, программист еще раз данный ответственность за освобождение любой выделяются ресурсы.

В отладочных сборках, произойдет сбой утверждения, если [CAutoVectorPtr::m_p](#m_p) переменную-член в текущий момент направлен к существующему значению; то есть не равно NULL.

##  <a name="cautovectorptr"></a>  CAutoVectorPtr::CAutoVectorPtr

Конструктор.

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Существующего указателя.

### <a name="remarks"></a>Примечания

`CAutoVectorPtr` Объект может быть создан с помощью существующего указателя, в этом случае он передает право владения указателем.

##  <a name="dtor"></a>  CAutoVectorPtr:: ~ CAutoVectorPtr

Деструктор

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы. Вызовы [CAutoVectorPtr::Free](#free).

##  <a name="detach"></a>  CAutoVectorPtr::Detach

Вызовите этот метод для освобождения владения указатель.

```
T* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию указателя.

### <a name="remarks"></a>Примечания

Освобождает права владения указателем, задает [CAutoVectorPtr::m_p](#m_p) переменную-член NULL и возвращает копию указателя. После вызова метода `Detach`, он на программиста, чтобы освободить все выделяется ресурсы по которому `CAutoVectorPtr` объект ранее предполагается ответственности.

##  <a name="free"></a>  CAutoVectorPtr::Free

Вызовите этот метод, чтобы удалить объект, на которые указывают `CAutoVectorPtr`.

```
void Free() throw();
```

### <a name="remarks"></a>Примечания

Объект, на который указывает `CAutoVectorPtr` освобождается и [CAutoVectorPtr::m_p](#m_p) переменной-члена имеет значение NULL.

##  <a name="m_p"></a>  CAutoVectorPtr::m_p

Указатель данных переменная-член.

```
T* m_p;
```

### <a name="remarks"></a>Примечания

Эта переменная-член содержит информацию об указателях.

##  <a name="operator_eq"></a>  CAutoVectorPtr::operator =

Оператор присваивания.

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на **CAutoVectorPtr\< T >**.

### <a name="remarks"></a>Примечания

Оператор присваивания отсоединяет `CAutoVectorPtr` объект из любой текущий указатель и присоединяет новый указатель, *p*, вместо него.

##  <a name="operator_t__star"></a>  CAutoVectorPtr::operator T *

Оператор приведения типов.

```
operator T*() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает указатель на тип данных объекта, определенный в шаблоне класса.

## <a name="see-also"></a>См. также

[Класс CAutoPtr](../../atl/reference/cautoptr-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
