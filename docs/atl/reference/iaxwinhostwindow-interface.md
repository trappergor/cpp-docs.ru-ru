---
title: Интерфейс IAxWinHostWindow
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
ms.openlocfilehash: ebecc611660a788ce59bb11beb95bd60eacaf01b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329996"
---
# <a name="iaxwinhostwindow-interface"></a>Интерфейс IAxWinHostWindow

Этот интерфейс предоставляет методы для манипулирования элементом управления и его объектом-хозяином.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[ПрикрепитьКонтроль](#attachcontrol)|Прикрепляет существующий элемент управления к объекту-хоста.|
|[CreateControl](#createcontrol)|Создает элемент управления и прикрепляет его к объекту-хозяину.|
|[СозданиеControlEx](#createcontrolex)|Создает элемент управления, прикрепляет его к объекту-хоста и дополнительно настраивает обработчик событий.|
|[ЗапросКонтроль](#querycontrol)|Возвращает указатель интерфейса в размещенный элемент управления.|
|[SetExternalDispatch](#setexternaldispatch)|Устанавливает внешний `IDispatch` интерфейс.|
|[SetExternalUIHandler](#setexternaluihandler)|Устанавливает внешний `IDocHostUIHandlerDispatch` интерфейс.|

## <a name="remarks"></a>Remarks

Этот интерфейс подвергается ATL в ActiveX управления хостингобъектов. Вызов иметодов на этом интерфейсе для создания и/или присоединения элемента управления к объекту-хосу, чтобы получить интерфейс из развмещаемого элемента управления или установить внешний дисинтерфейс или обработчик интерфейса для использования при хостинге веб-браузера.

## <a name="requirements"></a>Требования

Определение этого интерфейса доступно в виде IDL или C, как показано ниже.

|Тип определения|Файл|
|---------------------|----------|
|Idl|ATLIFace.idl|
|C++|ATLIFace.h (также включен в ATLBase.h)|

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a>IAxWinHostWindow::AttachControl

Прикрепляет существующий (и ранее инициализированный) элемент управления к объекту-хоста с помощью окна, идентифицированного *hWnd.*

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>Параметры

*pUnkControl*<br/>
(в) Указатель на `IUnknown` интерфейс элемента управления, который должен быть прикреплен к объекту-хозяину.

*Hwnd*<br/>
(в) Ручка к окну, которая будет использоваться для хостинга.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a>IAxWinHostWindow::CreateControl

Создает элемент управления, инициализирует его и размещает в окне, идентифицированном *hWnd.*

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>Параметры

*lpTricsData*<br/>
(в) Строка, идентифицирующая элемент управления для создания. Может быть CLSID (должен включать скобки), ProgID, URL, или сырья HTML (прификсированной **MSHTML:**).

*Hwnd*<br/>
(в) Ручка к окну, которая будет использоваться для хостинга.

*pStream*<br/>
(в) Указатель интерфейса для потока, содержащего данные инициализации для управления. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Это окно будет подклассифицировано объектом-хоста, разоблачающим этот интерфейс, чтобы сообщения могли быть отражены в элементе управления, а другие элементы контейнера работали.

Вызов этого метода эквивалентен вызову [IAxWinHostWindow::CreateControlEx](#createcontrolex).

Чтобы создать лицензированный элемент управления [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)ActiveX, см.

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a>IAxWinHostWindow::CreateControlEx

Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне, подобно [IAxWinHostWindow::CreateControl](#createcontrol).

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>Параметры

*lpTricsData*<br/>
(в) Строка, идентифицирующая элемент управления для создания. Может быть CLSID (должны включать скобки), ProgID, URL, или сырья HTML (прикреплительно с **MSHTML:**).

*Hwnd*<br/>
(в) Ручка к окну, которая будет использоваться для хостинга.

*pStream*<br/>
(в) Указатель интерфейса для потока, содержащего данные инициализации для управления. Может иметь значение NULL.

*ppUnk*<br/>
(ваут) Адрес указателя, который получит `IUnknown` интерфейс созданного элемента управления. Может иметь значение NULL.

*riidAdvise*<br/>
(в) Идентификатор интерфейса исходящего интерфейса на содержащемся объекте. Может быть IID_NULL.

*punkAdvise*<br/>
(в) Указатель на `IUnknown` интерфейс объекта раковины, который будет подключен к точке `iidSink`соединения на указанном объекте.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

В `CreateControl` отличие `CreateControlEx` от метода, также позволяет получать указатель интерфейса к вновь созданному элементу управления и настраивать опускание событий для получения событий, выпущенных элементом управления.

Чтобы создать лицензированный элемент управления [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)ActiveX, см.

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a>IAxWinHostWindow::ЗапросКонтроль

Возвращает указанный указатель интерфейса, предоставляемый размещенным элементом управления.

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
(в) Идентификатор интерфейса на запрашиваемом элементе управления.

*ppvObject*<br/>
(ваут) Адрес указателя, который получит указанный интерфейс созданного элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch

Устанавливает внешний дисинтерфейс, который доступен для содержащегося элементов управления через [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) метод.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
(в) Указатель на `IDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>IAxWinhostWindow::SetExternalUIHandler

Вызовите эту функцию, чтобы установить внешний `CAxWindow` интерфейс [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) для объекта.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
(в) Указатель на `IDocHostUIHandlerDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Эта функция используется элементами управления веб-браузером, которые задавают `IDocHostUIHandlerDispatch` запрос на сайт узла для интерфейса.

## <a name="see-also"></a>См. также раздел

[Интерфейс IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[CAxWindow::КвиторХост](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
