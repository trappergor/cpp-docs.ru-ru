---
title: Класс IDispEventSimpleImpl
ms.date: 11/04/2016
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
ms.openlocfilehash: 3ceb436e4f20a17ecd086fb68f9c1cfdcbe0be3e
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423084"
---
# <a name="idispeventsimpleimpl-class"></a>Класс IDispEventSimpleImpl

Этот класс предоставляет реализации методов `IDispatch`, не получая информацию о типах из библиотеки типов.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <UINT nID, class T, const IID* pdiid>
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```

#### <a name="parameters"></a>Параметры

*nID*<br/>
Уникальный идентификатор исходного объекта. Если `IDispEventSimpleImpl` является базовым классом для составного элемента управления, используйте идентификатор ресурса нужного вложенного элемента управления для этого параметра. В других случаях используйте произвольное положительное целое число.

*T*<br/>
Класс пользователя, производный от `IDispEventSimpleImpl`.

*пдиид*<br/>
Указатель на идентификатор IID интерфейса обработчика событий, реализованного этим классом.

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[IDispEventSimpleImpl:: Advise](#advise)|Устанавливает соединение с источником событий по умолчанию.|
|[IDispEventSimpleImpl::D Испевентадвисе](#dispeventadvise)|Устанавливает соединение с источником событий.|
|[IDispEventSimpleImpl::D Испевентунадвисе](#dispeventunadvise)|Прерывает соединение с источником событий.|
|[IDispEventSimpleImpl:: GetIDsOfNames](#getidsofnames)|Возвращает E_NOTIMPL.|
|[IDispEventSimpleImpl:: GetTypeInfo](#gettypeinfo)|Возвращает E_NOTIMPL.|
|[IDispEventSimpleImpl:: Жеттипеинфокаунт](#gettypeinfocount)|Возвращает E_NOTIMPL.|
|[IDispEventSimpleImpl:: Invoke](#invoke)|Вызывает обработчики событий, перечисленные в сопоставлении приемника событий.|
|[IDispEventSimpleImpl:: unadvise](#unadvise)|Разрыв соединения с источником событий по умолчанию.|

## <a name="remarks"></a>Remarks

`IDispEventSimpleImpl` предоставляет способ реализации интерфейса событий, не требуя предоставления кода реализации для каждого метода или события в этом интерфейсе. `IDispEventSimpleImpl` предоставляет реализации методов `IDispatch`. Необходимо предоставить только реализации для событий, которые вы хотите обработать.

`IDispEventSimpleImpl` работает в сочетании с картой приемника событий в классе для маршрутизации событий в соответствующую функцию обработчика. Чтобы использовать этот класс, сделайте следующее:

- Добавьте [SINK_ENTRY_INFOный](composite-control-macros.md#sink_entry_info) макрос в карту приемников событий для каждого события в каждом объекте, который требуется обменять.

- Предоставьте сведения о типе для каждого события, передав указатель на структуру [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) в качестве параметра каждой записи. На платформе x86 значение `_ATL_FUNC_INFO.cc` должно быть CC_CDECL с вызовом метода __stdcall в функции обратного вызова.

- Вызовите [диспевентадвисе](#dispeventadvise) , чтобы установить соединение между исходным объектом и базовым классом.

- Вызовите [диспевентунадвисе](#dispeventunadvise) , чтобы разорвать соединение.

Необходимо создать производный от `IDispEventSimpleImpl` (с использованием уникального значения для *NID*) для каждого объекта, для которого необходимо выполнять обработку событий. Можно повторно использовать базовый класс, не предзначая по одному исходному объекту, в то же время предустановив для другого исходного объекта, но максимальное количество исходных объектов, которые могут обрабатываться одним объектом за один раз, ограничено числом `IDispEventSimpleImpl` базовых классов.

`IDispEventSimplImpl` предоставляет те же функциональные возможности, что и [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), за исключением того, что она не получает сведений о типе интерфейса из библиотеки типов. Мастера создают код на основе только `IDispEventImpl`, но вы можете использовать `IDispEventSimpleImpl`, добавив код вручную. Используйте `IDispEventSimpleImpl`, если у вас нет библиотеки типов, описывающей интерфейс событий, или необходимо избежать издержек, связанных с использованием библиотеки типов.

> [!NOTE]
> `IDispEventImpl` и `IDispEventSimpleImpl` предоставляют собственную реализацию `IUnknown::QueryInterface` позволяя каждому `IDispEventImpl` или `IDispEventSimpleImpl` базовому классу работать как с отдельным COM-удостоверением и по-прежнему разрешать прямой доступ к членам класса в основном COM-объекте.

Реализация приемников событий ActiveX в CE ATL поддерживает только возвращаемые значения типа HRESULT или void из методов обработчика событий. любое другое возвращаемое значение не поддерживается, и его поведение не определено.

Дополнительные сведения см. в разделе [Поддержка IDispEventImpl](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_IDispEvent`

`_IDispEventLocator`

`IDispEventSimpleImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="advise"></a>IDispEventSimpleImpl:: Advise

Вызовите этот метод, чтобы установить соединение с источником событий, представленным *Punk*.

```
HRESULT Advise(IUnknown* pUnk);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
окне Указатель на интерфейс `IUnknown` объекта источника события.

