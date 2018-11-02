---
title: Класс IQuickActivateImpl
ms.date: 11/04/2016
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
ms.openlocfilehash: 5dacdd4986580ca665d2199568584faafa8d6699
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560814"
---
# <a name="iquickactivateimpl-class"></a>Класс IQuickActivateImpl

Этот класс объединяет инициализации элемента управления контейнеры в один вызов.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IQuickActivateImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Извлекает текущий размер изображения для выполнения элемента управления.|
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Выполняет быстрый инициализацию загружаемых элементов управления.|
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Информирует элемент управления контейнера, были назначены какой объем места на экране.|

## <a name="remarks"></a>Примечания

[IQuickActivate](/windows/desktop/api/ocidl/nn-ocidl-iquickactivate) интерфейс помогает избежать задержек при загрузке элементов управления путем объединения инициализации в одном вызове контейнеры. `QuickActivate` Метод позволяет контейнеру передавать указатель на [QACONTAINER](/windows/desktop/api/ocidl/ns-ocidl-tagqacontainer) требуется структура, которая хранит указатели на все интерфейсы управления. При возвращении управления передает указатель на [QACONTROL](/windows/desktop/api/ocidl/ns-ocidl-tagqacontrol) структуру, которая хранит указатели на собственных интерфейсов, которые используются в качестве контейнера. Класс `IQuickActivateImpl` предоставляет реализацию по умолчанию `IQuickActivate` и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="getcontentextent"></a>  IQuickActivateImpl::GetContentExtent

Извлекает текущий размер изображения для выполнения элемента управления.

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Примечания

Размер для полной подготовки к просмотру элемента управления и указывается в единицах HIMETRIC.

См. в разделе [IQuickActivate::GetContentExtent](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) в Windows SDK.

##  <a name="quickactivate"></a>  IQuickActivateImpl::QuickActivate

Выполняет быстрый инициализацию загружаемых элементов управления.

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>Примечания

Эта структура содержит указатели на интерфейсы, необходимые для управления и значения некоторых свойств окружения. При возврате управления передает указатель на [QACONTROL](/windows/desktop/api/ocidl/ns-ocidl-tagqacontrol) структуру, которая содержит указатели на собственных интерфейсов, необходимых для контейнера, а также дополнительные сведения о состоянии.

См. в разделе [IQuickActivate::QuickActivate](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-quickactivate) в Windows SDK.

##  <a name="setcontentextent"></a>  IQuickActivateImpl::SetContentExtent

Информирует элемент управления контейнера, были назначены какой объем места на экране.

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Примечания

Размер указывается в единицах HIMETRIC.

См. в разделе [IQuickActivate::SetContentExtent](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
