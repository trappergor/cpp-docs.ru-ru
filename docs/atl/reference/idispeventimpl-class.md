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
ms.openlocfilehash: e82a397b6d2abb66f773908c72a287c979e5ae1d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495933"
---
# <a name="idispeventimpl-class"></a>Класс IDispEventImpl

Этот класс предоставляет реализации `IDispatch` методов.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

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
Уникальный идентификатор исходного объекта. Если `IDispEventImpl` является базовым классом для составного элемента управления, используйте идентификатор ресурса нужного вложенного элемента управления для этого параметра. В других случаях используйте произвольное положительное целое число.

*T*<br/>
Класс пользователя, производный от `IDispEventImpl`.

*пдиид*<br/>
Указатель на идентификатор IID интерфейса обработчика событий, реализованного этим классом. Этот интерфейс должен быть определен в библиотеке типов, обозначенной *плибид*, *вмажор*и *вминор*.

*плибид*<br/>
Указатель на библиотеку типов, определяющий интерфейс диспетчеризации, на который указывает *пдиид*. Если **&AMP; GUID_NULL**, Библиотека типов будет загружена из объекта, который выберет события.

*вмажор*<br/>
Основной номер версии для библиотеки типов. Значение по умолчанию — 0.

*вминор*<br/>
Дополнительный номер версии для библиотеки типов. Значение по умолчанию — 0.

