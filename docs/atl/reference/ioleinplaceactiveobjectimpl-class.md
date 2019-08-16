---
title: Класс Иолеинплацеактивеобжектимпл
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
ms.openlocfilehash: f52638c8a28652cc958ebb3d774319ab37a3c46d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495756"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>Класс Иолеинплацеактивеобжектимпл

Этот класс предоставляет методы для облегчения взаимодействия между элементом управления на месте и его контейнером.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IOleInPlaceActiveObjectImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Иолеинплацеактивеобжектимпл:: Контекстсенситивехелп](#contextsensitivehelp)|Включает контекстную справку. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеинплацеактивеобжектимпл:: Енаблемоделесс](#enablemodeless)|Включение немодальных диалоговых окон. Реализация ATL возвращает значение S_OK.|
|[Иолеинплацеактивеобжектимпл::/Window](#getwindow)|Возвращает маркер окна.|
|[Иолеинплацеактивеобжектимпл:: OnDocWindowActivate](#ondocwindowactivate)|Уведомляет элемент управления о том, что окно документа контейнера активировано или отключено. Реализация ATL возвращает значение S_OK.|
|[Иолеинплацеактивеобжектимпл:: OnFrameWindowActivate](#onframewindowactivate)|Уведомляет элемент управления о том, что окно фрейма верхнего уровня контейнера активировано или отключено. Реализация ATL возвращает|
|[Иолеинплацеактивеобжектимпл:: ResizeBorder](#resizeborder)|Информирует элемент управления, что ему нужно изменить размер границ. Реализация ATL возвращает значение S_OK.|
|[Иолеинплацеактивеобжектимпл:: TranslateAccelerator](#translateaccelerator)|В меню "процессы" — сообщения ключа ускорителя из контейнера. Реализация ATL возвращает значение E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Интерфейс [метода IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) помогает взаимодействовать между элементами управления на месте и его контейнером. Например, связь активного состояния элемента управления и контейнера и уведомление элемента управления о необходимости изменения размера. Класс `IOleInPlaceActiveObjectImpl` `IUnknown` предоставляет`IOleInPlaceActiveObject` реализацию по умолчанию и поддерживает, отправляя сведения на устройство дампа в отладочных сборках.

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="contextsensitivehelp"></a>Иолеинплацеактивеобжектимпл:: Контекстсенситивехелп

Включает контекстную справку.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [иолевиндов:: контекстсенситивехелп](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) в Windows SDK.

##  <a name="enablemodeless"></a>Иолеинплацеактивеобжектимпл:: Енаблемоделесс

Включение немодальных диалоговых окон.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. раздел [метода IOleInPlaceActiveObject:: енаблемоделесс](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) в Windows SDK.

##  <a name="getwindow"></a>Иолеинплацеактивеобжектимпл::/Window

Контейнер вызывает эту функцию для получения маркера окна элемента управления.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Примечания

Некоторые контейнеры не будут работать с элементом управления, не имеющим окон, даже если он в настоящий момент находится в окне. В реализации ATL, если `CComControl::m_bWasOnceWindowless` элемент данных имеет значение true, функция возвращает E_FAIL. В противном \* случае, если *ФВНД* не `GetWindow` равно null, присваивает *ФВНД* элементу `m_hWnd` данных класса элемента управления и возвращает значение S_OK.

См. раздел [иолевиндов:: onwindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) в Windows SDK.

##  <a name="ondocwindowactivate"></a>Иолеинплацеактивеобжектимпл:: OnDocWindowActivate

Уведомляет элемент управления о том, что окно документа контейнера активировано или отключено.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. раздел [метода IOleInPlaceActiveObject:: OnDocWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) в Windows SDK.

##  <a name="onframewindowactivate"></a>Иолеинплацеактивеобжектимпл:: OnFrameWindowActivate

Уведомляет элемент управления о том, что окно фрейма верхнего уровня контейнера активировано или отключено.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. раздел [метода IOleInPlaceActiveObject:: OnFrameWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) в Windows SDK.

##  <a name="resizeborder"></a>Иолеинплацеактивеобжектимпл:: ResizeBorder

Информирует элемент управления, что ему нужно изменить размер границ.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. раздел [метода IOleInPlaceActiveObject:: ResizeBorder](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) в Windows SDK.

##  <a name="translateaccelerator"></a>Иолеинплацеактивеобжектимпл:: TranslateAccelerator

В меню "процессы" — сообщения ключа ускорителя из контейнера.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод поддерживает следующие возвращаемые значения.

Значение S_OK, если сообщение было успешно переведено.

S_FALSE, если сообщение не было переведено.

### <a name="remarks"></a>Примечания

См. раздел [метода IOleInPlaceActiveObject:: TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Интерфейсы элементов управления ActiveX](/windows/win32/com/activex-controls-interfaces)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
