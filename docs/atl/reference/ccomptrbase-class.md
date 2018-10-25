---
title: Класс CComPtrBase | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
dev_langs:
- C++
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68701e0cc79eac815ab56f99f41cc0f47bf3585f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065139"
---
# <a name="ccomptrbase-class"></a>Класс CComPtrBase

Этот класс предоставляет основу для классов интеллектуальных указателей, использование памяти на основе COM-подпрограммы.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, на которые ссылается интеллектуального указателя.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComPtrBase:: ~ CComPtrBase](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComPtrBase::Advise](#advise)|Вызовите этот метод, чтобы создать подключение между `CComPtrBase`в точку подключения и приемником клиента.|
|[CComPtrBase::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|Вызовите этот метод для создания объекта класса, связанного с указанным Идентификатором класса или идентификатор программы.|
|[CComPtrBase::CopyTo](#copyto)|Вызовите этот метод, чтобы скопировать `CComPtrBase` указатель на другой переменной указателя.|
|[CComPtrBase::Detach](#detach)|Вызовите этот метод для освобождения владения указатель.|
|[CComPtrBase::IsEqualObject](#isequalobject)|Вызовите этот метод для проверки, если указанный `IUnknown` указывает на тот же объект, связанный с `CComPtrBase` объекта.|
|[CComPtrBase::QueryInterface](#queryinterface)|Вызовите этот метод для возврата указателя на указанный интерфейс.|
|[CComPtrBase::Release](#release)|Вызовите этот метод для освобождения интерфейс.|
|[CComPtrBase::SetSite](#setsite)|Вызовите этот метод, чтобы задать для сайта `CComPtrBase` объект `IUnknown` родительского объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CComPtrBase::operator T *](#operator_t_star)|Оператор приведения типов.|
|[CComPtrBase::operator!](#operator_not)|Оператор NOT.|
|[CComPtrBase::operator &](#operator_amp)|& Оператор.|
|[CComPtrBase::operator *](#operator_star)|Оператор \*.|
|[CComPtrBase::operator <](#ccomptrbase__operator lt)|Меньше-оператор «больше».|
|[CComPtrBase::operator ==](#operator_eq_eq)|Оператор равенства.|
|[CComPtrBase::operator "->"](#operator_ptr)|Оператор указателя на элементы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComPtrBase::p](#p)|Указатель данных переменная-член.|

## <a name="remarks"></a>Примечания

Этот класс служит основой для других интеллектуальных указателей, которые используют процедур управления памятью COM, такие как [CComQIPtr](../../atl/reference/ccomqiptr-class.md) и [CComPtr](../../atl/reference/ccomptr-class.md). Производные классы, добавить свои собственные конструкторы и операторы, но полагаться на методы, предоставленные `CComPtrBase`.

## <a name="requirements"></a>Требования

**Заголовок:** atlcomcli.h

##  <a name="advise"></a>  CComPtrBase::Advise

Вызовите этот метод, чтобы создать подключение между `CComPtrBase`в точку подключения и приемником клиента.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
Указатель на клиент `IUnknown`.

*IID*<br/>
Идентификатор GUID точки подключения. Как правило это так же, как выходящего интерфейса, управляемого с использованием точки подключения.

*PDW*<br/>
Указатель на файл cookie, который однозначно идентифицирует соединение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

См. в разделе [AtlAdvise](connection-point-global-functions.md#atladvise) Дополнительные сведения.

##  <a name="attach"></a>  CComPtrBase::Attach

Вызовите этот метод, чтобы стать владельцем существующего указателя.

```
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Параметры

*P2*<br/>
`CComPtrBase` Объект будет стать владельцем этого указателя.

### <a name="remarks"></a>Примечания

`Attach` вызовы [CComPtrBase::Release](#release) в существующем [CComPtrBase::p](#p) переменной-члена, а затем назначает *p2* для `CComPtrBase::p`. Когда `CComPtrBase` объект принимает владение указатель, он будет автоматически вызывать `Release` на указатель, который приведет к удалению указатель и любые выделенных данных, если счетчик ссылок на объект становится равным 0.

##  <a name="dtor"></a>  CComPtrBase:: ~ CComPtrBase

Деструктор

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Примечания

Освобождает интерфейс, на которые указывают `CComPtrBase`.

##  <a name="cocreateinstance"></a>  CComPtrBase::CoCreateInstance

Вызовите этот метод для создания объекта класса, связанного с указанным Идентификатором класса или идентификатор программы.

```
HRESULT CoCreateInstance(
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```

### <a name="parameters"></a>Параметры

*szProgID*<br/>
Указатель на идентификатор ProgID, позволяющий восстановить идентификатор CLSID.

*pUnkOuter*<br/>
Если значение равно NULL, указывает, что объект не создается как часть агрегата. Если не NULL, — это указатель на Агрегатный объект `IUnknown` интерфейс (управляющий `IUnknown`).

*dwClsContext*<br/>
Контекст, в котором будет выполняться код, который управляет вновь созданный объект.

*rclsid*<br/>
CLSID, связанный с данными и кодом, который будет использоваться для создания объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибкой REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING или E_NOINTERFACE в случае сбоя. См. в разделе [CoCreateClassInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance) и [CLSIDFromProgID](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromprogid) описание этих ошибок.

### <a name="remarks"></a>Примечания

Если в первой форме метода вызывается, [CLSIDFromProgID](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromprogid) используется для восстановления CLSID. Затем вызовите обе формы [CoCreateClassInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

В отладочных сборках, произойдет ошибка утверждения, если [CComPtrBase::p](#p) не равно NULL.

##  <a name="copyto"></a>  CComPtrBase::CopyTo

Вызовите этот метод, чтобы скопировать `CComPtrBase` указатель на другой переменной указателя.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Параметры

*ppT*<br/>
Адрес переменной, которая получит `CComPtrBase` указатель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении E_POINTER в случае сбоя.

### <a name="remarks"></a>Примечания

Копирует `CComPtrBase` указатель на *ppT*. Количество ссылок в [CComPtrBase::p](#p) увеличивается переменная-член.

Ошибка HRESULT, будет возвращено в том случае, если *ppT* равен NULL. В отладочных сборках, произойдет ошибка утверждения, если *ppT* равен NULL.

##  <a name="detach"></a>  CComPtrBase::Detach

Вызовите этот метод для освобождения владения указатель.

```
T* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию указателя.

### <a name="remarks"></a>Примечания

Освобождает права владения указателем, задает [CComPtrBase::p](#p) переменной-члена данных значение NULL и возвращает копию указателя.

##  <a name="isequalobject"></a>  CComPtrBase::IsEqualObject

Вызовите этот метод для проверки, если указанный `IUnknown` указывает на тот же объект, связанный с `CComPtrBase` объекта.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Параметры

*pOther*<br/>
Сравниваемый шаблон `IUnknown *`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если объекты идентичны.

##  <a name="operator_not"></a>  CComPtrBase::operator!

Оператор NOT.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если `CComHeapPtr` указатель равен NULL, false в противном случае.

##  <a name="operator_amp"></a>  CComPtrBase::operator &amp;

& Оператор.

```
T** operator&() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес объекта, на которые указывают `CComPtrBase` объекта.

##  <a name="operator_star"></a>  CComPtrBase::operator \*

Оператор \*.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение [CComPtrBase::p](#p); то есть указатель на объект, упоминаемый в `CComPtrBase` объекта.

Если отладочные построения, ошибка возникнет, если [CComPtrBase::p](#p) не равно NULL.

##  <a name="operator_eq_eq"></a>  CComPtrBase::operator ==

Оператор равенства.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Параметры

*pT*<br/>
Указатель на объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если `CComPtrBase` и *pT* указывал тот же объект, значение false в противном случае.

##  <a name="operator_ptr"></a>  CComPtrBase::operator-&gt;

Оператор указателя на член.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение [CComPtrBase::p](#p) переменной-члена данных.

### <a name="remarks"></a>Примечания

Этот оператор используется для вызова метода в классе, на которые указывают `CComPtrBase` объекта. В отладочных сборках, произойдет сбой утверждения, если `CComPtrBase` элемент данных указывает на значение NULL.

##  <a name="operator_lt"></a>  CComPtrBase::operator &lt;

Меньше-оператор «больше».

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Параметры

*pT*<br/>
Указатель на объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если указатель управляет текущий объект меньше, чем указатель, к которому он сравнивается.

##  <a name="operator_t_star"></a>  CComPtrBase::operator T\*

Оператор приведения типов.

```
operator T*() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает указатель на тип данных объекта, определенный в шаблоне класса.

##  <a name="p"></a>  CComPtrBase::p

Указатель данных переменная-член.

```
T* p;
```

### <a name="remarks"></a>Примечания

Эта переменная-член содержит информацию об указателях.

##  <a name="queryinterface"></a>  CComPtrBase::QueryInterface

Вызовите этот метод для возврата указателя на указанный интерфейс.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Параметры

*Q*<br/>
Тип объекта, указатель на интерфейс является обязательным.

*PP*<br/>
Адрес выходной переменной, которая получает указатель на запрошенный интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK в случае успеха или E_NOINTERFACE в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [IUnknown::QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

В отладочных сборках, произойдет ошибка утверждения, если *pp* не равно NULL.

##  <a name="release"></a>  CComPtrBase::Release

Вызовите этот метод для освобождения интерфейс.

```
void Release() throw();
```

### <a name="remarks"></a>Примечания

Интерфейс освобождается, и [CComPtrBase::p](#p) имеет значение NULL.

##  <a name="setsite"></a>  CComPtrBase::SetSite

Вызовите этот метод, чтобы задать для сайта `CComPtrBase` объект `IUnknown` родительского объекта.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Параметры

*punkParent*<br/>
Указатель на `IUnknown` интерфейс родительского элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
