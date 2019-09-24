---
title: Класс Икуиккактиватеимпл
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
ms.openlocfilehash: 2169686ebbf756c5caf9232f5031532c62ac8265
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495506"
---
# <a name="iquickactivateimpl-class"></a>Класс Икуиккактиватеимпл

Этот класс сочетает инициализацию элементов управления контейнера с одним вызовом.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IQuickActivateImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Икуиккактиватеимпл:: Жетконтентекстент](#getcontentextent)|Извлекает текущий отображаемый размер для выполняемого элемента управления.|
|[Икуиккактиватеимпл:: Куиккактивате](#quickactivate)|Выполняет быструю инициализацию загружаемых элементов управления.|
|[Икуиккактиватеимпл:: Сетконтентекстент](#setcontentextent)|Информирует Управление объемом отображаемого пространства, назначенного контейнеру.|

## <a name="remarks"></a>Примечания

Интерфейс [икуиккактивате](/windows/win32/api/ocidl/nn-ocidl-iquickactivate) помогает контейнерам избежать задержек при загрузке элементов управления путем объединения инициализации в одном вызове. Метод `QuickActivate` позволяет контейнеру передать указатель на [ структуру QACONTAINER](/windows/win32/api/ocidl/ns-ocidl-qacontainer), содержащую указатели на все интерфейсы, необходимые элементу управления. При возврате элемент управления передает указатель на структуру [каконтрол](/windows/win32/api/ocidl/ns-ocidl-qacontrol) , которая содержит указатели на собственные интерфейсы, используемые контейнером. Класс `IQuickActivateImpl` `IUnknown` предоставляет`IQuickActivate` реализацию по умолчанию и реализует, отправляя сведения в устройство дампа в отладочных сборках.

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="getcontentextent"></a>Икуиккактиватеимпл:: Жетконтентекстент

Извлекает текущий отображаемый размер для выполняемого элемента управления.

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Примечания

Размер предназначен для полной отрисовки элемента управления и указывается в единицах HIMETRIC.

См. раздел [икуиккактивате:: жетконтентекстент](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) в Windows SDK.

##  <a name="quickactivate"></a>Икуиккактиватеимпл:: Куиккактивате

Выполняет быструю инициализацию загружаемых элементов управления.

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>Примечания

Структура содержит указатели на интерфейсы, необходимые элементу управления, и значения некоторых внешних свойств. После возврата элемент управления передает указатель на структуру [каконтрол](/windows/win32/api/ocidl/ns-ocidl-qacontrol) , содержащую указатели на собственные интерфейсы, необходимые контейнеру, и дополнительные сведения о состоянии.

См. раздел [икуиккактивате:: куиккактивате](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-quickactivate) в Windows SDK.

##  <a name="setcontentextent"></a>Икуиккактиватеимпл:: Сетконтентекстент

Информирует Управление объемом отображаемого пространства, назначенного контейнеру.

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Примечания

Размер указывается в единицах HIMETRIC.

См. раздел [икуиккактивате:: сетконтентекстент](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
