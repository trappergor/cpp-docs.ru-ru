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
ms.openlocfilehash: 6f5629370bc1f821dac0a08cc76b5df1450f7a5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318720"
---
# <a name="caxwindow-class"></a>Класс CAxWindow

Этот класс предоставляет методы для манипулирования окном, размещающим элемент управления ActiveX.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CAxWindow : public CWindow
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[ПрикрепитьКонтроль](#attachcontrol)|Прикрепляет к объекту `CAxWindow` существующий элемент управления ActiveX.|
|[CAxWindow](#caxwindow)|Формирует объект `CAxWindow`.|
|[CreateControl](#createcontrol)|Создает элемент управления ActiveX, инициализирует `CAxWindow` его и размещает в окне.|
|[СозданиеControlEx](#createcontrolex)|Создает элемент управления ActiveX и извлекает указатель интерфейса (или указателей) из элемента управления.|
|[GetWndClassName](#getwndclassname)|(Статик) Извлекает предопределенное название `CAxWindow` класса объекта.|
|[ЗапросКонтроль](#querycontrol)|Извлекает `IUnknown` из хостового управления ActiveX.|
|[КериХост](#queryhost)|Извлекает `IUnknown` указатель `CAxWindow` объекта.|
|[SetExternalDispatch](#setexternaldispatch)|Устанавливает внешний интерфейс диспетчеризации, используемый объектом. `CAxWindow`|
|[SetExternalUIHandler](#setexternaluihandler)|Устанавливает внешний `IDocHostUIHandler` интерфейс, `CAxWindow` используемый объектом.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор](#operator_eq)|Присваивает HWND `CAxWindow` существующему объекту.|

## <a name="remarks"></a>Remarks

Этот класс предоставляет методы для манипулирования окном, в котором размещается элемент управления ActiveX. Хостинг предоставляется **"AtlAxWin80",** который обернут `CAxWindow`.

Класс `CAxWindow` реализован как специализация `CAxWindowT` класса. Эта специализация заявлена как:

`typedef CAxWindowT<CWindow> CAxWindow;`

Если необходимо изменить базовый класс, `CAxWindowT` можно использовать и указывать новый базовый класс в качестве аргумента шаблона.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="caxwindowattachcontrol"></a><a name="attachcontrol"></a>CAxWindow::AttachControl

Создает новый объект-хоста, если он еще не присутствует, и прикрепляет указанный элемент управления к хосту.

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
(в) Указатель на `IUnknown` элемент управления.

*ppUnkContainer*<br/>
(ваут) Указатель на `IUnknown` усев `AxWin` (объект).

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Присоединенный объект управления должен быть правильно `AttachControl`инициализирован перед вызовом.

## <a name="caxwindowcaxwindow"></a><a name="caxwindow"></a>CAxWindow::CAxWindow

Строит `CAxWindow` объект с помощью существующей ручки объекта окна.

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
Ручка существующего объекта окна.

## <a name="caxwindowcreatecontrol"></a><a name="createcontrol"></a>CAxWindow::CreateControl

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
Указатель на строку для создания элемента управления. Должен быть отформатирован одним из следующих способов:

- Прогид, например,`"MSCAL.Calendar.7"`

- CLSID, такие как`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL, такой как`"<https://www.microsoft.com>"`

- Ссылка на активный документ, такой как`"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML, например,`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML. Только ProgID и CLSID поддерживаются на платформах Windows Mobile. Встроенные платформы Windows CE, кроме Windows Mobile с поддержкой CE IE поддержки всех типов, включая ProgID, CLSID, URL, ссылку на активный документ, и фрагмент HTML.

*pStream*<br/>
(в) Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
(ваут) Адрес указателя, который получит `IUnknown` контейнер. Может иметь значение NULL.

*dwResID*<br/>
Идентификатор ресурса HTML-ресурса. Управление WebBrowser будет создано и загружено с указанным ресурсом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Если используется вторая версия этого метода, создается элемент html-управления, связанный с ресурсом, идентифицированным *dwResID.*

Этот метод дает вам тот же результат, что и вызов:

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

Смотрите [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) для создания, инициализации и размещения лицензированного управления ActiveX.

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует. `CreateControl`

## <a name="caxwindowcreatecontrolex"></a><a name="createcontrolex"></a>CAxWindow::CreateControlEx

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
Указатель на строку для создания элемента управления. Должен быть отформатирован одним из следующих способов:

- Прогид, например,`"MSCAL.Calendar.7"`

- CLSID, такие как`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL, такой как`"<https://www.microsoft.com>"`

- Ссылка на активный документ, такой как`"file://\\\Documents\MyDoc.doc"`

- Фрагмент HTML, например,`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`должен предшествовать фрагменту HTML, чтобы он был обозначен как поток MSHTML. Только ProgID и CLSID поддерживаются на платформах Windows Mobile. Встроенные платформы Windows CE, кроме Windows Mobile с поддержкой CE IE поддержки всех типов, включая ProgID, CLSID, URL, ссылку на активный документ, и фрагмент HTML.

*pStream*<br/>
(в) Указатель на поток, который используется для инициализации свойств элемента управления. Может иметь значение NULL.

*ppUnkContainer*<br/>
(ваут) Адрес указателя, который получит `IUnknown` контейнер. Может иметь значение NULL.

*ppUnkControl*<br/>
(ваут) Адрес указателя, который получит `IUnknown` элемент управления. Может иметь значение NULL.

*iidSink*<br/>
(в) Идентификатор интерфейса исходящего интерфейса на содержащемся объекте. Может быть IID_NULL.

*punkSink*<br/>
(в) Указатель на `IUnknown` интерфейс объекта раковины, который будет подключен к точке соединения на объекте, указанном *iidSink.*

*dwResID*<br/>
(в) Идентификатор ресурса HTML-ресурса. Управление WebBrowser будет создано и загружено с указанным ресурсом.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Этот метод похож на [CAxWindow::CreateControl](#createcontrol), `CreateControlEx` но в отличие от этого метода, также позволяет получить указатель интерфейса к вновь созданному элементу управления и настроить раковину события для получения событий, выпущенных элементом управления.

Смотрите [CAxWindow2T::СозданиеControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) для создания, инициализации и размещения лицензированного управления ActiveX.

### <a name="example"></a>Пример

Смотрите [хостинг ActiveX Управления С помощью ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) для образца, который использует. `CreateControlEx`

## <a name="caxwindowgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow::GetWndClassName

Извлекает название класса окон.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, содержащую имя класса окон, который может размещать нелицензированные элементы управления ActiveX.

## <a name="caxwindowoperator-"></a><a name="operator_eq"></a>CAxWindow::оператор

Присваивает HWND `CAxWindow` существующему объекту.

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>Параметры

*Hwnd*<br/>
Ручка к существующему окну.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на текущий объект `CAxWindow`.

## <a name="caxwindowquerycontrol"></a><a name="querycontrol"></a>CAxWindow::Контроль качества

Извлекает указанный интерфейс развмещаемого элемента управления.

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) Определяет iID интерфейса управления.

*ppUnk*<br/>
(ваут) Указатель на интерфейс управления. В шаблонной версии этого метода нет необходимости в идентификаторе ссылки при наличии набранного интерфейса с соответствующим UUID.

*Q*<br/>
(в) Интерфейс, который запрашивается для.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="caxwindowqueryhost"></a><a name="queryhost"></a>CAxWindow::КвиторХост

Возвращает указанный интерфейс хоста.

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) Определяет iID интерфейса управления.

*ppUnk*<br/>
(ваут) Указатель на интерфейс на хосте. В шаблонной версии этого метода нет необходимости в идентификаторе ссылки при наличии набранного интерфейса с соответствующим UUID.

*Q*<br/>
(в) Интерфейс, который запрашивается для.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Интерфейс хоста позволяет получить доступ к основной функциональности кода-хостинга окон, реализованного `AxWin`.

## <a name="caxwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>CAxWindow::SetExternalDispatch

Устанавливает внешний интерфейс `CAxWindow` диспетчеризации объекта.

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
(в) Указатель на `IDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="caxwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>CAxWindow::SetExternalUIHandler

Устанавливает внешний интерфейс [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) для `CAxWindow` объекта.

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>Параметры

*pUIHandler*<br/>
(в) Указатель на `IDocHostUIHandlerDispatch` интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Внешний `IDocHostUIHandlerDispatch` интерфейс используется элементами управления, которые заследуют `IDocHostUIHandlerDispatch` сайт узла для интерфейса. Управление WebBrowser — это один элемент управления, который делает это.

## <a name="see-also"></a>См. также раздел

[АТЛКОН ОбразЕЦ](../../overview/visual-cpp-samples.md)<br/>
[Класс CWindow](../../atl/reference/cwindow-class.md)<br/>
[Основные сведения о составном элементе управления](../../atl/atl-composite-control-fundamentals.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Часто задаваемые вопросы о вложении элементов управления](../../atl/atl-control-containment-faq.md)