### <a name="return-value"></a>Возвращаемое значение

S_OK или любое значение HRESULT сбоя.

### <a name="remarks"></a>Remarks

После установления соединения события, инициируемые из *Punk* , будут направляться в обработчики в классе посредством схемы приемника событий.

> [!NOTE]
>  Если класс является производным от нескольких `IDispEventSimpleImpl` классов, необходимо устранить неоднозначность вызовов этого метода путем определения области вызова с определенным базовым классом, который вас интересует.

`Advise` устанавливает соединение с источником событий по умолчанию, он получает идентификатор IID источника событий по умолчанию для объекта, определенного параметром [атлжетобжектсаурцеинтерфаце](composite-control-global-functions.md#atlgetobjectsourceinterface).

##  <a name="dispeventadvise"></a>IDispEventSimpleImpl::D Испевентадвисе

Вызовите этот метод, чтобы установить соединение с источником событий, представленным *Punk*.

```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
окне Указатель на интерфейс `IUnknown` объекта источника события.

*пиид*<br/>
Указатель на идентификатор IID объекта источника события.

### <a name="return-value"></a>Возвращаемое значение

S_OK или любое значение HRESULT сбоя.

### <a name="remarks"></a>Remarks

В дальнейшем события, запускаемые из *Punk* , будут направляться в обработчики в классе посредством схемы приемника событий.

> [!NOTE]
>  Если класс является производным от нескольких `IDispEventSimpleImpl` классов, необходимо устранить неоднозначность вызовов этого метода путем определения области вызова с определенным базовым классом, который вас интересует.

`DispEventAdvise` устанавливает соединение с источником событий, указанным в `pdiid`.

##  <a name="dispeventunadvise"></a>IDispEventSimpleImpl::D Испевентунадвисе

Прерывает соединение с источником событий, представленным *Punk*.

```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
окне Указатель на интерфейс `IUnknown` объекта источника события.

*пиид*<br/>
Указатель на идентификатор IID объекта источника события.

### <a name="return-value"></a>Возвращаемое значение

S_OK или любое значение HRESULT сбоя.

### <a name="remarks"></a>Remarks

После разрыва соединения события больше не будут направляться в функции обработчика, перечисленные в карте приемника событий.

> [!NOTE]
>  Если класс является производным от нескольких `IDispEventSimpleImpl` классов, необходимо устранить неоднозначность вызовов этого метода путем определения области вызова с определенным базовым классом, который вас интересует.

`DispEventAdvise` прерывает подключение, установленное с источником событий, указанным в `pdiid`.

##  <a name="getidsofnames"></a>IDispEventSimpleImpl:: GetIDsOfNames

Эта реализация `IDispatch::GetIDsOfNames` возвращает E_NOTIMPL.

```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```

### <a name="remarks"></a>Remarks

См. раздел [IDispatch:: GetIdsOfNames](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) в Windows SDK.

##  <a name="gettypeinfo"></a>IDispEventSimpleImpl:: GetTypeInfo

Эта реализация `IDispatch::GetTypeInfo` возвращает E_NOTIMPL.

```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```

### <a name="remarks"></a>Remarks

См. раздел [IDispatch:: GetTypeInfo](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo) в Windows SDK.

##  <a name="gettypeinfocount"></a>IDispEventSimpleImpl:: Жеттипеинфокаунт

Эта реализация `IDispatch::GetTypeInfoCount` возвращает E_NOTIMPL.

```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```

### <a name="remarks"></a>Remarks

См. раздел [IDispatch:: жеттипеинфокаунт](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) в Windows SDK.

##  <a name="invoke"></a>IDispEventSimpleImpl:: Invoke

Эта реализация `IDispatch::Invoke` вызывает обработчики событий, перечисленные в сопоставлении приемника событий.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```

### <a name="remarks"></a>Remarks

См. раздел [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke).

##  <a name="unadvise"></a>IDispEventSimpleImpl:: unadvise

Прерывает соединение с источником событий, представленным *Punk*.

```
HRESULT Unadvise(IUnknown* pUnk);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
окне Указатель на интерфейс `IUnknown` объекта источника события.

### <a name="return-value"></a>Возвращаемое значение

S_OK или любое значение HRESULT сбоя.

### <a name="remarks"></a>Remarks

После разрыва соединения события больше не будут направляться в функции обработчика, перечисленные в карте приемника событий.

> [!NOTE]
>  Если класс является производным от нескольких `IDispEventSimpleImpl` классов, необходимо устранить неоднозначность вызовов этого метода путем определения области вызова с определенным базовым классом, который вас интересует.

`Unadvise` прерывает подключение, установленное с источником событий по умолчанию, указанным в `pdiid`.

`Unavise` прерывает подключение к источнику событий по умолчанию, оно получает идентификатор IID источника событий по умолчанию для объекта, определенного параметром [атлжетобжектсаурцеинтерфаце](composite-control-global-functions.md#atlgetobjectsourceinterface).

## <a name="see-also"></a>См. также раздел

[Структура _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)<br/>
[Класс IDispatchImpl](../../atl/reference/idispatchimpl-class.md)<br/>
[Класс IDispEventImpl](../../atl/reference/idispeventimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
