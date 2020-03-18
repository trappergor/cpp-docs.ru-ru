---
title: Класс Каксвиндов
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
ms.openlocfilehash: 6f5c178090a970906209e41da9298be61a61c639
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423390"
---
# <a name="caxwindow-class"></a>Класс Каксвиндов

Этот класс предоставляет методы для управления окном, в котором размещается элемент ActiveX.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAxWindow : public CWindow
```

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[аттачконтрол](#attachcontrol)|Присоединяет существующий элемент управления ActiveX к объекту `CAxWindow`.|
|[каксвиндов](#caxwindow)|Формирует объект `CAxWindow`.|
|[CreateControl](#createcontrol)|Создает элемент управления ActiveX, инициализирует его и размещает в окне `CAxWindow`.|
|[креатеконтролекс](#createcontrolex)|Создает элемент управления ActiveX и получает указатель интерфейса (или указатели) из элемента управления.|
|[жетвндкласснаме](#getwndclassname)|Статически Извлекает предопределенное имя класса `CAxWindow` объекта.|
|[куериконтрол](#querycontrol)|Извлекает `IUnknown` размещенного элемента управления ActiveX.|
|[куерихост](#queryhost)|Возвращает указатель `IUnknown` объекта `CAxWindow`.|
|[сетекстерналдиспатч](#setexternaldispatch)|Задает внешний интерфейс диспетчеризации, используемый объектом `CAxWindow`.|
|[сетекстерналуихандлер](#setexternaluihandler)|Задает внешний интерфейс `IDocHostUIHandler`, используемый объектом `CAxWindow`.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](#operator_eq)|Присваивает HWND существующему объекту `CAxWindow`.|

## <a name="remarks"></a>Remarks

Этот класс предоставляет методы для манипуляций с окном, в котором размещается элемент управления ActiveX. Размещение обеспечивается " **AtlAxWin80"** , который упаковывается `CAxWindow`.

Класс `CAxWindow` реализован как специализация класса `CAxWindowT`. Эта специализация объявляется следующим образом:

`typedef CAxWindowT<CWindow> CAxWindow;`

Если необходимо изменить базовый класс, можно использовать `CAxWindowT` и указать новый базовый класс в качестве аргумента шаблона.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin. h

##  <a name="attachcontrol"></a>Каксвиндов:: Аттачконтрол

Создает новый объект узла, если он еще не существует, и присоединяет указанный элемент управления к узлу.

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Параметры

*пконтрол*<br/>
окне Указатель на `IUnknown` элемента управления.

*ппункконтаинер*<br/>
заполняет Указатель на `IUnknown` узла (объект `AxWin`).

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Присоединяемый объект элемента управления должен быть правильно инициализирован перед вызовом `AttachControl`.

##  <a name="caxwindow"></a>Каксвиндов:: Каксвиндов

Конструирует объект `CAxWindow` с помощью существующего обработчика объекта окна.

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Маркер существующего объекта Window.

##  <a name="createcontrol"></a>Каксвиндов:: CreateControl

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

*лпсзнаме*<br/>
Указатель на строку для создания элемента управления. Должен быть отформатирован одним из следующих способов:

- ProgID, например `"MSCAL.Calendar.7"`

- CLSID, например `"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL-адрес, например `"<https://www.microsoft.com>"`

- Ссылка на активный документ, например `"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML-кода, например `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"` должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML. На платформах Windows Mobile поддерживаются только идентификаторы ProgID и CLSID. Windows CE Embedded Platforms, кроме Windows Mobile с поддержкой CE IE, поддерживают все типы, включая ProgID, CLSID, URL-адрес, ссылку на активный документ и фрагмент кода HTML.

*пстреам*<br/>
окне Указатель на поток, используемый для инициализации свойств элемента управления. Может иметь значение NULL.

*ппункконтаинер*<br/>
заполняет Адрес указателя, который получит `IUnknown` контейнера. Может иметь значение NULL.

*двресид*<br/>
Идентификатор ресурса HTML-ресурса. Элемент управления WebBrowser будет создан и загружен с указанным ресурсом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Если используется вторая версия этого метода, создается HTML-элемент управления и связывается с ресурсом, идентифицируемым *двресид*.

Этот метод дает тот же результат, что и вызов:

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

См. раздел [CAxWindow2T:: креатеконтроллик](../../atl/reference/caxwindow2t-class.md#createcontrollic) для создания, инициализации и размещения лицензированного элемента управления ActiveX.

### <a name="example"></a>Пример

Пример, в котором используется `CreateControl`, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/hosting-activex-controls-using-atl-axhost.md) .

##  <a name="createcontrolex"></a>Каксвиндов:: Креатеконтролекс

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

*лпсзнаме*<br/>
Указатель на строку для создания элемента управления. Должен быть отформатирован одним из следующих способов:

- ProgID, например `"MSCAL.Calendar.7"`

