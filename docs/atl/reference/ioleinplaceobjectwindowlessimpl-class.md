---
title: Класс Иолеинплацеобжектвиндовлессимпл
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
ms.openlocfilehash: fdd660daae109ac2a656519131dd9869ceaeaf4e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495751"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>Класс Иолеинплацеобжектвиндовлессимпл

Этот класс реализует `IUnknown` и предоставляет методы, позволяющие безоконному управлению принимать сообщения окон и принимать участие в операциях перетаскивания.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IOleInPlaceObjectWindowlessImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Иолеинплацеобжектвиндовлессимпл:: Контекстсенситивехелп](#contextsensitivehelp)|Включает контекстную справку. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеинплацеобжектвиндовлессимпл:: Жетдроптаржет](#getdroptarget)|`IDropTarget` Предоставляет интерфейс для активного, безоконного объекта, поддерживающего перетаскивание. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеинплацеобжектвиндовлессимпл::/Window](#getwindow)|Возвращает маркер окна.|
|[Иолеинплацеобжектвиндовлессимпл:: Инплацедеактивате](#inplacedeactivate)|Деактивирует активный элемент управления на месте.|
|[Иолеинплацеобжектвиндовлессимпл:: Онвиндовмессаже](#onwindowmessage)|Отправляет сообщение из контейнера в безоконный элемент управления, который находится в активном состоянии.|
|[Иолеинплацеобжектвиндовлессимпл:: Реактиватеандундо](#reactivateandundo)|Повторно активирует ранее деактивированный элемент управления. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеинплацеобжектвиндовлессимпл:: Сетобжектректс](#setobjectrects)|Указывает, какая часть элемента управления является видимой.|
|[Иолеинплацеобжектвиндовлессимпл:: Уидеактивате](#uideactivate)|Деактивирует и удаляет пользовательский интерфейс, поддерживающий активацию на месте.|

## <a name="remarks"></a>Примечания

Интерфейс [иолеинплацеобжект](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) управляет повторной активацией и деактивацией элементов управления на месте и определяет, какая часть элемента управления должна быть видима. Интерфейс [иолеинплацеобжектвиндовлесс](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) позволяет безоконному управлению принимать сообщения окон и участвовать в операциях перетаскивания. Класс `IOleInPlaceObjectWindowlessImpl` предоставляет `IOleInPlaceObjectWindowless` `IUnknown` реализацию по умолчанию иреализует,отправляясведениявустройстводампавотладочныхсборках.`IOleInPlaceObject`

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="contextsensitivehelp"></a>  IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp

Возвращает значение E_NOTIMPL.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>Примечания

См. раздел [иолевиндов:: контекстсенситивехелп](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) в Windows SDK.

##  <a name="getdroptarget"></a>Иолеинплацеобжектвиндовлессимпл:: Жетдроптаржет

Возвращает значение E_NOTIMPL.

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>Примечания

См. раздел [иолеинплацеобжектвиндовлесс:: жетдроптаржет](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget) в Windows SDK.

##  <a name="getwindow"></a>Иолеинплацеобжектвиндовлессимпл::/Window

Контейнер вызывает эту функцию для получения маркера окна элемента управления.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Примечания

Некоторые контейнеры не будут работать с элементом управления, не имеющим окон, даже если он в настоящий момент находится в окне. В реализации ATL, если элемент `m_bWasOnceWindowless` данных класса элемента управления имеет значение true, функция возвращает E_FAIL. В противном случае, если *ФВНД* не `GetWindow` равен \* null, устанавливает *ФВНД* в элемент `m_hWnd` данных класса элемента управления и возвращает значение S_OK.

См. раздел [иолевиндов:: onwindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) в Windows SDK.

##  <a name="inplacedeactivate"></a>Иолеинплацеобжектвиндовлессимпл:: Инплацедеактивате

Вызывается контейнером для деактивации активного элемента управления на месте.

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>Примечания

Этот метод выполняет полную или частичную деактивацию в зависимости от состояния элемента управления. При необходимости пользовательский интерфейс элемента управления деактивируется, и окно элемента управления, если таковое имеется, уничтожается. Контейнер уведомляется о том, что элемент управления больше не активен. `IOleInPlaceUIWindow` Интерфейс, используемый контейнером для согласования меню и пространства границ, освобождается.

См. раздел [иолеинплацеобжект:: инплацедеактивате](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) в Windows SDK.

##  <a name="onwindowmessage"></a>Иолеинплацеобжектвиндовлессимпл:: Онвиндовмессаже

Отправляет сообщение из контейнера в безоконный элемент управления, который находится в активном состоянии.

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>Примечания

См. раздел [иолеинплацеобжектвиндовлесс:: онвиндовмессаже](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage) в Windows SDK.

##  <a name="reactivateandundo"></a>Иолеинплацеобжектвиндовлессимпл:: Реактиватеандундо

Возвращает значение E_NOTIMPL.

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>Примечания

См. раздел [иолеинплацеобжект:: реактиватеандундо](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) в Windows SDK.

##  <a name="setobjectrects"></a>Иолеинплацеобжектвиндовлессимпл:: Сетобжектректс

Вызывается контейнером для информирования элемента управления о том, что его размер и (или) расположение изменились.

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>Примечания

Обновляет элемент `m_rcPos` данных элемента управления и отображение элемента управления. Отображается только часть элемента управления, пересекающего область отсечения. Если отображение элемента управления было ранее обрезано, но обрезка была удалена, эту функцию можно вызвать для перерисовки полного представления элемента управления.

См. раздел [иолеинплацеобжект:: сетобжектректс](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) в Windows SDK.

##  <a name="uideactivate"></a>Иолеинплацеобжектвиндовлессимпл:: Уидеактивате

Деактивирует и удаляет пользовательский интерфейс элемента управления, поддерживающий активацию на месте.

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>Примечания

Задает для элемента `m_bUIActive` данных класса элемента управления значение false. Реализация этой функции в библиотеке ATL всегда возвращает значение S_OK.

См. раздел [иолеинплацеобжект:: уидеактивате](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
