---
title: Класс CDHtmlDialog
ms.date: 03/27/2019
f1_keywords:
- CDHtmlDialog
- AFXDHTML/CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CanAccessExternal
- AFXDHTML/CDHtmlDialog::CreateControlSite
- AFXDHTML/CDHtmlDialog::DDX_DHtml_AxControl
- AFXDHTML/CDHtmlDialog::DDX_DHtml_CheckBox
- AFXDHTML/CDHtmlDialog::DDX_DHtml_ElementText
- AFXDHTML/CDHtmlDialog::DDX_DHtml_Radio
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectIndex
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectString
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectValue
- AFXDHTML/CDHtmlDialog::DestroyModeless
- AFXDHTML/CDHtmlDialog::EnableModeless
- AFXDHTML/CDHtmlDialog::FilterDataObject
- AFXDHTML/CDHtmlDialog::GetControlDispatch
- AFXDHTML/CDHtmlDialog::GetControlProperty
- AFXDHTML/CDHtmlDialog::GetCurrentUrl
- AFXDHTML/CDHtmlDialog::GetDHtmlDocument
- AFXDHTML/CDHtmlDialog::GetDropTarget
- AFXDHTML/CDHtmlDialog::GetElement
- AFXDHTML/CDHtmlDialog::GetElementHtml
- AFXDHTML/CDHtmlDialog::GetElementInterface
- AFXDHTML/CDHtmlDialog::GetElementProperty
- AFXDHTML/CDHtmlDialog::GetElementText
- AFXDHTML/CDHtmlDialog::GetEvent
- AFXDHTML/CDHtmlDialog::GetExternal
- AFXDHTML/CDHtmlDialog::GetHostInfo
- AFXDHTML/CDHtmlDialog::GetOptionKeyPath
- AFXDHTML/CDHtmlDialog::HideUI
- AFXDHTML/CDHtmlDialog::IsExternalDispatchSafe
- AFXDHTML/CDHtmlDialog::LoadFromResource
- AFXDHTML/CDHtmlDialog::Navigate
- AFXDHTML/CDHtmlDialog::OnBeforeNavigate
- AFXDHTML/CDHtmlDialog::OnDocumentComplete
- AFXDHTML/CDHtmlDialog::OnDocWindowActivate
- AFXDHTML/CDHtmlDialog::OnFrameWindowActivate
- AFXDHTML/CDHtmlDialog::OnInitDialog
- AFXDHTML/CDHtmlDialog::OnNavigateComplete
- AFXDHTML/CDHtmlDialog::ResizeBorder
- AFXDHTML/CDHtmlDialog::SetControlProperty
- AFXDHTML/CDHtmlDialog::SetElementHtml
- AFXDHTML/CDHtmlDialog::SetElementProperty
- AFXDHTML/CDHtmlDialog::SetElementText
- AFXDHTML/CDHtmlDialog::SetExternalDispatch
- AFXDHTML/CDHtmlDialog::SetHostFlags
- AFXDHTML/CDHtmlDialog::ShowContextMenu
- AFXDHTML/CDHtmlDialog::ShowUI
- AFXDHTML/CDHtmlDialog::TranslateAccelerator
- AFXDHTML/CDHtmlDialog::TranslateUrl
- AFXDHTML/CDHtmlDialog::UpdateUI
- AFXDHTML/CDHtmlDialog::m_bUseHtmlTitle
- AFXDHTML/CDHtmlDialog::m_nHtmlResID
- AFXDHTML/CDHtmlDialog::m_pBrowserApp
- AFXDHTML/CDHtmlDialog::m_spHtmlDoc
- AFXDHTML/CDHtmlDialog::m_strCurrentUrl
- AFXDHTML/CDHtmlDialog::m_szHtmlResID
helpviewer_keywords:
- CDHtmlDialog [MFC], CDHtmlDialog
- CDHtmlDialog [MFC], CanAccessExternal
- CDHtmlDialog [MFC], CreateControlSite
- CDHtmlDialog [MFC], DDX_DHtml_AxControl
- CDHtmlDialog [MFC], DDX_DHtml_CheckBox
- CDHtmlDialog [MFC], DDX_DHtml_ElementText
- CDHtmlDialog [MFC], DDX_DHtml_Radio
- CDHtmlDialog [MFC], DDX_DHtml_SelectIndex
- CDHtmlDialog [MFC], DDX_DHtml_SelectString
- CDHtmlDialog [MFC], DDX_DHtml_SelectValue
- CDHtmlDialog [MFC], DestroyModeless
- CDHtmlDialog [MFC], EnableModeless
- CDHtmlDialog [MFC], FilterDataObject
- CDHtmlDialog [MFC], GetControlDispatch
- CDHtmlDialog [MFC], GetControlProperty
- CDHtmlDialog [MFC], GetCurrentUrl
- CDHtmlDialog [MFC], GetDHtmlDocument
- CDHtmlDialog [MFC], GetDropTarget
- CDHtmlDialog [MFC], GetElement
- CDHtmlDialog [MFC], GetElementHtml
- CDHtmlDialog [MFC], GetElementInterface
- CDHtmlDialog [MFC], GetElementProperty
- CDHtmlDialog [MFC], GetElementText
- CDHtmlDialog [MFC], GetEvent
- CDHtmlDialog [MFC], GetExternal
- CDHtmlDialog [MFC], GetHostInfo
- CDHtmlDialog [MFC], GetOptionKeyPath
- CDHtmlDialog [MFC], HideUI
- CDHtmlDialog [MFC], IsExternalDispatchSafe
- CDHtmlDialog [MFC], LoadFromResource
- CDHtmlDialog [MFC], Navigate
- CDHtmlDialog [MFC], OnBeforeNavigate
- CDHtmlDialog [MFC], OnDocumentComplete
- CDHtmlDialog [MFC], OnDocWindowActivate
- CDHtmlDialog [MFC], OnFrameWindowActivate
- CDHtmlDialog [MFC], OnInitDialog
- CDHtmlDialog [MFC], OnNavigateComplete
- CDHtmlDialog [MFC], ResizeBorder
- CDHtmlDialog [MFC], SetControlProperty
- CDHtmlDialog [MFC], SetElementHtml
- CDHtmlDialog [MFC], SetElementProperty
- CDHtmlDialog [MFC], SetElementText
- CDHtmlDialog [MFC], SetExternalDispatch
- CDHtmlDialog [MFC], SetHostFlags
- CDHtmlDialog [MFC], ShowContextMenu
- CDHtmlDialog [MFC], ShowUI
- CDHtmlDialog [MFC], TranslateAccelerator
- CDHtmlDialog [MFC], TranslateUrl
- CDHtmlDialog [MFC], UpdateUI
- CDHtmlDialog [MFC], m_bUseHtmlTitle
- CDHtmlDialog [MFC], m_nHtmlResID
- CDHtmlDialog [MFC], m_pBrowserApp
- CDHtmlDialog [MFC], m_spHtmlDoc
- CDHtmlDialog [MFC], m_strCurrentUrl
- CDHtmlDialog [MFC], m_szHtmlResID
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
ms.openlocfilehash: d53d3afb464b9dcfa32ab3cf4ee51446f8313a92
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771829"
---
# <a name="cdhtmldialog-class"></a>Класс CDHtmlDialog

