---
title: Класс Иобжектвисситеимпл
ms.date: 11/04/2016
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
ms.openlocfilehash: e857f739e3ff7235c473e99abbef6aab0d3f4205
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495831"
---
# <a name="iobjectwithsiteimpl-class"></a>Класс Иобжектвисситеимпл

Этот класс предоставляет методы, позволяющие объекту взаимодействовать с его сайтом.

## <a name="syntax"></a>Синтаксис

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IObjectWithSiteImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Иобжектвисситеимпл::-сайт](#getsite)|Запрашивает у сайта указатель интерфейса.|
|[Иобжектвисситеимпл:: Сетчилдсите](#setchildsite)|Предоставляет объект с `IUnknown` указателем сайта.|
|[Иобжектвисситеимпл:: SetSite](#setsite)|Предоставляет объект с `IUnknown` указателем сайта.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Иобжектвисситеимпл:: m_spUnkSite](#m_spunksite)|Управляет `IUnknown` указателем сайта.|

## <a name="remarks"></a>Примечания

Интерфейс [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) позволяет объекту взаимодействовать с его сайтом. Класс `IObjectWithSiteImpl` предоставляет реализацию этого интерфейса по умолчанию и реализует `IUnknown` , отправляя сведения в устройство дампа в отладочных сборках.

`IObjectWithSiteImpl`задает два метода. Сначала клиент вызывает `SetSite`, передавая `IUnknown` указатель сайта. Этот указатель хранится в объекте и затем может быть извлечен с помощью вызова `GetSite`.

Как правило, класс является производным от `IObjectWithSiteImpl` при создании объекта, который не является элементом управления. Для элементов управления следует наследовать класс от [иолеобжектимпл](../../atl/reference/ioleobjectimpl-class.md), который также предоставляет указатель сайта. Не наследовать класс от `IObjectWithSiteImpl` и. `IOleObjectImpl`

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="getsite"></a>Иобжектвисситеимпл::-сайт

Запрашивает у сайта указатель на интерфейс, указанный `riid`в.

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>Примечания

Если сайт поддерживает этот интерфейс, указатель возвращается через `ppvSite`. `ppvSite` В противном случае устанавливается значение null.

См. раздел [IObjectWithSite::-site](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) в Windows SDK.

##  <a name="m_spunksite"></a>Иобжектвисситеимпл:: m_spUnkSite

Управляет `IUnknown` указателем сайта.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>Примечания

`m_spUnkSite`изначально получает этот указатель через вызов [SetSite](#setsite).

##  <a name="setchildsite"></a>Иобжектвисситеимпл:: Сетчилдсите

Предоставляет объект с `IUnknown` указателем сайта.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>Параметры

*пунксите*<br/>
окне Указатель на `IUnknown` указатель интерфейса сайта, управляющего этим объектом. Если значение равно null, объект должен `IUnknown::Release` вызывать на любом существующем сайте, где объект больше не знает свой сайт.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="setsite"></a>Иобжектвисситеимпл:: SetSite

Предоставляет объект с `IUnknown` указателем сайта.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>Примечания

См. раздел [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) в Windows SDK.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
