---
title: Класс IDispEventImpl
ms.date: 11/04/2016
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
ms.openlocfilehash: 8de620cd6e2433375284f6493b5117c40a356603
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275325"
---
# <a name="idispeventimpl-class"></a>Класс IDispEventImpl

Этот класс предоставляет реализацию `IDispatch` методы.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```

#### <a name="parameters"></a>Параметры

*nID*<br/>
Уникальный идентификатор для исходного объекта. Когда `IDispEventImpl` является базовым классом для составного элемента управления, используйте идентификатор ресурса для нужного элемента управления в контейнере для этого параметра. В других случаях используйте произвольное целое положительное число.

*T*<br/>
Класс пользователя, который является производным от `IDispEventImpl`.

*pdiid*<br/>
Указатель на идентификатор IID disp-интерфейс событий, реализованные этим классом. Этот интерфейс должен быть определен в библиотеке типов, обозначенное с помощью *plibid*, *wMajor*, и *wMinor*.

*plibid*<br/>
Указатель на библиотеку типов, определяющий интерфейс диспетчеризации, на которые указывают *pdiid*. Если **& GUID_NULL**, будет загрузить библиотеку типов из объекта источника события.

*wMajor*<br/>
Основной номер версии для библиотеки типов. Значение по умолчанию — 0.

*wMinor*<br/>
Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.

*tihclass*<br/>
Класс, используемый для управления сведения о типе *T*. Значение по умолчанию — класс типа `CComTypeInfoHolder`; тем не менее, можно переопределить этот параметр шаблона, предоставляет класс типа, отличные от `CComTypeInfoHolder`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|Класс, используемый для управления сведения о типе. По умолчанию `CComTypeInfoHolder`.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Находит индекс, функции с заданным идентификатором диспетчеризации.|
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Сопоставляет один элемент и необязательный набор имен аргументов соответствующему набору идентификаторов DispId целого числа.|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Извлекает сведения о типе для объекта.|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Возвращает число интерфейсов, сведения о типе.|
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Возвращает базовый тип определяемого пользователем типа.|

## <a name="remarks"></a>Примечания

`IDispEventImpl` предоставляет способ реализации диспетчерский интерфейс событий без необходимости указать код реализации для каждого метода и события в этом интерфейсе. `IDispEventImpl` предоставляет реализацию `IDispatch` методы. Необходимо предоставлять реализации для событий, что вы заинтересованы в обработке.

`IDispEventImpl` работает совместно с картой приемника событий в классе события соответствующим функциям обработки. Чтобы использовать этот класс:

Добавить [SINK_ENTRY](composite-control-macros.md#sink_entry) или [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) макрос для карты приемника событий для каждого события для каждого объекта, который необходимо обработать. При использовании `IDispEventImpl` как базовый класс составного элемента управления, можно вызвать [AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap) для установления подключения и отключения с источниками событий для всех записей событий приемника карты. В других случаях, или для большего контроля, вызовите [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) для установления соединения между исходным объектом и базовый класс. Вызовите [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) Чтобы разорвать подключение.

Должен быть производным от `IDispEventImpl` (с помощью уникальное значение для *nID*) для каждого объекта, для которого требуется для обработки событий. Можно повторно использовать базовый класс, unadvising от одного исходного объекта, затем о том, с объектом другого источника, но максимальное число объектов источника, которые могут обрабатываться одновременно в одном объекте ограничивается число `IDispEventImpl` базовых классов.

`IDispEventImpl` предоставляет те же функции, что [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), за исключением того, он возвращает сведения о типе об интерфейсе из библиотеки типов, вместо того, он предоставлен как указатель на [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) Структура. Используйте `IDispEventSimpleImpl` при не имеют библиотеку типов, описывающие интерфейса событий или хотите избежать издержек, связанных с использованием библиотеки типов.

> [!NOTE]
> `IDispEventImpl` и `IDispEventSimpleImpl` предоставляют свою собственную реализацию `IUnknown::QueryInterface` включение каждого `IDispEventImpl` и `IDispEventSimpleImpl` базового класса в качестве отдельного удостоверения COM по-прежнему предоставляя прямой доступ к членам класса в основной COM-объект.

Реализация CE ATL ActiveX событий приемники только поддерживает возвращаемого значения типа HRESULT или void из методов обработчика событий; Возвращаемое значение не поддерживается, и его поведение не определено.

Дополнительные сведения см. в разделе [поддержка IDispEventImpl](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="getfuncinfofromid"></a>  IDispEventImpl::GetFuncInfoFromId

Находит индекс, функции с заданным идентификатором диспетчеризации.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Ссылка на идентификатор функции.

*dispidMember*<br/>
[in] Идентификатор диспетчера функции.

*lcid*<br/>
[in] Контекст языкового идентификатора функции.

*Сведения о*<br/>
[in] Структура, указывающее, как эта функция вызывается.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="getidsofnames"></a>  IDispEventImpl::GetIDsOfNames

Сопоставляет один элемент и необязательный набор имена аргументов с соответствующим набором целого числа DispId, которые могут использоваться при последующих вызовах [IDispatch::Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke).

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Примечания

См. в разделе [IDispatch::GetIdsOfNames расширенное](/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) в Windows SDK.

##  <a name="gettypeinfo"></a>  IDispEventImpl::GetTypeInfo

Возвращает сведения о типе объекта, которые затем могут использоваться для получения сведений о типе интерфейса.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Примечания

##  <a name="gettypeinfocount"></a>  IDispEventImpl::GetTypeInfoCount

Возвращает количество предоставляемых объектом интерфейсов для доступа к сведениям о типе (0 или 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Примечания

См. в разделе [IDispatch::GetTypeInfoCount](/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) в Windows SDK.

##  <a name="getuserdefinedtype"></a>  IDispEventImpl::GetUserDefinedType

Возвращает базовый тип определяемого пользователем типа.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>Параметры

*pTI*<br/>
[in] Указатель на [ITypeInfo](/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) интерфейса, содержащего определяемый пользователем тип.

*hrt*<br/>
[in] Дескриптор для описания типа, который требуется получить.

### <a name="return-value"></a>Возвращаемое значение

Тип variant.

### <a name="remarks"></a>Примечания

См. в разделе [ITypeInfo::GetRefTypeInfo](/windows/desktop/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo).

##  <a name="idispeventimpl"></a>  IDispEventImpl::IDispEventImpl

Конструктор. Сохраняет значения параметров шаблона класса *plibid*, *pdiid*, *wMajor*, и *wMinor*.

```
IDispEventImpl();
```

##  <a name="tihclass"></a>  IDispEventImpl::tihclass

Это определение типа является экземпляром класса параметр шаблона класса *tihclass*.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>Примечания

По умолчанию класс является `CComTypeInfoHolder`. `CComTypeInfoHolder` Управляет сведения о типе для класса.

## <a name="see-also"></a>См. также

[Структура _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)<br/>
[Класс IDispatchImpl](../../atl/reference/idispatchimpl-class.md)<br/>
[Класс IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