*тихкласс*<br/>
Класс, используемый для управления сведениями о типе для *T*. Значение по умолчанию — класс типа `CComTypeInfoHolder`; однако этот параметр шаблона можно переопределить, предоставив класс типа, отличный от. `CComTypeInfoHolder`

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|[IDispEventImpl:: _tihclass](../../atl/reference/idispeventimpl-class.md)|Класс, используемый для управления сведениями о типе. По умолчанию `CComTypeInfoHolder`.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[IDispEventImpl:: IDispEventImpl](#idispeventimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IDispEventImpl:: ЖетфунЦинфофромид](#getfuncinfofromid)|Находит индекс функции для указанного идентификатора диспетчеризации.|
|[IDispEventImpl:: GetIDsOfNames](#getidsofnames)|Сопоставляет один элемент и необязательный набор имен аргументов с соответствующим набором целочисленных идентификаторов DISPID.|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Извлекает сведения о типе для объекта.|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Извлекает число интерфейсов сведений о типе.|
|[IDispEventImpl:: Жетусердефинедтипе](#getuserdefinedtype)|Возвращает базовый тип определяемого пользователем типа.|

## <a name="remarks"></a>Примечания

`IDispEventImpl`предоставляет способ реализации интерфейса событий, не требуя предоставления кода реализации для каждого метода или события в этом интерфейсе. `IDispEventImpl`предоставляет реализации `IDispatch` методов. Необходимо предоставить только реализации для событий, которые вы хотите обработать.

`IDispEventImpl`работает в сочетании с картой приемника событий в классе для маршрутизации событий в соответствующую функцию обработчика. Чтобы использовать этот класс, сделайте следующее:

Добавьте макрос [SINK_ENTRY](composite-control-macros.md#sink_entry) или [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) в карту приемников событий для каждого события в каждом объекте, который необходимо обменять. При использовании `IDispEventImpl` в качестве базового класса составного элемента управления можно вызвать [атладвисесинкмап](connection-point-global-functions.md#atladvisesinkmap) , чтобы установить и разорвать соединение с источниками событий для всех записей в карте приемника событий. В других случаях или для более высокого контроля вызовите [диспевентадвисе](idispeventsimpleimpl-class.md#dispeventadvise) , чтобы установить соединение между исходным объектом и базовым классом. Вызовите [диспевентунадвисе](idispeventsimpleimpl-class.md#dispeventunadvise) , чтобы разорвать соединение.

Для каждого объекта, для `IDispEventImpl` которого необходимо выполнять обработку событий, необходимо создать производный от (с помощью уникального значения для *NID*). Можно повторно использовать базовый класс, отменив его на один исходный объект, а затем добавив к другому исходному объекту, но максимальное количество исходных объектов, которые могут обрабатываться одним объектом за один раз, ограничено числом `IDispEventImpl` базовых классов.

`IDispEventImpl`предоставляет те же функциональные возможности, что и [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), за исключением того, что она получает сведения о типе интерфейса из библиотеки типов, а не предоставляет ее в качестве указателя на структуру [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) . Используйте `IDispEventSimpleImpl` , если у вас нет библиотеки типов, описывающей интерфейс событий, или необходимо избежать издержек, связанных с использованием библиотеки типов.

> [!NOTE]
> `IDispEventImpl`и `IDispEventSimpleImpl` предоставляют собственные `IUnknown::QueryInterface` реализации, позволяющие каждому `IDispEventImpl` и `IDispEventSimpleImpl` базовому классу действовать как отдельное удостоверение com, при этом разрешая прямой доступ к членам класса в основном COM-объекте.

Реализация приемников событий ActiveX в CE ATL поддерживает только возвращаемые значения типа HRESULT или void из методов обработчика событий. любое другое возвращаемое значение не поддерживается, и его поведение не определено.

Дополнительные сведения см. в разделе [Поддержка IDispEventImpl](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="getfuncinfofromid"></a>IDispEventImpl:: ЖетфунЦинфофромид

Находит индекс функции для указанного идентификатора диспетчеризации.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Ссылка на идентификатор функции.

*диспидмембер*<br/>
окне Идентификатор диспетчеризации функции.

*lcid*<br/>
окне Контекст языкового стандарта для идентификатора функции.

*контактные*<br/>
окне Структура, указывающая, как вызывается функция.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="getidsofnames"></a>IDispEventImpl:: GetIDsOfNames

Сопоставляет один элемент и необязательный набор имен аргументов с соответствующим набором целочисленных идентификаторов DISPID, которые могут использоваться при последующих вызовах [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke).

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Примечания

См. раздел [IDispatch:: GetIdsOfNames](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) в Windows SDK.

##  <a name="gettypeinfo"></a>IDispEventImpl:: GetTypeInfo

Возвращает сведения о типе объекта, которые затем могут использоваться для получения сведений о типе интерфейса.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Примечания

##  <a name="gettypeinfocount"></a>IDispEventImpl:: Жеттипеинфокаунт

Возвращает количество предоставляемых объектом интерфейсов для доступа к сведениям о типе (0 или 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Примечания

См. раздел [IDispatch:: жеттипеинфокаунт](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) в Windows SDK.

##  <a name="getuserdefinedtype"></a>IDispEventImpl:: Жетусердефинедтипе

Возвращает базовый тип определяемого пользователем типа.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>Параметры

*пти*<br/>
окне Указатель на интерфейс [ITypeInfo](/windows/win32/api/oaidl/nn-oaidl-itypeinfo) , содержащий определяемый пользователем тип.

*хрт*<br/>
окне Описатель извлекаемого описания типа.

### <a name="return-value"></a>Возвращаемое значение

Тип Variant.

### <a name="remarks"></a>Примечания

См. раздел [ITypeInfo:: GetRefTypeInfo](/windows/win32/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo).

##  <a name="idispeventimpl"></a>IDispEventImpl:: IDispEventImpl

Конструктор. Сохраняет значения параметров шаблона класса *плибид*, *пдиид*, *вмажор*и *вминор*.

```
IDispEventImpl();
```

##  <a name="tihclass"></a>IDispEventImpl:: тихкласс

Это определение типа является экземпляром параметра-шаблона класса *тихкласс*.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>Примечания

По умолчанию класс имеет `CComTypeInfoHolder`значение. `CComTypeInfoHolder`управляет сведениями о типе для класса.

## <a name="see-also"></a>См. также

[Структура _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)<br/>
[Класс IDispatchImpl](../../atl/reference/idispatchimpl-class.md)<br/>
[Класс IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
