---
title: Класс CAxWindow
ms.date: 11/04/2016
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
ms.openlocfilehash: 33c5b48c88a6fc7a4ed18a93e874d318a16a20dd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58775443"
---
# <a name="caxwindow-class"></a>Класс CAxWindow

Этот класс предоставляет методы для работы с окном, размещения элемента управления ActiveX.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAxWindow : public CWindow
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[AttachControl](#attachcontrol)|Присоединяет существующего элемента управления ActiveX для `CAxWindow` объекта.|
|[CAxWindow](#caxwindow)|Создает объект `CAxWindow`.|
|[CreateControl](#createcontrol)|Создает элемент управления ActiveX, инициализирует его и размещает его в `CAxWindow` окна.|
|[CreateControlEx](#createcontrolex)|Создает элемент управления ActiveX и получает указатель интерфейса (или указатели) из элемента управления.|
|[GetWndClassName](#getwndclassname)|(Статический) Извлекает имя предварительно определенный класс `CAxWindow` объекта.|
|[QueryControl](#querycontrol)|Извлекает `IUnknown` размещенного элемента управления ActiveX.|
|[QueryHost](#queryhost)|Извлекает `IUnknown` указатель `CAxWindow` объекта.|
|[SetExternalDispatch](#setexternaldispatch)|Задает интерфейс внешнего диспетчеризации, используемые `CAxWindow` объекта.|
|[SetExternalUIHandler](#setexternaluihandler)|Задает внешние `IDocHostUIHandler` интерфейс, используемый `CAxWindow` объекта.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор =](#operator_eq)|Назначает HWND в существующий `CAxWindow` объекта.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы для работы с окном, на котором размещается элемент управления ActiveX. Размещение обеспечивается " **AtlAxWin80»**, который инкапсулируется `CAxWindow`.

Класс `CAxWindow` реализуется как специализация `CAxWindowT` класса. Такая специализация объявляется как:

`typedef CAxWindowT<CWindow> CAxWindow;`

Если необходимо изменить базовый класс, можно использовать `CAxWindowT` и укажите новый базовый класс в качестве аргумента шаблона.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="attachcontrol"></a>  CAxWindow::AttachControl

Создает новый объект узла, если еще не присутствует и прикрепляет указанный элемент управления к узлу.

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
[in] Указатель на `IUnknown` элемента управления.

*ppUnkContainer*<br/>
[out] Указатель на `IUnknown` узла ( `AxWin` объекта).

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Присоединяемый объект элемента управления необходимо правильно инициализировать перед вызовом `AttachControl`.

##  <a name="caxwindow"></a>  CAxWindow::CAxWindow

Создает `CAxWindow` с помощью существующего объекта дескриптора окна.

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Дескриптор существующего объекта окна.

##  <a name="createcontrol"></a>  CAxWindow::CreateControl

Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.

```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку для создания элемента управления. Должен быть отформатирован в одном из следующих способов:

- ProgID, например «MSCAL. Calendar.7»

- CLSID, такие как «{8E27C92B-1264-101C-8A2F-040224009C02}»

- URL-адрес, например "<http://www.microsoft.com>"

- Ссылку на активный документ, например, «file://\\\Documents\MyDoc.doc»

- Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY >\<парными >»

   > [!NOTE]
   > «MSHTML:» должен предшествовать фрагмент HTML, таким образом, чтобы он обозначается как поток MSHTML. На платформах Windows Mobile, поддерживаются только идентификаторы ProgID и CLSID. Windows CE внедренные платформ, отличных от Windows Mobile с CE IE поддерживает использование всех типов, включая идентификатор ProgID, CLSID, URL-адрес, ссылка на активный документ и фрагмент кода HTML.

*pStream*<br/>
[in] Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
[out] Адрес указателя, который будет получать `IUnknown` контейнера. Может иметь значение NULL.

*dwResID*<br/>
Идентификатор ресурса ресурс HTML. Элемент управления WebBrowser будет создан и загружен с указанным ресурсом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если используется второй версии этого метода он привязывается к ресурсу, определяемому элемента управления HTML *dwResID*.

Этот метод дает тот же результат, что и вызов метода:

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

См. в разделе [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) создание, инициализация и размещения лицензированный элемент управления ActiveX.

### <a name="example"></a>Пример

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CreateControl`.

##  <a name="createcontrolex"></a>  CAxWindow::CreateControlEx

Создает элемент управления ActiveX, инициализирует его и размещает в указанном окне.

```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку для создания элемента управления. Должен быть отформатирован в одном из следующих способов:

- ProgID, например «MSCAL. Calendar.7»

- CLSID, такие как «{8E27C92B-1264-101C-8A2F-040224009C02}»

- URL-адрес, например "<http://www.microsoft.com>"

- Ссылку на активный документ, например, «file://\\\Documents\MyDoc.doc»

- Фрагмент HTML, такие как «MSHTML:\<HTML >\<текст > это строка текста\</BODY >\<парными >»

   > [!NOTE]
   > «MSHTML:» должен предшествовать фрагмент HTML, таким образом, чтобы он обозначается как поток MSHTML. На платформах Windows Mobile, поддерживаются только идентификаторы ProgID и CLSID. Windows CE внедренные платформ, отличных от Windows Mobile с CE IE поддерживает использование всех типов, включая идентификатор ProgID, CLSID, URL-адрес, ссылка на активный документ и фрагмент кода HTML.

*pStream*<br/>
[in] Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
[out] Адрес указателя, который будет получать `IUnknown` контейнера. Может иметь значение NULL.

*ppUnkControl*<br/>
[out] Адрес указателя, который будет получать `IUnknown` элемента управления. Может иметь значение NULL.

*iidSink*<br/>
[in] Идентификатор исходящего интерфейса на содержащийся объект. Может быть IID_NULL.

*punkSink*<br/>
[in] Указатель на `IUnknown` интерфейс приемника объекта должен быть подключен к точкой соединения в автономной объекта, заданного параметром *iidSink*.

*dwResID*<br/>
[in] Идентификатор ресурса ресурс HTML. Элемент управления WebBrowser будет создан и загружен с указанным ресурсом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Этот метод аналогичен методу [CAxWindow::CreateControl](#createcontrol), но в отличие от этого метода `CreateControlEx` также позволяет получать указатель интерфейса на вновь созданный элемент управления и настройка приемник событий для получения события, инициируемые элементом управления.

См. в разделе [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) создание, инициализация и размещения лицензированный элемент управления ActiveX.

### <a name="example"></a>Пример

См. в разделе [размещения ActiveX элементов управления с помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий `CreateControlEx`.

##  <a name="getwndclassname"></a>  CAxWindow::GetWndClassName

Извлекает имя класса окна.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, содержащую имя класса окна, nonlicensed элементов управления ActiveX.

##  <a name="operator_eq"></a>  CAxWindow::operator =

Назначает HWND в существующий `CAxWindow` объекта.

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Дескриптор к существующему окну.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на текущий объект `CAxWindow`.

##  <a name="querycontrol"></a>  CAxWindow::QueryControl

Извлекает указанный интерфейс размещенного элемента управления.

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Указывает идентификатор IID интерфейса элемента управления.

*ppUnk*<br/>
[out] Указатель на интерфейс элемента управления. В шаблоне версия этого метода нет необходимости для идентификатора ссылки, до тех пор, пока передается типизированный интерфейс с связанные UUID.

*Q*<br/>
[in] Интерфейс, запрашиваемый для.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="queryhost"></a>  CAxWindow::QueryHost

Возвращает указанный интерфейс узла.

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Указывает идентификатор IID интерфейса элемента управления.

*ppUnk*<br/>
[out] Указатель на интерфейс на узле. В шаблоне версия этого метода нет необходимости для идентификатора ссылки, до тех пор, пока передается типизированный интерфейс с связанные UUID.

*Q*<br/>
[in] Интерфейс, запрашиваемый для.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Интерфейс узла разрешает доступ к базовой функции размещения окно кода, реализуемый `AxWin`.

##  <a name="setexternaldispatch"></a>  CAxWindow::SetExternalDispatch

Задает интерфейс внешнего диспетчера для `CAxWindow` объекта.

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
[in] Указатель на `IDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="setexternaluihandler"></a>  CAxWindow::SetExternalUIHandler

Задает внешние [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) интерфейс для `CAxWindow` объекта.

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>Параметры

*pUIHandler*<br/>
[in] Указатель на `IDocHostUIHandlerDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Внешние `IDocHostUIHandlerDispatch` интерфейс используется элементами управления, к которым запрос узлу для `IDocHostUIHandlerDispatch` интерфейс. Элемент управления WebBrowser — один элемент управления, выполняющий это.

## <a name="see-also"></a>См. также

[Образец ATLCON](../../overview/visual-cpp-samples.md)<br/>
[Класс CWindow](../../atl/reference/cwindow-class.md)<br/>
[Основы составного элемента управления](../../atl/atl-composite-control-fundamentals.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)
