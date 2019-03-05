---
title: Класс IOleInPlaceActiveObjectImpl
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
ms.openlocfilehash: fd0bcb7bb20967128ef3b3cc62722c3b68e728d8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285052"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>Класс IOleInPlaceActiveObjectImpl

Этот класс предоставляет методы, за помощь при написании связи между элементом управления на месте и его контейнером.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IOleInPlaceActiveObjectImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|Обеспечивает контекстную справку. Реализация ATL возвращает E_NOTIMPL.|
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|Позволяет немодальных диалоговых окон. Реализация ATL, возвращается значение s_ок.|
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|Получает дескриптор окна.|
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|Уведомляет элемент управления, при активации или отключении окна документа контейнера. Реализация ATL, возвращается значение s_ок.|
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|Уведомляет элемент управления, при активации или отключении окна фрейма верхнего уровня контейнера. Возвращает реализацию ATL|
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Информирует элемент управления, необходимые для изменения размера его границы. Реализация ATL, возвращается значение s_ок.|
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Обрабатывает сообщения сочетания клавиш меню из контейнера. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Примечания

[IOleInPlaceActiveObject](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceactiveobject) интерфейс помогает связи между элементом управления на месте и его контейнером; например, взаимодействие активное состояние элемента управления и контейнер и о том, элемент управления необходимости изменить размер сам. Класс `IOleInPlaceActiveObjectImpl` предоставляет реализацию по умолчанию `IOleInPlaceActiveObject` и поддерживает `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="contextsensitivehelp"></a>  IOleInPlaceActiveObjectImpl::ContextSensitiveHelp

Обеспечивает контекстную справку.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. в разделе [IOleWindow::ContextSensitiveHelp](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) в Windows SDK.

##  <a name="enablemodeless"></a>  IOleInPlaceActiveObjectImpl::EnableModeless

Позволяет немодальных диалоговых окон.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. в разделе [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) в Windows SDK.

##  <a name="getwindow"></a>  IOleInPlaceActiveObjectImpl::GetWindow

Контейнер вызывает эту функцию, чтобы получить дескриптор окна элемента управления.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Примечания

Некоторые контейнеры не будет работать с элементом управления, без окон, даже если он является в настоящее время оконные. В реализации библиотеки ATL Если `CComControl::m_bWasOnceWindowless` элемент данных имеет значение TRUE, функция возвращает E_FAIL. В противном случае, если \* *phwnd* не равно NULL, `GetWindow` назначает *phwnd* на данные-член класса элемента управления `m_hWnd` и возвращает значение S_OK.

См. в разделе [IOleWindow::GetWindow](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-getwindow) в Windows SDK.

##  <a name="ondocwindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnDocWindowActivate

Уведомляет элемент управления, при активации или отключении окна документа контейнера.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. в разделе [IOleInPlaceActiveObject::OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) в Windows SDK.

##  <a name="onframewindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnFrameWindowActivate

Уведомляет элемент управления, при активации или отключении окна фрейма верхнего уровня контейнера.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. в разделе [IOleInPlaceActiveObject::OnFrameWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) в Windows SDK.

##  <a name="resizeborder"></a>  IOleInPlaceActiveObjectImpl::ResizeBorder

Информирует элемент управления, необходимые для изменения размера его границы.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. в разделе [IOleInPlaceActiveObject::ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) в Windows SDK.

##  <a name="translateaccelerator"></a>  IOleInPlaceActiveObjectImpl::TranslateAccelerator

Обрабатывает сообщения сочетания клавиш меню из контейнера.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод поддерживает следующие возвращаемые значения.

Значение S_OK, если сообщение было успешно преобразовано.

S_FALSE, если сообщение не было преобразовано.

### <a name="remarks"></a>Примечания

См. в разделе [IOleInPlaceActiveObject::TranslateAccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Интерфейсы, элементы управления ActiveX](/windows/desktop/com/activex-controls-interfaces)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