Используется для создания диалоговых окон, использующих HTML вместо ресурсов диалогового окна для своей реализации интерфейса пользователя.

## <a name="syntax"></a>Синтаксис

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|Создает объект CDHtmlDialog.|
|[CDHtmlDialog::~CDHtmlDialog](#_dtorcdhtmldialog)|Уничтожает объект CDHtmlDialog.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|Переопределяемый, вызываемого как ли объекты сценариев на странице "загрузки" доступ к внешней диспетчеризация сайт элемента управления проверки доступа. Проверяет, чтобы убедиться в том, что диспетчеризации, либо safe для использования в сценариях или текущей зоны позволяет для объектов, которые не являются безопасными для использования в сценариях.|
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|Переопределяемый класс, используемый для создания экземпляра сайта элемента управления, чтобы разместить элемент управления WebBrowser в диалоговом окне.|
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|Обеспечивает обмен данными между переменной-члена и значение свойства элемента управления ActiveX, на странице HTML.|
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|Обеспечивает обмен данными между переменной-члена и типа "флажок" на странице HTML.|
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|Обеспечивает обмен данными между переменную-член и любого свойства элемента HTML на странице HTML.|
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|Обеспечивает обмен данными между переменной-члена и типа "переключатель" на странице HTML.|
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|Возвращает или задает индекс в списке на странице HTML.|
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|Возвращает или задает отображаемый текст (на основе текущего индекса) записи поле списка на странице HTML.|
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|Получает или задает значение записи поле списка (на основе текущего индекса) на странице HTML.|
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|Уничтожает немодального диалогового окна.|
|[CDHtmlDialog::EnableModeless](#enablemodeless)|Позволяет немодальных диалоговых окон.|
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|Позволяет диалогового окна, чтобы отфильтровать объекты данных буфера обмена, созданные размещенного браузером.|
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|Извлекает `IDispatch` интерфейс на элементе управления ActiveX, внедренные в документ HTML.|
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|Извлекает запрошенного свойства указанного элемента управления ActiveX.|
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|Извлекает унифицированный указатель ресурса (URL), связанный с текущим документом.|
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|Извлекает интерфейс IHTMLDocument2 на текущем загруженном документе HTML.|
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|Вызвано элемента управления WebBrowser в контейнере, при его использовании в качестве целевого объекта перетаскивания позволяет диалогового окна, чтобы предоставить альтернативный интерфейс [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).|
|[CDHtmlDialog::GetElement](#getelement)|Возвращает интерфейс на HTML-элемент.|
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|Извлекает `innerHTML` свойство HTML-элемента.|
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|Извлекает указатель на запрошенный интерфейс из HTML-элемент.|
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|Извлекает значение свойства элемента HTML.|
|[CDHtmlDialog::GetElementText](#getelementtext)|Извлекает `innerText` свойство HTML-элемента.|
|[CDHtmlDialog::GetEvent](#getevent)|Получает `IHTMLEventObj` указатель на текущий объект события.|
|[CDHtmlDialog::GetExternal](#getexternal)|Получает узел `IDispatch` интерфейс.|
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|Возвращает возможности пользовательского интерфейса ведущего приложения.|
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|Получает раздел реестра, в которой хранятся пользовательские настройки.|
|[CDHtmlDialog::HideUI](#hideui)|Скрывает пользовательский Интерфейс основного приложения.|
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|Указывает, является ли хоста `IDispatch` интерфейс безопасен для скриптов.|
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|Загружает указанный ресурс в элементе управления WebBrowser.|
|[CDHtmlDialog::Navigate](#navigate)|Выполняет переход к указанному URL-АДРЕСУ.|
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|Вызывается платформой, прежде чем событие навигации.|
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|Вызывается платформой для оповещения приложения, в том случае, когда документ, достигает состояния READYSTATE_COMPLETE.|
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|Вызывается платформой при активации или отключении окна документа.|
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|Вызывается платформой при активации или отключении окна фрейма.|
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|Вызывается в ответ на сообщение WM_INITDIALOG.|
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|Вызывается платформой, после завершения события навигации.|
|[CDHtmlDialog::ResizeBorder](#resizeborder)|Оповещает объект о необходимости изменить размер пространства границы.|
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|Задает свойство элемента управления ActiveX на новое значение.|
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|Наборы `innerHTML` свойства HTML-элемента.|
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|Задает свойство элемента HTML.|
|[CDHtmlDialog::SetElementText](#setelementtext)|Наборы `innerText` свойства HTML-элемента.|
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|Задает хоста `IDispatch` интерфейс.|
|[CDHtmlDialog::SetHostFlags](#sethostflags)|Задает флаги пользовательского интерфейса ведущего приложения.|
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|Вызывается перед отображением контекстного меню.|
|[CDHtmlDialog::ShowUI](#showui)|Показан пользовательский Интерфейс основного приложения.|
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|Вызывается для обработки сообщений сочетания клавиш меню.|
|[CDHtmlDialog::TranslateUrl](#translateurl)|Вызывается, чтобы изменить URL-адрес для загрузки.|
|[CDHtmlDialog::UpdateUI](#updateui)|Вызывается для уведомления узла об изменении состояния команды.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|Указывает, следует ли использовать название документа HTML как заголовок диалогового окна.|
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|Ресурс ресурса код HTML для отображения.|
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Указатель на веб-приложения браузера.|
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|Указатель на документ HTML.|
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|Текущий URL-адрес.|
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|Строковая версия идентификатор ресурса HTML.|

## <a name="remarks"></a>Примечания

`CDHtmlDialog` можно загрузить код HTML для отображения из ресурс HTML или URL-адрес.

`CDHtmlDialog` Можно также данные обмена с HTML-элементы управления и обработки событий из HTML-элементы управления, например при нажатии кнопки.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

`CDHtmlDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdhtml.h

##  <a name="ddx_dhtml_helper_macros"></a>  Вспомогательные макросы DDX_DHtml

Вспомогательные макросы DDX_DHtml обеспечивают простой доступ к часто используемые свойства элементов управления на HTML-страницы.

### <a name="data-exchange-macros"></a>Макросы для обмена данными

|||
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Задает или получает значение свойства выбранного элемента управления.|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Задает или получает текст между тегами начала и окончания текущего элемента.|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Устанавливает или извлекает HTML между открывающий и закрывающий теги текущего элемента.|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Задает или получает назначения URL-адрес или точку привязки.|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Задает или получает целевое окно или фрейм.|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Задает или получает имя изображения или видеоклипа в документ.|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|Задает или получает URL-адрес связанного кадра.|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|Задает или получает URL-адрес связанного кадра.|

##  <a name="canaccessexternal"></a>  CDHtmlDialog::CanAccessExternal

Переопределяемый, вызываемого как ли объекты сценариев на странице "загрузки" доступ к внешней диспетчеризация сайт элемента управления проверки доступа. Проверяет, чтобы убедиться в том, что диспетчеризации, либо safe для использования в сценариях или текущей зоны позволяет для объектов, которые не являются безопасными для использования в сценариях.

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="cdhtmldialog"></a>  CDHtmlDialog::CDHtmlDialog

Создает диалоговое окно на основе ресурсов динамического HTML.

```
CDHtmlDialog();

CDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID,
    CWnd *pParentWnd = NULL);

CDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd *pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*lpszTemplateName*<br/>
Завершающаяся нулем строка, представляющая имя ресурса шаблона диалогового окна.

*szHtmlResID*<br/>
Завершающаяся нулем строка, представляющая имя ресурса HTML.

*pParentWnd*<br/>
Указатель на объект окна родительский объект или владельца (типа [CWnd](../../mfc/reference/cwnd-class.md)), которому принадлежит объект диалогового окна. Если это значение NULL, родительское окно объекта диалогового окна будет присвоено главного окна приложения.

*nIDTemplate*<br/>
Содержит идентификатор ресурса шаблона диалогового окна.

*nHtmlResID*<br/>
Содержит идентификатор ресурса HTML.

### <a name="remarks"></a>Примечания

Вторая форма конструктора предоставляет доступ к ресурсу через имя шаблона диалогового окна. Третья форма конструктора предоставляет доступ к ресурсу через идентификатор ресурса шаблона диалогового окна. Как правило, идентификатор начинается с **IDD_** префикс.

##  <a name="_dtorcdhtmldialog"></a>  CDHtmlDialog::~CDHtmlDialog

Уничтожает объект CDHtmlDialog.

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>Примечания

[CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) необходимо использовать функцию-член для уничтожения безрежимные диалоговые окна, созданные [CDialog::Create](../../mfc/reference/cdialog-class.md#create).

##  <a name="createcontrolsite"></a>  CDHtmlDialog::CreateControlSite

Переопределяемый класс, используемый для создания экземпляра сайта элемента управления, чтобы разместить элемент управления WebBrowser в диалоговом окне.

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>Параметры

*pContainer*<br/>
Указатель на [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) объекта

*ppSite*<br/>
Указатель на указатель на [COleControlSite](../../mfc/reference/colecontrolsite-class.md).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Можно переопределить эту функцию-член для возврата экземпляра вашего собственного класса элемента управления узла.

##  <a name="ddx_dhtml_axcontrol"></a>  CDHtmlDialog::DDX_DHtml_AxControl

Обеспечивает обмен данными между переменной-члена и значение свойства элемента управления ActiveX, на странице HTML.

```
void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    VARIANT& var);

void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    LPCTSTR szPropName,
    VARIANT& var);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*szId*<br/>
Значение параметра идентификатор тега объекта в источнике HTML для элемента управления ActiveX.

*Идентификатор dispId*<br/>
Идентификатор диспетчера свойства, с которым вы хотите обмениваться данными.

*szPropName*<br/>
Имя свойства.

*var*<br/>
Элемент данных типа VARIANT, [COleVariant](../../mfc/reference/colevariant-class.md), или [CComVariant](../../atl/reference/ccomvariant-class.md), которая содержит значение, обмен которыми осуществляется с помощью свойства элемента управления ActiveX.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]

##  <a name="ddx_dhtml_checkbox"></a>  CDHtmlDialog::DDX_DHtml_CheckBox

Обеспечивает обмен данными между переменной-члена и типа "флажок" на странице HTML.

```
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,
    LPCTSTR szId,
    int& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*szId*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*value*<br/>
Значение, при обмене.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

##  <a name="ddx_dhtml_elementtext"></a>  CDHtmlDialog::DDX_DHtml_ElementText

Обеспечивает обмен данными между переменную-член и любого свойства элемента HTML на странице HTML.

```
void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    CString& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    short& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    int& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    long& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    DWORD& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    float& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    double& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*szId*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*Идентификатор dispId*<br/>
Идентификатор диспетчеризации HTML-элемента, с которым вы хотите обмениваться данными.

*value*<br/>
Значение, при обмене.

##  <a name="ddx_dhtml_radio"></a>  CDHtmlDialog::DDX_DHtml_Radio

Обеспечивает обмен данными между переменной-члена и типа "переключатель" на странице HTML.

```
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*szId*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*value*<br/>
Значение, при обмене.

##  <a name="ddx_dhtml_selectindex"></a>  CDHtmlDialog::DDX_DHtml_SelectIndex

Возвращает или задает индекс в списке на странице HTML.

```
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*szId*<br/>
Значение, которое указано для элемента управления HTML `id` параметра.

*value*<br/>
Значение, при обмене.

##  <a name="ddx_dhtml_selectstring"></a>  CDHtmlDialog::DDX_DHtml_SelectString

Возвращает или задает отображаемый текст (на основе текущего индекса) записи поле списка на странице HTML.

```
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*szId*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*value*<br/>
Значение, при обмене.

##  <a name="ddx_dhtml_selectvalue"></a>  CDHtmlDialog::DDX_DHtml_SelectValue

Получает или задает значение записи поле списка (на основе текущего индекса) на странице HTML.

```
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Параметры

*pDX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*szId*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*value*<br/>
Значение, при обмене.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

##  <a name="destroymodeless"></a>  CDHtmlDialog::DestroyModeless

Отсоединяет немодального диалогового окна из `CDHtmlDialog` объекта и уничтожает объект.

```
void DestroyModeless();
```

##  <a name="enablemodeless"></a>  CDHtmlDialog::EnableModeless

Позволяет немодальных диалоговых окон.

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>Параметры

*fEnable*<br/>
См. в разделе *fEnable* в [IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="filterdataobject"></a>  CDHtmlDialog::FilterDataObject

Позволяет диалогового окна, чтобы отфильтровать объекты данных буфера обмена, созданные размещенного браузером.

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>Параметры

*pDO*<br/>
См. в разделе *pDO* в [IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)) в пакете Windows SDK.

*ppDORet*<br/>
См. в разделе *ppDORet* в `IDocHostUIHandler::FilterDataObject` в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="getcontroldispatch"></a>  CDHtmlDialog::GetControlDispatch

Извлекает `IDispatch` интерфейс на элементе управления ActiveX, внедренные в документ HTML, возвращаемый [GetDHtmlDocument](#getdhtmldocument).

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>Параметры

*szId*<br/>
HTML-идентификатор элемента управления ActiveX.

*ppdisp*<br/>
`IDispatch` Интерфейса элемента управления если найден в веб-страницы.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="getcontrolproperty"></a>  CDHtmlDialog::GetControlProperty

Извлекает запрошенного свойства указанного элемента управления ActiveX.

```
VARIANT GetControlProperty(
    LPCTSTR szId,
    LPCTSTR szPropName);

VARIANT GetControlProperty(
    LPCTSTR szId,
    DISPID dispId);

VARIANT GetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId);
```

### <a name="parameters"></a>Параметры

*szId*<br/>
HTML-идентификатор элемента управления ActiveX.

*szPropName*<br/>
Имя свойства в языковом стандарте по умолчанию текущего пользователя.

*pdispControl*<br/>
`IDispatch` Указатель на элемент управления ActiveX.

*Идентификатор dispId*<br/>
Идентификатор диспетчера свойства.

### <a name="return-value"></a>Возвращаемое значение

Значение типа variant, содержащее запрошенное свойство или пустое значение типа variant, если не удается найти элемент управления или свойства.

### <a name="remarks"></a>Примечания

Перегрузки перечисляются от наименее эффективным в верхней для наиболее эффективный внизу.

##  <a name="getcurrenturl"></a>  CDHtmlDialog::GetCurrentUrl

Извлекает унифицированный указатель ресурса (URL), связанный с текущим документом.

```
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>Параметры

*szUrl*<br/>
Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий URL-адрес для получения.

##  <a name="getdhtmldocument"></a>  CDHtmlDialog::GetDHtmlDocument

Извлекает [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) интерфейса на текущем загруженном документе HTML.

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>Параметры

*\*\*pphtmlDoc* указатель на указатель на документ HTML.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT. Возвращает значение S_OK при успешном выполнении.

##  <a name="getdroptarget"></a>  CDHtmlDialog::GetDropTarget

Вызвано элемента управления WebBrowser в контейнере, при его использовании в качестве целевого объекта перетаскивания позволяет диалогового окна, чтобы предоставить альтернативный интерфейс [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>Параметры

*pDropTarget*<br/>
См. в разделе *pDropTarget* в [IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)) в пакете Windows SDK.

*ppDropTarget*<br/>
См. в разделе *ppDropTarget* в `IDocHostUIHandler::GetDropTarget` в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="getelement"></a>  CDHtmlDialog::GetElement

Возвращает интерфейс на HTML-элемент, указанный *szElementId*.

```
HRESULT GetElement(
    LPCTSTR szElementId,
    IDispatch** ppdisp,
    BOOL* pbCollection = NULL);

HRESULT GetElement(
    LPCTSTR szElementId,
    IHTMLElement** pphtmlElement);
```

### <a name="parameters"></a>Параметры

*szElementId*<br/>
Идентификатор HTML-элемента.

*ppdisp*<br/>
`IDispatch` Указатель на запрошенный элемент или коллекция элементов.

*pbCollection*<br/>
Логическое значение, указывающее, является ли объект, представленный *ppdisp* один элемент или коллекция элементов.

*pphtmlElement*<br/>
`IHTMLElement` Указатель на запрошенный элемент.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Использовать первую перегрузку, если требуется для обработки условий, в которых может быть более одного элемента с указанным идентификатором. Последний параметр можно использовать, чтобы узнать, является ли возвращаемый указатель интерфейса на коллекцию или один элемент. Если указатель интерфейса находится в коллекции, вы можете запрашивать `IHTMLElementCollection` и использовать его `item` свойство для ссылки на элементы по порядковому номеру.

Вторая перегрузка завершится ошибкой, если имеется более одного элемента с одинаковым Идентификатором на странице.

##  <a name="getelementhtml"></a>  CDHtmlDialog::GetElementHtml

Извлекает `innerHTML` свойство элемента HTML, определяемого *szElementId*.

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>Параметры

*szElementId*<br/>
Идентификатор HTML-элемента.

### <a name="return-value"></a>Возвращаемое значение

`innerHTML` Свойство элемента HTML, определяемого *szElementId* или значение NULL, если элемент не найден.

##  <a name="getelementinterface"></a>  CDHtmlDialog::GetElementInterface

Извлекает указатель на запрошенный интерфейс из HTML-элемент, идентифицируемый *szElementId*.

```
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,
    Q** ppvObj);

HRESULT GetElementInterface(
    LPCTSTR szElementId,
    REFIID refiid,
    void** ppvObj);
```

### <a name="parameters"></a>Параметры

*szElementId*<br/>
Идентификатор HTML-элемента.

*ppvObj*<br/>
Адрес указатель, который заполняется запрошенный указатель интерфейса, если элемент найден и запрос завершается успешно.

*refiid*<br/>
Идентификатор IID запрошенного интерфейса интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

##  <a name="getelementproperty"></a>  CDHtmlDialog::GetElementProperty

Получает значение свойства, идентифицируемого по *dispId* из HTML-элемент, идентифицируемый *szElementId*.

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId);
```

### <a name="parameters"></a>Параметры

*szElementId*<br/>
Идентификатор HTML-элемента.

*Идентификатор dispId*<br/>
Идентификатор диспетчера свойства.

### <a name="return-value"></a>Возвращаемое значение

Значение свойства или пустой вариант, если свойство или элемент не найден.

##  <a name="getelementtext"></a>  CDHtmlDialog::GetElementText

Извлекает `innerText` свойство элемента HTML, определяемого *szElementId*.

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>Параметры

*szElementId*<br/>
Идентификатор HTML-элемента.

### <a name="return-value"></a>Возвращаемое значение

`innerText` Свойство элемента HTML, определяемого *szElementId* или значение NULL, если свойство или элемент не найден.

##  <a name="getevent"></a>  CDHtmlDialog::GetEvent

Возвращает `IHTMLEventObj` указатель на текущий объект события.

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>Параметры

*ppEventObj*<br/>
Адрес указателя, будет заполняться `IHTMLEventObj` указатель на интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Эта функция должна вызываться только из в обработчике событий DHTML.

##  <a name="getexternal"></a>  CDHtmlDialog::GetExternal

Получает узел `IDispatch` интерфейс.

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>Параметры

*ppDispatch*<br/>
См. в разделе *ppDispatch* в [IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK в случае успеха или E_NOTIMPL в случае сбоя.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="gethostinfo"></a>  CDHtmlDialog::GetHostInfo

Возвращает возможности пользовательского интерфейса ведущего приложения.

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>Параметры

*pInfo*<br/>
См. в разделе *pInfo* в [IDocHostUIHandler::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="getoptionkeypath"></a>  CDHtmlDialog::GetOptionKeyPath

Получает раздел реестра, в которой хранятся пользовательские настройки.

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>Параметры

*pchKey*<br/>
См. в разделе *pchKey* в [IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)) в пакете Windows SDK.

*dw*<br/>
См. в разделе *dw* в `IDocHostUIHandler::GetOptionKeyPath` в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="hideui"></a>  CDHtmlDialog::HideUI

Скрывает пользовательский Интерфейс основного приложения.

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="isexternaldispatchsafe"></a>  CDHtmlDialog::IsExternalDispatchSafe

Указывает, является ли хоста `IDispatch` интерфейс безопасен для скриптов.

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение FALSE.

##  <a name="loadfromresource"></a>  CDHtmlDialog::LoadFromResource

Загружает указанный ресурс в элемент управления WebBrowser в диалоговом окне DHTML.

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>Параметры

*lpszResource*<br/>
Указатель на строку, содержащую имя ресурса для загрузки.

*nRes*<br/>
Идентификатор ресурса для загрузки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

##  <a name="m_busehtmltitle"></a>  CDHtmlDialog::m_bUseHtmlTitle

Указывает, следует ли использовать название документа HTML как заголовок диалогового окна.

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>Примечания

Если **m**_ **bUseHtmlTitle** имеет значение TRUE, заголовок диалогового окна приравнивается к заголовок документа HTML; в противном случае используется заголовок в ресурс диалогового окна.

##  <a name="m_nhtmlresid"></a>  CDHtmlDialog::m_nHtmlResID

Ресурс ресурса код HTML для отображения.

```
UINT m_nHtmlResID;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]

##  <a name="m_pbrowserapp"></a>  CDHtmlDialog::m_pBrowserApp

Указатель на веб-приложения браузера.

```
CComPtr <IWebBrowser2> m_pBrowserApp;
```

##  <a name="m_sphtmldoc"></a>  CDHtmlDialog::m_spHtmlDoc

Указатель на документ HTML.

```
CComPtr<IHTMLDocument2> m_spHtmlDoc;
```

##  <a name="m_strcurrenturl"></a>  CDHtmlDialog::m_strCurrentUrl

Текущий URL-адрес.

```
CString m_strCurrentUrl;
```

##  <a name="m_szhtmlresid"></a>  CDHtmlDialog::m_szHtmlResID

Строковая версия идентификатор ресурса HTML.

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

##  <a name="navigate"></a>  CDHtmlDialog::Navigate

Переходит к ресурсу, определяемому URL-адрес, который задается параметром *lpszURL*.

```
void Navigate(
    LPCTSTR lpszURL,
    DWORD dwFlags = 0,
    LPCTSTR lpszTargetFrameName = NULL,
    LPCTSTR lpszHeaders = NULL,
    LPVOID lpvPostData = NULL,
    DWORD dwPostDataLen = 0);
```

### <a name="parameters"></a>Параметры

*lpszURL*<br/>
Указатель на строку, содержащую URL-адрес, для которых будет включен.

*dwFlags*<br/>
Флаги, переменной, которая указывает, следует ли добавить ресурс в список журнала, следует ли для чтения в кэш или записи из кэша и необходимость отображения ресурса в новом окне. Переменная может представлять собой сочетание значений, определенных в [BrowserNavConstants](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768360\(v=vs.85\)) перечисления.

*lpszTargetFrameName*<br/>
Указатель на строку, содержащую имя фрейма, в котором будет отображаться ресурс.

*lpszHeaders*<br/>
Указатель на значение, указывающее заголовки HTTP для отправки на сервер. Эти заголовки добавляются к заголовкам Internet Explorer по умолчанию. Заголовки можно указать такие сведения, как действие, необходимое на сервере, тип данных, передаваемых на сервер, или код состояния. Этот параметр игнорируется, если URL-адрес не является URL-адресом HTTP.

*lpvPostData*<br/>
Указатель на данные для отправки с помощью операции HTTP POST. Например операции POST используется для отправки HTML-формы для сбора данных. Если этот параметр не содержит никаких данных post, `Navigate` выдает операции HTTP GET. Этот параметр игнорируется, если URL-адрес не является URL-адресом HTTP.

*dwPostDataLen*<br/>
Данные, отправляемые с транзакцией HTTP POST. Например операции POST используется для отправки HTML-формы для сбора данных. Если этот параметр не содержит никаких данных post, `Navigate` выдает операции HTTP GET. Этот параметр игнорируется, если URL-адрес не является URL-адресом HTTP.

##  <a name="onbeforenavigate"></a>  CDHtmlDialog::OnBeforeNavigate

Вызывается платформой для события, возникающего перед его выполнением.

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
Указатель на объект `IDispatch` .

*szUrl*<br/>
Указатель на строку, содержащую URL-адрес для перехода.

##  <a name="ondocumentcomplete"></a>  CDHtmlDialog::OnDocumentComplete

Вызывается платформой для оповещения приложения, в том случае, когда документ выполнен состояния READYSTATE_COMPLETE.

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
Указатель на объект `IDispatch` .

*szUrl*<br/>
Указатель на строку, содержащую URL-адрес, по которому был осуществлен переход.

##  <a name="ondocwindowactivate"></a>  CDHtmlDialog::OnDocWindowActivate

Вызывается платформой при активации или отключении окна документа.

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Параметры

*fActivate*<br/>
См. в разделе *fActivate* в [IDocHostUIHandler::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="onframewindowactivate"></a>  CDHtmlDialog::OnFrameWindowActivate

Вызывается платформой при активации или отключении окна фрейма.

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Параметры

*fActivate*<br/>
См. в разделе *fActivate* в [IDocHostUIHandler::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="oninitdialog"></a>  CDHtmlDialog::OnInitDialog

Вызывается в ответ на сообщение WM_INITDIALOG.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Это сообщение отправляется в диалоговое окно во время `Create`, `CreateIndirect`, или `DoModal` вызовы, которые происходят непосредственно перед откроется диалоговое окно.

Переопределите эту функцию-член, если необходимо выполнять специальную обработку при инициализации диалоговое окно. В переопределенные версии, необходимо сначала вызвать базовый класс `OnInitDialog` , но игнорируйте его возвращаемое значение. Обычно из функции переопределенным членом возвратит TRUE.

Вызовы Windows `OnInitDialog` работать через процедуру стандартный глобального диалогового окна, общие для всех диалоговых библиотеки Microsoft Foundation Class, а не через схему сообщений, поэтому нет необходимости записи схемы сообщений для этой функции-члена.

##  <a name="onnavigatecomplete"></a>  CDHtmlDialog::OnNavigateComplete

Вызывается платформой, после завершения перехода на указанный URL-адрес.

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
Указатель на объект `IDispatch` .

*szUrl*<br/>
Указатель на строку, содержащую URL-адрес, по которому был осуществлен переход.

##  <a name="resizeborder"></a>  CDHtmlDialog::ResizeBorder

Оповещает объект о необходимости изменить размер пространства границы.

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>Параметры

*prcBorder*<br/>
См. в разделе *prcBorder* в [IDocHostUIHandler::ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\)) в пакете Windows SDK.

*pUIWindow*<br/>
См. в разделе *pUIWindow* в `IDocHostUIHandler::ResizeBorder` в пакете Windows SDK.

*fFrameWindow*<br/>
См. в разделе *fFrameWindow* в `IDocHostUIHandler::ResizeBorder` в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

##  <a name="setcontrolproperty"></a>  CDHtmlDialog::SetControlProperty

Задает свойство элемента управления ActiveX на новое значение.

```
void SetControlProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    LPCTSTR szElementId,
    LPCTSTR szPropName,
    VARIANT* pVar);
```

### <a name="parameters"></a>Параметры

*szElementId*<br/>
HTML-идентификатор элемента управления ActiveX.

*Идентификатор dispId*<br/>
Идентификатор диспетчера свойства.

*pVar*<br/>
Указатель на значение VARIANT, содержащий новое значение свойства.

*pdispControl*<br/>
Указатель на элемент управления ActiveX `IDispatch` интерфейс.

*szPropName*<br/>
Строка, содержащая имя задаваемого свойства.

##  <a name="setelementhtml"></a>  CDHtmlDialog::SetElementHtml

Наборы `innerHTML` свойства HTML-элемента.

```
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Параметры

*szElementId*<br/>
Идентификатор HTML-элемента.

*bstrText*<br/>
Новое значение свойства `innerHTML`.

*punkElem*<br/>
`IUnknown` Указатель элемента HTML.

##  <a name="setelementproperty"></a>  CDHtmlDialog::SetElementProperty

Задает свойство элемента HTML.

```
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);
```

### <a name="parameters"></a>Параметры

*szElementId*<br/>
Идентификатор HTML-элемента.

*Идентификатор dispId*<br/>
Идентификатор диспетчера свойства.

*pVar*<br/>
Новое значение свойства.

##  <a name="setelementtext"></a>  CDHtmlDialog::SetElementText

Наборы `innerText` свойства HTML-элемента.

```
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Параметры

*szElementId*<br/>
Идентификатор HTML-элемента.

*bstrText*<br/>
Новое значение свойства `innerText`.

*punkElem*<br/>
`IUnknown` Указатель элемента HTML.

##  <a name="setexternaldispatch"></a>  CDHtmlDialog::SetExternalDispatch

Задает хоста `IDispatch` интерфейс.

```
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>Параметры

*pdispExternal*<br/>
Новый `IDispatch` интерфейс.

##  <a name="sethostflags"></a>  CDHtmlDialog::SetHostFlags

Задает флаги пользовательского интерфейса узла.

```
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Возможные значения см. в разделе [DOCHOSTUIFLAG](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753277\(v=vs.85\)) в пакете Windows SDK.

##  <a name="showcontextmenu"></a>  CDHtmlDialog::ShowContextMenu

Вызывается перед отображением контекстного меню.

```
STDMETHOD(ShowContextMenu)(
    DWORD dwID,
    POINT* ppt,
    IUnknown* pcmdtReserved,
    IDispatch* pdispReserved);
```

### <a name="parameters"></a>Параметры

*dwID*<br/>
См. в разделе *dwID* в [IDocHostUIHandler::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)) в пакете Windows SDK.

*PPT*<br/>
См. в разделе *ppt* в `IDocHostUIHandler::ShowContextMenu` в Windows SDK.

*pcmdtReserved*<br/>
См. в разделе *pcmdtReserved* в `IDocHostUIHandler::ShowContextMenu` в пакете Windows SDK.

*pdispReserved*<br/>
См. в разделе *pdispReserved* в `IDocHostUIHandler::ShowContextMenu` в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="showui"></a>  CDHtmlDialog::ShowUI

Показан пользовательский Интерфейс основного приложения.

```
STDMETHOD(ShowUI)(
    DWORD dwID,
    IOleInPlaceActiveObject* pActiveObject,
    IOleCommandTarget* pCommandTarget,
    IOleInPlaceFrame* pFrame,
    IOleInPlaceUIWindow* pDoc);
```

### <a name="parameters"></a>Параметры

*dwID*<br/>
См. в разделе *dwID* в [IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)) в пакете Windows SDK.

*pActiveObject*<br/>
См. в разделе *d pActiveObject* в `IDocHostUIHandler::ShowUI` в пакете Windows SDK.

*pCommandTarget*<br/>
См. в разделе *pCommandTarget* в `IDocHostUIHandler::ShowUI` в пакете Windows SDK.

*pFrame*<br/>
См. в разделе *pFrame* в `IDocHostUIHandler::ShowUI` в пакете Windows SDK.

*pDoc*<br/>
См. в разделе *pDoc* в `IDocHostUIHandler::ShowUI` в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="translateaccelerator"></a>  CDHtmlDialog::TranslateAccelerator

Вызывается для обработки сообщений сочетания клавиш меню.

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>Параметры

*lpMsg*<br/>
См. в разделе *lpMsg* в [IDocHostUIHandler::TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)) в пакете Windows SDK.

*pguidCmdGroup*<br/>
См. в разделе *параметром pguidCmdGroup* в `IDocHostUIHandler::TranslateAccelerator` в пакете Windows SDK.

*nCmdID*<br/>
См. в разделе *nCmdID* в `IDocHostUIHandler::TranslateAccelerator` в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="translateurl"></a>  CDHtmlDialog::TranslateUrl

Вызывается, чтобы изменить URL-адрес для загрузки.

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>Параметры

*dwTranslate*<br/>
См. в разделе *dwTranslate* в [IDocHostUIHandler::TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)) в пакете Windows SDK.

*pchURLIn*<br/>
См. в разделе *pchURLIn* в `IDocHostUIHandler::TranslateUrl` в пакете Windows SDK.

*ppchURLOut*<br/>
См. в разделе *ppchURLOut* в `IDocHostUIHandler::TranslateUrl` в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_FALSE.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)), как описано в пакете Windows SDK.

##  <a name="updateui"></a>  CDHtmlDialog::UpdateUI

Вызывается для уведомления узла об изменении состояния команды.

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Эта функция-член является реализацией в CDHtmlDialog [IDocHostUIHandler::UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\)), как описано в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Сложный пример MFC](../../overview/visual-cpp-samples.md)<br/>
[Вспомогательные макросы DDX_DHtml](#ddx_dhtml_helper_macros)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
