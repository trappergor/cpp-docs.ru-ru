---
title: Класс Иолеконтролимпл
ms.date: 11/04/2016
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
ms.openlocfilehash: 3bdb501d8210c98ce982719358564c4937991e12
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495830"
---
# <a name="iolecontrolimpl-class"></a>Класс Иолеконтролимпл

Этот класс предоставляет реализацию `IOleControl` интерфейса по умолчанию и реализует. `IUnknown`

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IOleControlImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Иолеконтролимпл:: FreezeEvents](#freezeevents)|Указывает, будет ли контейнер игнорировать или принимать события от элемента управления.|
|[Иолеконтролимпл:: Жетконтролинфо](#getcontrolinfo)|Заполняет сведения о поведении клавиатуры элемента управления. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеконтролимпл:: Онамбиентпропертичанже](#onambientpropertychange)|Информирует элемент управления, что изменилось одно или несколько внешних свойств контейнера. Реализация ATL возвращает значение S_OK.|
|[Иолеконтролимпл:: OnMnemonic](#onmnemonic)|Информирует элемент управления о нажатии пользователем указанного нажатия клавиши. Реализация ATL возвращает значение E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Класс `IOleControlImpl` предоставляет реализацию интерфейса [метод интерфейса IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol) по умолчанию и реализует `IUnknown` , отправляя сведения в устройство дампа в отладочных сборках.

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="freezeevents"></a>Иолеконтролимпл:: FreezeEvents

В `FreezeEvents` реализации ATL увеличивает элемент `bFreeze` `m_nFreezeEvents` данных класса элемента управления, если имеет значение true, и уменьшает `m_nFreezeEvents` , если `bFreeze` имеет значение false.

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>Примечания

`FreezeEvents`затем возвращает значение S_OK.

См. раздел [метод интерфейса IOleControl:: FreezeEvents](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents) в Windows SDK.

##  <a name="getcontrolinfo"></a>Иолеконтролимпл:: Жетконтролинфо

Заполняет сведения о поведении клавиатуры элемента управления.

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>Примечания

См. раздел [метод интерфейса IOleControl: жетконтролинфо](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

##  <a name="onambientpropertychange"></a>Иолеконтролимпл:: Онамбиентпропертичанже

Информирует элемент управления, что изменилось одно или несколько внешних свойств контейнера.

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. раздел [метод интерфейса IOleControl:: онамбиентпропертичанже](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) в Windows SDK.

##  <a name="onmnemonic"></a>Иолеконтролимпл:: OnMnemonic

Информирует элемент управления о нажатии пользователем указанного нажатия клавиши.

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [метод интерфейса IOleControl:: OnMnemonic](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)<br/>
[Интерфейсы элементов управления ActiveX](/windows/win32/com/activex-controls-interfaces)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
