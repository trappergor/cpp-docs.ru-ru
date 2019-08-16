---
title: Класс Ккомптрбасе
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
ms.openlocfilehash: 689221ec77b21fc8bfaed2e929aee5402a4bc676
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496976"
---
# <a name="ccomptrbase-class"></a>Класс Ккомптрбасе

Этот класс предоставляет базу для классов интеллектуальных указателей, использующих подпрограммы памяти на основе COM.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, на который ссылается интеллектуальный указатель.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ккомптрбасе:: ~ Ккомптрбасе](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккомптрбасе:: Advise](#advise)|Вызовите этот метод, чтобы создать соединение между `CComPtrBase`точкой подключения и приемником клиента.|
|[CComPtrBase::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|
|[Ккомптрбасе:: CoCreateInstance](#cocreateinstance)|Вызовите этот метод, чтобы создать объект класса, связанный с указанным ИДЕНТИФИКАТОРом класса или ИДЕНТИФИКАТОРом программы.|
|[Ккомптрбасе:: CopyTo](#copyto)|Вызовите этот метод, чтобы `CComPtrBase` скопировать указатель на другую переменную указателя.|
|[Ккомптрбасе::D етач](#detach)|Вызовите этот метод, чтобы освободить владение указателем.|
|[Ккомптрбасе:: Исекуалобжект](#isequalobject)|Вызовите этот метод, чтобы проверить, `IUnknown` указывают ли указанные точки на один и тот `CComPtrBase` же объект, связанный с объектом.|
|[Ккомптрбасе:: QueryInterface](#queryinterface)|Вызовите этот метод, чтобы вернуть указатель на указанный интерфейс.|
|[CComPtrBase::Release](#release)|Вызовите этот метод, чтобы освободить интерфейс.|
|[Ккомптрбасе:: SetSite](#setsite)|Вызовите этот метод, чтобы задать сайт `CComPtrBase` объекта `IUnknown` для родительского объекта.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Ккомптрбасе:: operator T *](#operator_t_star)|Оператор CAST.|
|[Ккомптрбасе:: operator!](#operator_not)|Оператор NOT.|
|[Ккомптрбасе:: operator &](#operator_amp)|Оператор &.|
|[Ккомптрбасе:: operator *](#operator_star)|Оператор \*.|
|[Ккомптрбасе:: operator <](#ccomptrbase__operator lt)|Оператор "меньше чем".|
|[Ккомптрбасе:: operator = =](#operator_eq_eq)|Оператор равенства.|
|[Ккомптрбасе:: operator — >](#operator_ptr)|Оператор указателя на члены.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Ккомптрбасе::p](#p)|Переменная члена данных указателя.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет базу для других смарт-указателей, использующих подпрограммы управления памятью COM, такие как [CComQIPtr](../../atl/reference/ccomqiptr-class.md) и [CComPtr](../../atl/reference/ccomptr-class.md). Производные классы добавляют собственные конструкторы и операторы, но используют методы, предоставляемые `CComPtrBase`.

## <a name="requirements"></a>Требования

**Заголовок:** atlcomcli. h

##  <a name="advise"></a>Ккомптрбасе:: Advise

Вызовите этот метод, чтобы создать соединение между `CComPtrBase`точкой подключения и приемником клиента.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
Указатель на клиентский `IUnknown`объект.

*IID*<br/>
Идентификатор GUID точки подключения. Как правило, это то же самое, что и исходящий интерфейс, управляемый точкой подключения.

*альтернатив*<br/>
Указатель на файл cookie, который однозначно определяет соединение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [атладвисе](connection-point-global-functions.md#atladvise) .

##  <a name="attach"></a>Ккомптрбасе:: Attach

Вызовите этот метод, чтобы стать владельцем существующего указателя.

```
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Параметры

*–*<br/>
`CComPtrBase` Объект будет становиться владельцем этого указателя.

### <a name="remarks"></a>Примечания

`Attach`вызывает [ккомптрбасе:: Release](#release) для существующей переменной члена [ккомптрбасе::p](#p) , а затем присваивает *P2* значение `CComPtrBase::p`. Когда объект становится владельцем указателя, он автоматически вызывается `Release` по указателю, который удаляет указатель и все выделенные данные, если счетчик ссылок на объект переходит в 0. `CComPtrBase`

##  <a name="dtor"></a>Ккомптрбасе:: ~ Ккомптрбасе

Деструктор

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Примечания

Освобождает интерфейс, `CComPtrBase`на который указывает.

##  <a name="cocreateinstance"></a>Ккомптрбасе:: CoCreateInstance

Вызовите этот метод, чтобы создать объект класса, связанный с указанным ИДЕНТИФИКАТОРом класса или ИДЕНТИФИКАТОРом программы.

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

*сзпрогид*<br/>
Указатель на идентификатор ProgID, используемый для восстановления идентификатора CLSID.

*пункаутер*<br/>
Если значение — NULL, указывает, что объект не создается как часть агрегатной функции. Если значение не равно null, то является указателем на `IUnknown` интерфейс агрегатного объекта (Управление `IUnknown`).

*двклсконтекст*<br/>
Контекст, в котором будет выполняться код, управляющий только что созданным объектом.

*рклсид*<br/>
CLSID, связанный с данными и кодом, который будет использоваться для создания объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении, или REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING или E_NOINTERFACE при сбое. Описание этих ошибок см. в разделе [кокреатеклассинстанце](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) и [клсидфромпрогид](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) .

### <a name="remarks"></a>Примечания

Если вызывается первая форма метода, [клсидфромпрогид](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) используется для восстановления идентификатора CLSID. Затем обе формы вызывают [кокреатеклассинстанце](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

В отладочных сборках возникнет ошибка утверждения, если [ккомптрбасе::p](#p) не равно null.

##  <a name="copyto"></a>Ккомптрбасе:: CopyTo

Вызовите этот метод, чтобы `CComPtrBase` скопировать указатель на другую переменную указателя.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Параметры

*PowerPoint*<br/>
Адрес переменной, которая получит `CComPtrBase` указатель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении, E_POINTER при сбое.

### <a name="remarks"></a>Примечания

Копирует указатель на *PPT.* `CComPtrBase` Счетчик ссылок на переменную-член [ккомптрбасе::p](#p) увеличивается.

Если *PPT* имеет значение null, будет возвращено сообщение об ошибке HRESULT. В отладочных сборках возникнет ошибка утверждения, если *PPT* имеет значение null.

##  <a name="detach"></a>Ккомптрбасе::D етач

Вызовите этот метод, чтобы освободить владение указателем.

```
T* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию указателя.

### <a name="remarks"></a>Примечания

Освобождает владение указателем, задает для переменной-члена [ккомптрбасе::p](#p) данных значение NULL и возвращает копию указателя.

##  <a name="isequalobject"></a>Ккомптрбасе:: Исекуалобжект

Вызовите этот метод, чтобы проверить, `IUnknown` указывают ли указанные точки на один и тот `CComPtrBase` же объект, связанный с объектом.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Параметры

*посер*<br/>
Сравниваемый шаблон `IUnknown *`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если объекты идентичны, и false в противном случае.

##  <a name="operator_not"></a>Ккомптрбасе:: operator!

Оператор NOT.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, `CComHeapPtr` если указатель равен null, и false в противном случае.

##  <a name="operator_amp"></a>Ккомптрбасе:: operator&amp;

Оператор &.

```
T** operator&() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес объекта, `CComPtrBase` на который указывает объект.

##  <a name="operator_star"></a>Ккомптрбасе:: operator\*

Оператор \*.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение [ккомптрбасе::p](#p); то есть указатель на объект, на который ссылается `CComPtrBase` объект.

При отладочной сборке возникнет ошибка утверждения, если [ккомптрбасе::p](#p) не равно null.

##  <a name="operator_eq_eq"></a>Ккомптрбасе:: operator = =

Оператор равенства.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Параметры

*Лутор*<br/>
Указатель на объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает true, `CComPtrBase` если и *PT* указывают на один и тот же объект; в противном случае — значение false.

##  <a name="operator_ptr"></a>Ккомптрбасе:: operator —&gt;

Оператор указателя на член.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение переменной элемента данных [ккомптрбасе::p](#p) .

### <a name="remarks"></a>Примечания

Этот оператор используется для вызова метода в классе, на `CComPtrBase` который указывает объект. В отладочных сборках произойдет сбой утверждения, если `CComPtrBase` элемент данных указывает на значение null.

##  <a name="operator_lt"></a>Ккомптрбасе:: operator&lt;

Оператор "меньше чем".

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Параметры

*Лутор*<br/>
Указатель на объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если указатель, управляемый текущим объектом, меньше, чем указатель, на который выполняется сравнение.

##  <a name="operator_t_star"></a>Ккомптрбасе:: operator T\*

Оператор CAST.

```
operator T*() const throw();
```

### <a name="remarks"></a>Примечания

Возвращает указатель на тип данных Object, определенный в шаблоне класса.

##  <a name="p"></a>Ккомптрбасе::p

Переменная члена данных указателя.

```
T* p;
```

### <a name="remarks"></a>Примечания

Эта переменная члена содержит сведения об указателе.

##  <a name="queryinterface"></a>Ккомптрбасе:: QueryInterface

Вызовите этот метод, чтобы вернуть указатель на указанный интерфейс.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Параметры

*Q*<br/>
Тип объекта, указатель интерфейса которого требуется.

*PP*<br/>
Адрес выходной переменной, которая получает запрошенный указатель интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или E_NOINTERFACE при сбое.

### <a name="remarks"></a>Примечания

Этот метод вызывает [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

В отладочных сборках возникнет ошибка утверждения, если *PP* не равно null.

##  <a name="release"></a>Ккомптрбасе:: Release

Вызовите этот метод, чтобы освободить интерфейс.

```
void Release() throw();
```

### <a name="remarks"></a>Примечания

Интерфейс освобожден, и [ккомптрбасе::p](#p) имеет значение null.

##  <a name="setsite"></a>Ккомптрбасе:: SetSite

Вызовите этот метод, чтобы задать сайт `CComPtrBase` объекта `IUnknown` для родительского объекта.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Параметры

*пункпарент*<br/>
Указатель на `IUnknown` интерфейс родителя.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Этот метод вызывает [атлсетчилдсите](composite-control-global-functions.md#atlsetchildsite).

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