- CLSID, например `"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL-адрес, например `"<https://www.microsoft.com>"`

- Ссылка на активный документ, например `"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML-кода, например `"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"` должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML. На платформах Windows Mobile поддерживаются только идентификаторы ProgID и CLSID. Windows CE Embedded Platforms, кроме Windows Mobile с поддержкой CE IE, поддерживают все типы, включая ProgID, CLSID, URL-адрес, ссылку на активный документ и фрагмент кода HTML.

*пстреам*<br/>
окне Указатель на поток, используемый для инициализации свойств элемента управления. Может иметь значение NULL.

*ппункконтаинер*<br/>
заполняет Адрес указателя, который получит `IUnknown` контейнера. Может иметь значение NULL.

*ппункконтрол*<br/>
заполняет Адрес указателя, который получит `IUnknown` элемента управления. Может иметь значение NULL.

*иидсинк*<br/>
окне Идентификатор интерфейса для исходящего интерфейса в автономном объекте. Можно IID_NULL.

*пунксинк*<br/>
окне Указатель на интерфейс `IUnknown` объекта приемника, который подключается к точке подключения в содержащемся объекте, указанном параметром *иидсинк*.

*двресид*<br/>
окне Идентификатор ресурса HTML-ресурса. Элемент управления WebBrowser будет создан и загружен с указанным ресурсом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Этот метод аналогичен [каксвиндов:: CreateControl](#createcontrol), но в отличие от этого метода, `CreateControlEx` также позволяет получить указатель интерфейса на только что созданном элементе управления и настроить приемник событий для получения событий, инициированных элементом управления.

См. раздел [CAxWindow2T:: креатеконтроллицекс](../../atl/reference/caxwindow2t-class.md#createcontrollicex) для создания, инициализации и размещения лицензированного элемента управления ActiveX.

### <a name="example"></a>Пример

Пример, в котором используется `CreateControlEx`, см. в разделе [Размещение элементов управления ActiveX с помощью библиотеки ATL](../../atl/hosting-activex-controls-using-atl-axhost.md) .

##  <a name="getwndclassname"></a>Каксвиндов:: Жетвндкласснаме

Извлекает имя класса окна.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, содержащую имя класса окна, в котором могут размещаться нелицензированные элементы управления ActiveX.

##  <a name="operator_eq"></a>Каксвиндов:: operator =

Присваивает HWND существующему объекту `CAxWindow`.

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*hWnd*<br/>
Маркер существующего окна.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на текущий объект `CAxWindow`.

##  <a name="querycontrol"></a>Каксвиндов:: Куериконтрол

Извлекает указанный интерфейс размещенного элемента управления.

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Указывает идентификатор IID интерфейса элемента управления.

*ппунк*<br/>
заполняет Указатель на интерфейс элемента управления. В версии шаблона этого метода нет необходимости указывать идентификатор ссылки при условии, что передан типизированный интерфейс со связанным UUID.

*Q*<br/>
окне Интерфейс, для которого выполняется запрос.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="queryhost"></a>Каксвиндов:: Куерихост

Возвращает указанный интерфейс узла.

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Указывает идентификатор IID интерфейса элемента управления.

*ппунк*<br/>
заполняет Указатель на интерфейс на узле. В версии шаблона этого метода нет необходимости указывать идентификатор ссылки при условии, что передан типизированный интерфейс со связанным UUID.

*Q*<br/>
окне Интерфейс, для которого выполняется запрос.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Интерфейс узла обеспечивает доступ к базовой функциональности кода, который размещается в окне, реализуемого `AxWin`.

##  <a name="setexternaldispatch"></a>Каксвиндов:: Сетекстерналдиспатч

Задает внешний интерфейс диспетчеризации для объекта `CAxWindow`.

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*пдисп*<br/>
окне Указатель на интерфейс `IDispatch`.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="setexternaluihandler"></a>Каксвиндов:: Сетекстерналуихандлер

Задает внешний интерфейс [идочостуихандлердиспатч](../../atl/reference/idochostuihandlerdispatch-interface.md) для объекта `CAxWindow`.

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>Параметры

*пуихандлер*<br/>
окне Указатель на интерфейс `IDocHostUIHandlerDispatch`.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Внешний интерфейс `IDocHostUIHandlerDispatch` используется элементами управления, которые запрашивают узел узла для интерфейса `IDocHostUIHandlerDispatch`. Элемент управления WebBrowser — это один из элементов управления, который делает это.

## <a name="see-also"></a>См. также раздел

[Пример АТЛКОН](../../overview/visual-cpp-samples.md)<br/>
[Класс CWindow](../../atl/reference/cwindow-class.md)<br/>
[Основные сведения о составном элементе управления](../../atl/atl-composite-control-fundamentals.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)<br/>
[Контрольное вложение вопросов и ответов](../../atl/atl-control-containment-faq.md)
