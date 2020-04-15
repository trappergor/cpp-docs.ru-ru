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
ms.openlocfilehash: 57ea8f3a1dbbce4fcfa350bd99e4ee628e9675c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375686"
---
# <a name="cdhtmldialog-class"></a>Класс CDHtmlDialog

Используется для создания диалоговые поля, которые используют HTML, а не диалоговые ресурсы для реализации их пользовательского интерфейса.

## <a name="syntax"></a>Синтаксис

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDHtmlДиалог::CDHtmlДиалог](#cdhtmldialog)|Строит объект CDHtmlDialog.|
|[CDHtmlДиалог:: »CDHtmlДиалог](#_dtorcdhtmldialog)|Уничтожает объект CDHtmlDialog.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDHtmlДиалог::CanAccessExternal](#canaccessexternal)|Переизвисшая, называемая проверкой доступа, чтобы выяснить, могут ли объекты скрипта на загруженной странице получить доступ к внешней отправке сайта управления. Проверка, чтобы убедиться, что отправка либо безопасна для скриптов, либо текущая зона позволяет объектам, которые не безопасны для сценариев.|
|[CDHtmlДиалог::СозданиеControlSite](#createcontrolsite)|Чрезмерно используется для создания экземпляра сайта управления для размещения управления WebBrowser в диалоге.|
|[CDHtmlDialog::DDX-DHtml-AxControl](#ddx_dhtml_axcontrol)|Обмен данными между переменной участника и значением свойства элемента управления ActiveX на странице HTML.|
|[CDHtmlDialog::DDX-DHtml](#ddx_dhtml_checkbox)|Обменивается данными между переменной участника и флажкой на странице HTML.|
|[CDHtmlDialog::DDX-DHtml-ЭлементТекст](#ddx_dhtml_elementtext)|Обменивается данными между переменной участника и любым свойством HTML-элемента на странице HTML.|
|[CDHtmlDialog::DDX-DHtml](#ddx_dhtml_radio)|Обмен данными между переменной участника и радиокнопкой на странице HTML.|
|[CDHtmlDialog::DDX-DHtml-SelectIndex](#ddx_dhtml_selectindex)|Получает или устанавливает индекс окна списка на странице HTML.|
|[CDHtmlDialog::DDX-DHtml-SelectString](#ddx_dhtml_selectstring)|Получает или устанавливает отображение текста ввода окна списка (на основе текущего индекса) на странице HTML.|
|[CDHtmlDialog::DDX-DHtml-SelectValue](#ddx_dhtml_selectvalue)|Получает или устанавливает значение входа в поле списка (на основе текущего индекса) на странице HTML.|
|[CDHtmlДиалог: :Dбезудейбез](#destroymodeless)|Уничтожает бесрежимную диалоговую коробку.|
|[CDHtmlДиалог::Безудержный](#enablemodeless)|Включает в себя бесрежимные диалоговые ящики.|
|[CDHtmlДиалог::FilterDataObject](#filterdataobject)|Позволяет диалогу фильтровать объекты данных буфера обмена, созданные размещенным браузером.|
|[CDHtmlДиалог::GetControlDispatch](#getcontroldispatch)|Извлекает `IDispatch` интерфейс на элемент управления ActiveX, встроенный в HTML-документ.|
|[CDHtmlДиалог:GetControlProperty](#getcontrolproperty)|Извлекает запрашиваемое свойство указанного элемента управления ActiveX.|
|[CDHtmlДиалог::GetCurrentUrl](#getcurrenturl)|Извлекает единый локатор ресурсов (URL), связанный с текущим документом.|
|[CDHtmlDialog::GetDHtmlДокумент](#getdhtmldocument)|Извлекает интерфейс IHTMLDocument2 на загруженном в настоящее время HTML-документе.|
|[CDHtmlДиалог:GetDropTarget](#getdroptarget)|Вызывается, содержащийся в управлении WebBrowser, когда он используется в качестве цели падения, чтобы позволить диалогу поставлять альтернативный [IDropTarget.](/windows/win32/api/oleidl/nn-oleidl-idroptarget)|
|[CDHtmlДиалог::GetElement](#getelement)|Получает интерфейс на элементе HTML.|
|[CDHtmlДиалог::GetElementHtml](#getelementhtml)|Извлекает `innerHTML` свойство html элемента.|
|[CDHtmlДиалог::GetElementInterface](#getelementinterface)|Извлекает запрашиваемый указатель интерфейса из элемента HTML.|
|[CDHtmlДиалог::GetElementProperty](#getelementproperty)|Извлекает значение свойства html элемента.|
|[CDHtmlДиалог::GetElementText](#getelementtext)|Извлекает `innerText` свойство html элемента.|
|[CDHtmlДиалог::GetEvent](#getevent)|Получает `IHTMLEventObj` указатель на текущий объект события.|
|[CDHtmlДиалог::GetExternal](#getexternal)|Получает `IDispatch` интерфейс хоста.|
|[CDHtmlДиалог::GetHostInfo](#gethostinfo)|Извлекает возможности uI-размноза.|
|[CDHtmlДиалог::GetOptionKeyPath](#getoptionkeypath)|Извлекает ключ реестра, под которым хранятся предпочтения пользователей.|
|[CDHtmlДиалог::HideUI](#hideui)|Скрывает ui хозяина.|
|[CDHtmlДиалог::IsexternalDispatchSafe](#isexternaldispatchsafe)|Указывает, является ли `IDispatch` интерфейс хоста безопасным для сценариев.|
|[CDHtmlДиалог::LoadFromResource](#loadfromresource)|Загружает указанный ресурс в управление WebBrowser.|
|[CDHtmlДиалог::Навигация](#navigate)|Переход по указанному URL-адресу.|
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|Вызывается по системе перед навигационным событием.|
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|Вызывается в рамках, чтобы уведомить приложение, когда документ достиг READYSTATE_COMPLETE состоянии.|
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|Вызывается инфраструктурой при активации или деактивации окна документа.|
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|Вызывается фреймворком при активации или деактивации окна кадра.|
|[CDHtmlДиалог::OnInitDialog](#oninitdialog)|Вызывается в ответ на сообщение WM_INITDIALOG.|
|[CDHtmlDialog::OnNavigatecomplete](#onnavigatecomplete)|Вызывается рамкой после завершения навигационного события.|
|[CDHtmlДиалог::ResizeBorder](#resizeborder)|Предупреждает объект о том, что он должен изменить размер своего пограничного пространства.|
|[CDHtmlДиалог::SetControlProperty](#setcontrolproperty)|Устанавливает свойство элемента управления ActiveX на новое значение.|
|[CDHtmlДиалог::SetElementHtml](#setelementhtml)|Устанавливает `innerHTML` свойство элемента HTML.|
|[CDHtmlДиалог::SetElementProperty](#setelementproperty)|Устанавливает свойство html элемента.|
|[CDHtmlДиалог::SetElementText](#setelementtext)|Устанавливает `innerText` свойство элемента HTML.|
|[CDHtmlДиалог::SetExternalDispatch](#setexternaldispatch)|Устанавливает `IDispatch` интерфейс хоста.|
|[CDHtmlДиалог::SetHostFlags](#sethostflags)|Устанавливает флаги uI хоста.|
|[CDHtmlДиалог::ShowContextMenu](#showcontextmenu)|Вызывается, когда меню контекста вот-вот будет отображаться.|
|[CDHtmlDialog::ShowUI](#showui)|Отображается ui-разбивка.|
|[CDHtmlДиалог::TranslateAccelerator](#translateaccelerator)|Вызывается для обработки акселератора меню-ключ сообщений.|
|[CDHtmlДиалог::TranslateUrl](#translateurl)|Вызывается для изменения URL-адреса для загрузки.|
|[CDHtmlДиалог::UpdateUI](#updateui)|Вызывается, чтобы уведомить узла об изменении состояния команды.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDHtmlДиалог::m_bUseHtmlTitle](#m_busehtmltitle)|Указывается, следует ли использовать название HTML-документа в качестве заголовка диалога.|
|[CDHtmlДиалог::m_nHtmlResID](#m_nhtmlresid)|Идентификатор ресурса HTML-ресурса для отображения.|
|[CDHtmlДиалог::m_pBrowserApp](#m_pbrowserapp)|Указатель на приложение веб-браузера.|
|[CDHtmlДиалог::m_spHtmlDoc](#m_sphtmldoc)|Указатель на HTML-документ.|
|[CDHtmlДиалог::m_strCurrentUrl](#m_strcurrenturl)|Текущий URL-|
|[CDHtmlДиалог::m_szHtmlResID](#m_szhtmlresid)|Строковая версия идентификатора ресурса HTML.|

## <a name="remarks"></a>Remarks

`CDHtmlDialog`может загрузить HTML для отображения с ресурса HTML или URL.

`CDHtmlDialog`также может осуществлять обмен данными с помощью HTML-элементов управления и обрабатывать события с html-элементов управления, таких как кнопки нажатий.

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

## <a name="ddx_dhtml-helper-macros"></a><a name="ddx_dhtml_helper_macros"></a>DDX_DHtml Помощник Макрос

Макросы DDX_DHtml помощника обеспечивают легкий доступ к широко используемым свойствам элементов управления на странице HTML.

### <a name="data-exchange-macros"></a>Макрос обмена данными

|||
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Устанавливает или извлекает свойство Значения из выбранного элемента управления.|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Устанавливает или извлекает текст между тегами начала и конца текущего элемента.|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Устанавливает или извлекает HTML между тегами начала и конца текущего элемента.|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Устанавливает или получает URL назначения или точку якоря.|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Устанавливает или извлекает целевое окно или рамку.|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Устанавливает или получает имя изображения или видеоклипа в документе.|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|Устанавливает или извлекает URL-адрес связанного кадра.|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|Устанавливает или извлекает URL-адрес связанного кадра.|

## <a name="cdhtmldialogcanaccessexternal"></a><a name="canaccessexternal"></a>CDHtmlДиалог::CanAccessExternal

Переизвисшая, называемая проверкой доступа, чтобы выяснить, могут ли объекты скрипта на загруженной странице получить доступ к внешней отправке сайта управления. Проверка, чтобы убедиться, что отправка либо безопасна для скриптов, либо текущая зона позволяет объектам, которые не безопасны для сценариев.

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="cdhtmldialogcdhtmldialog"></a><a name="cdhtmldialog"></a>CDHtmlДиалог::CDHtmlДиалог

Строит ресурсо-динамический диалоговой ящик HTML.

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
Строка с нулевым завершением, которая является названием ресурса шаблона диалог-бокса.

*szHtmlResID*<br/>
Строка с нулевым завершением, которая является именем ресурса HTML.

*pParentWnd*<br/>
Указатель на объект окна родителя или владельца (типа [CWnd),](../../mfc/reference/cwnd-class.md)к которому принадлежит объект диалога. Если это NULL, родительское окно объекта диалога устанавливается на основное окно приложения.

*nIDTemplate*<br/>
Содержит идентификационный номер ресурса шаблона диалогового ящика.

*nHtmlResID*<br/>
Содержит идентификационный номер ресурса HTML.

### <a name="remarks"></a>Remarks

Вторая форма конструктора обеспечивает доступ к диалоговому ресурсу через имя шаблона. Третья форма конструктора обеспечивает доступ к ресурсу диалогов через идентификатор шаблона ресурса. Обычно идентификатор начинается с **IDD_** префикса.

## <a name="cdhtmldialogcdhtmldialog"></a><a name="_dtorcdhtmldialog"></a>CDHtmlДиалог:: »CDHtmlДиалог

Уничтожает объект CDHtmlDialog.

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>Remarks

Функция члена [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) должна использоваться для уничтожения бесрежимных диалоговые ящики, созданные [CDialog::Create](../../mfc/reference/cdialog-class.md#create).

## <a name="cdhtmldialogcreatecontrolsite"></a><a name="createcontrolsite"></a>CDHtmlДиалог::СозданиеControlSite

Чрезмерно используется для создания экземпляра сайта управления для размещения управления WebBrowser в диалоге.

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>Параметры

*pContainer*<br/>
Указатель на объект [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)

*ppSite*<br/>
Указатель на указатель на [COleControlSite](../../mfc/reference/colecontrolsite-class.md).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Вы можете переопределить эту функцию участника, чтобы вернуть экземпляр вашего собственного класса сайта управления.

## <a name="cdhtmldialogddx_dhtml_axcontrol"></a><a name="ddx_dhtml_axcontrol"></a>CDHtmlDialog::DDX-DHtml-AxControl

Обмен данными между переменной участника и значением свойства элемента управления ActiveX на странице HTML.

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

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*szId*<br/>
Значение идентификатора объекта в источнике HTML для управления ActiveX.

*Dispid*<br/>
Идентификатор отправки свойства, с которым вы хотите обмениваться данными.

*szPropName*<br/>
Имя свойства.

*Var*<br/>
Член данных, типа VARIANT, [COleVariant](../../mfc/reference/colevariant-class.md), или [CComVariant](../../atl/reference/ccomvariant-class.md), который держит значение, обмениваемое с свойством управления ActiveX.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]

## <a name="cdhtmldialogddx_dhtml_checkbox"></a><a name="ddx_dhtml_checkbox"></a>CDHtmlDialog::DDX-DHtml

Обменивается данными между переменной участника и флажкой на странице HTML.

```
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,
    LPCTSTR szId,
    int& value);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*szId*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*value*<br/>
Значение обменивается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

## <a name="cdhtmldialogddx_dhtml_elementtext"></a><a name="ddx_dhtml_elementtext"></a>CDHtmlDialog::DDX-DHtml-ЭлементТекст

Обменивается данными между переменной участника и любым свойством HTML-элемента на странице HTML.

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

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*szId*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*Dispid*<br/>
Идентификатор отправки HTML-элемента, с помощью которого требуется обмен данными.

*value*<br/>
Значение обменивается.

## <a name="cdhtmldialogddx_dhtml_radio"></a><a name="ddx_dhtml_radio"></a>CDHtmlDialog::DDX-DHtml

Обмен данными между переменной участника и радиокнопкой на странице HTML.

```
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*szId*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*value*<br/>
Значение обменивается.

## <a name="cdhtmldialogddx_dhtml_selectindex"></a><a name="ddx_dhtml_selectindex"></a>CDHtmlDialog::DDX-DHtml-SelectIndex

Получает или устанавливает индекс окна списка на странице HTML.

```
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*szId*<br/>
Значение, указанное для `id` параметра HTML-управления.

*value*<br/>
Значение обменивается.

## <a name="cdhtmldialogddx_dhtml_selectstring"></a><a name="ddx_dhtml_selectstring"></a>CDHtmlDialog::DDX-DHtml-SelectString

Получает или устанавливает отображение текста ввода окна списка (на основе текущего индекса) на странице HTML.

```
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*szId*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*value*<br/>
Значение обменивается.

## <a name="cdhtmldialogddx_dhtml_selectvalue"></a><a name="ddx_dhtml_selectvalue"></a>CDHtmlDialog::DDX-DHtml-SelectValue

Получает или устанавливает значение входа в поле списка (на основе текущего индекса) на странице HTML.

```
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>Параметры

*Pdx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*szId*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*value*<br/>
Значение обменивается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

## <a name="cdhtmldialogdestroymodeless"></a><a name="destroymodeless"></a>CDHtmlДиалог: :Dбезудейбез

Отсоединяет от объекта нережимную диалоговую коробку `CDHtmlDialog` и уничтожает объект.

```
void DestroyModeless();
```

## <a name="cdhtmldialogenablemodeless"></a><a name="enablemodeless"></a>CDHtmlДиалог::Безудержный

Включает в себя бесрежимные диалоговые ящики.

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>Параметры

*fEnable*<br/>
Смотрите *в* [IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)) в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialogfilterdataobject"></a><a name="filterdataobject"></a>CDHtmlДиалог::FilterDataObject

Позволяет диалогу фильтровать объекты данных буфера обмена, созданные размещенным браузером.

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>Параметры

*Pdo*<br/>
Смотрите *pDO* в [IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)) в SDK Windows.

*ppDORet*<br/>
Смотрите *ppDORet* в `IDocHostUIHandler::FilterDataObject` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Remarks

Эта функция является CDHtmlDialog реализации [IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialoggetcontroldispatch"></a><a name="getcontroldispatch"></a>CDHtmlДиалог::GetControlDispatch

Извлекает `IDispatch` интерфейс на элемент управления ActiveX, встроенный в HTML-документ, возвращенный [GetDHtmlDocument.](#getdhtmldocument)

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>Параметры

*szId*<br/>
HTML ID управления ActiveX.

*ppdisp*<br/>
Интерфейс `IDispatch` управления, если он находится на веб-странице.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="cdhtmldialoggetcontrolproperty"></a><a name="getcontrolproperty"></a>CDHtmlДиалог:GetControlProperty

Извлекает запрашиваемое свойство указанного элемента управления ActiveX.

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
HTML ID управления ActiveX.

*szPropName*<br/>
Имя свойства в локальном потоке по умолчанию текущего пользователя.

*pdispControl*<br/>
Указатель `IDispatch` управления ActiveX.

*Dispid*<br/>
Идентификатор отправки свойства.

### <a name="return-value"></a>Возвращаемое значение

Вариант, содержащий запрошенное свойство, или пустой вариант, если элемент управления или свойство не могут быть найдены.

### <a name="remarks"></a>Remarks

Перегрузки перечислены от наименее эффективных в верхней части до наиболее эффективных в нижней части.

## <a name="cdhtmldialoggetcurrenturl"></a><a name="getcurrenturl"></a>CDHtmlДиалог::GetCurrentUrl

Извлекает единый локатор ресурсов (URL), связанный с текущим документом.

```
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>Параметры

*szUrl*<br/>
Объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий URL для извлечения.

## <a name="cdhtmldialoggetdhtmldocument"></a><a name="getdhtmldocument"></a>CDHtmlDialog::GetDHtmlДокумент

Извлекает интерфейс [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) на загруженном в настоящее время HTML-документе.

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>Параметры

* \* \** Указатель на указатель на HTML-документ.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT. Возвращает S_OK в случае успеха.

## <a name="cdhtmldialoggetdroptarget"></a><a name="getdroptarget"></a>CDHtmlДиалог:GetDropTarget

Вызывается, содержащийся в управлении WebBrowser, когда он используется в качестве цели падения, чтобы позволить диалогу поставлять альтернативный [IDropTarget.](/windows/win32/api/oleidl/nn-oleidl-idroptarget)

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>Параметры

*pDropTarget*<br/>
Смотрите *pDropTarget* в [IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)) в Windows SDK.

*ppDropTarget*<br/>
Смотрите *ppDropTarget* в `IDocHostUIHandler::GetDropTarget` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialoggetelement"></a><a name="getelement"></a>CDHtmlДиалог::GetElement

Возвращает интерфейс на html элемент, указанный *szElementId.*

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

*szЭлементИд*<br/>
Идентификатор html элемента.

*ppdisp*<br/>
Указатель `IDispatch` на запрашиваемый элемент или набор элементов.

*pbКоллекция*<br/>
BOOL, указывающий, является ли объект, представленный *PPDisp,* единым элементом или набором элементов.

*pphtmlElement*<br/>
Указатель `IHTMLElement` на запрашиваемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Используйте первую перегрузку, если вам нужно обрабатывать условия, в которых может быть несколько элементов с указанным идентификатором. Вы можете использовать последний параметр, чтобы узнать, является ли возвращенный указатель интерфейса для коллекции или одного элемента. Если указатель интерфейса находится в коллекции, `IHTMLElementCollection` можно запросить и использовать его `item` свойство для обозначения элементов по ординаторскому положению.

Вторая перегрузка завершится неудачей, если на странице есть более одного элемента с тем же идентификатором.

## <a name="cdhtmldialoggetelementhtml"></a><a name="getelementhtml"></a>CDHtmlДиалог::GetElementHtml

Извлекает `innerHTML` свойство html элемента, идентифицированного *szElementId*.

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>Параметры

*szЭлементИд*<br/>
Идентификатор html элемента.

### <a name="return-value"></a>Возвращаемое значение

Свойство `innerHTML` html элемента, идентифицированного *szElementId* или NULL, если элемент не может быть найден.

## <a name="cdhtmldialoggetelementinterface"></a><a name="getelementinterface"></a>CDHtmlДиалог::GetElementInterface

Извлекает запрашиваемый указатель интерфейса из элемента HTML, идентифицированного *szElementId.*

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

*szЭлементИд*<br/>
Идентификатор html элемента.

*ppvObj*<br/>
Адрес указателя, который будет заполнен запрашиваемым указателем интерфейса, если элемент найден и запрос будет успешным.

*refiid*<br/>
Идентификатор интерфейса (IID) запрашиваемого интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

## <a name="cdhtmldialoggetelementproperty"></a><a name="getelementproperty"></a>CDHtmlДиалог::GetElementProperty

Извлекает значение свойства, идентифицированное *dispId,* из элемента HTML, идентифицированного *szElementId.*

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId);
```

### <a name="parameters"></a>Параметры

*szЭлементИд*<br/>
Идентификатор html элемента.

*Dispid*<br/>
Идентификатор отправки свойства.

### <a name="return-value"></a>Возвращаемое значение

Значение свойства или пустой вариант, если свойство или элемент не может быть найдено.

## <a name="cdhtmldialoggetelementtext"></a><a name="getelementtext"></a>CDHtmlДиалог::GetElementText

Извлекает `innerText` свойство html элемента, идентифицированного *szElementId*.

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>Параметры

*szЭлементИд*<br/>
Идентификатор html элемента.

### <a name="return-value"></a>Возвращаемое значение

Свойство `innerText` html-элемента, идентифицированного *szElementId* или NULL, если свойство или элемент не может быть найдено.

## <a name="cdhtmldialoggetevent"></a><a name="getevent"></a>CDHtmlДиалог::GetEvent

`IHTMLEventObj` Возвращает указатель на объект текущего события.

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>Параметры

*ppEventObj*<br/>
Адрес указателя, который будет заполнен `IHTMLEventObj` указателем интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Эта функция должна вызываться только из обработчика событий DHTML.

## <a name="cdhtmldialoggetexternal"></a><a name="getexternal"></a>CDHtmlДиалог::GetExternal

Получает `IDispatch` интерфейс хоста.

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>Параметры

*ppDispatch*<br/>
Смотрите *ppDispatch* в [IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех или E_NOTIMPL на неудачу.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialoggethostinfo"></a><a name="gethostinfo"></a>CDHtmlДиалог::GetHostInfo

Извлекает возможности uI-размноза.

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>Параметры

*pInfo*<br/>
Смотрите *pInfo* в [IDocHostUIHandler::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialoggetoptionkeypath"></a><a name="getoptionkeypath"></a>CDHtmlДиалог::GetOptionKeyPath

Извлекает ключ реестра, под которым хранятся предпочтения пользователей.

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>Параметры

*pchKey*<br/>
Смотрите *pchKey* в [IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)) в Windows SDK.

*dw*<br/>
Смотрите *dw* в `IDocHostUIHandler::GetOptionKeyPath` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialoghideui"></a><a name="hideui"></a>CDHtmlДиалог::HideUI

Скрывает ui хозяина.

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialogisexternaldispatchsafe"></a><a name="isexternaldispatchsafe"></a>CDHtmlДиалог::IsexternalDispatchSafe

Указывает, является ли `IDispatch` интерфейс хоста безопасным для сценариев.

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает FALSE.

## <a name="cdhtmldialogloadfromresource"></a><a name="loadfromresource"></a>CDHtmlДиалог::LoadFromResource

Загружает указанный ресурс в управление WebBrowser в диалоге DHTML.

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>Параметры

*lpszРесурс*<br/>
Указатель строки, содержащей имя ресурса для загрузки.

*nRes*<br/>
Идентификатор загружаемого ресурса.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

## <a name="cdhtmldialogm_busehtmltitle"></a><a name="m_busehtmltitle"></a>CDHtmlДиалог::m_bUseHtmlTitle

Указывается, следует ли использовать название HTML-документа в качестве заголовка диалога.

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>Remarks

Если **m** **и bUseHtmlTitle** является правдой, подпись к диалогу устанавливается равна названию документа HTML; в противном случае используется заголовок в ресурсе диалога.

## <a name="cdhtmldialogm_nhtmlresid"></a><a name="m_nhtmlresid"></a>CDHtmlДиалог::m_nHtmlResID

Идентификатор ресурса HTML-ресурса для отображения.

```
UINT m_nHtmlResID;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]

## <a name="cdhtmldialogm_pbrowserapp"></a><a name="m_pbrowserapp"></a>CDHtmlДиалог::m_pBrowserApp

Указатель на приложение веб-браузера.

```
CComPtr <IWebBrowser2> m_pBrowserApp;
```

## <a name="cdhtmldialogm_sphtmldoc"></a><a name="m_sphtmldoc"></a>CDHtmlДиалог::m_spHtmlDoc

Указатель на HTML-документ.

```
CComPtr<IHTMLDocument2> m_spHtmlDoc;
```

## <a name="cdhtmldialogm_strcurrenturl"></a><a name="m_strcurrenturl"></a>CDHtmlДиалог::m_strCurrentUrl

Текущий URL-

```
CString m_strCurrentUrl;
```

## <a name="cdhtmldialogm_szhtmlresid"></a><a name="m_szhtmlresid"></a>CDHtmlДиалог::m_szHtmlResID

Строковая версия идентификатора ресурса HTML.

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

## <a name="cdhtmldialognavigate"></a><a name="navigate"></a>CDHtmlДиалог::Навигация

Переходит к ресурсу, идентифицированному по URL, указанному *lpszURL.*

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
Указатель на строку, содержащую URL для таргетинга.

*dwFlags*<br/>
Флаги переменной, которая определяет, следует ли добавлять ресурс в список истории, следует ли читать кэш или писать из кэша, и следует ли отображать ресурс в новом окне. Переменная может быть комбинацией значений, определенных [перечислением BrowserNavConstants.](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768360\(v=vs.85\))

*lpszTargetFrameName*<br/>
Указатель на строку, содержащую имя кадра, в котором отображается ресурс.

*lpszHeaders*<br/>
Указатель на значение, которое определяет заголовки HTTP для отправки на сервер. Эти заголовки добавляются в заголовки Internet Explorer по умолчанию. Заголовки могут указать такую информацию, как действие, требуемое от сервера, тип данных, передаваемых на сервер, или код состояния. Этот параметр игнорируется, если URL не является URL HTTP.

*lpvPostData*<br/>
Указатель на данные для отправки с транзакцией HTTP POST. Например, транзакция POST используется для отправки данных, собранных в форме HTML. Если этот параметр не указывает `Navigate` какие-либо данные о публикации, выдает транзакцию HTTP GET. Этот параметр игнорируется, если URL не является URL HTTP.

*dwPostDataLen*<br/>
Данные для отправки с транзакцией HTTP POST. Например, транзакция POST используется для отправки данных, собранных в форме HTML. Если этот параметр не указывает `Navigate` какие-либо данные о публикации, выдает транзакцию HTTP GET. Этот параметр игнорируется, если URL не является URL HTTP.

## <a name="cdhtmldialogonbeforenavigate"></a><a name="onbeforenavigate"></a>CDHtmlDialog::OnBeforeNavigate

Вызывается инфраструктурой, чтобы вызвать событие к пожару до навигации происходит.

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
Указатель на объект `IDispatch`.

*szUrl*<br/>
Указатель на строку, содержащую URL для навигации.

## <a name="cdhtmldialogondocumentcomplete"></a><a name="ondocumentcomplete"></a>CDHtmlDialog::OnDocumentComplete

Вызывается в рамках, чтобы уведомить приложение, когда документ достиг READYSTATE_COMPLETE состояния.

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
Указатель на объект `IDispatch`.

*szUrl*<br/>
Указатель на строку, содержащую URL,который был перемещаться.

## <a name="cdhtmldialogondocwindowactivate"></a><a name="ondocwindowactivate"></a>CDHtmlDialog::OnDocWindowActivate

Вызывается инфраструктурой при активации или деактивации окна документа.

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Параметры

*fАктивировать*<br/>
Смотрите *fActivate* в [IDocHostUIHandler::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)) в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialogonframewindowactivate"></a><a name="onframewindowactivate"></a>CDHtmlDialog::OnFrameWindowActivate

Вызывается фреймворком при активации или деактивации окна кадра.

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>Параметры

*fАктивировать*<br/>
Смотрите *fActivate* в [IDocHostUIHandler::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)) в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Эта функция является CDHtmlDialog реализации [IDocHostUIHandler::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialogoninitdialog"></a><a name="oninitdialog"></a>CDHtmlДиалог::OnInitDialog

Вызывается в ответ на сообщение WM_INITDIALOG.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает TRUE.

### <a name="remarks"></a>Remarks

Это сообщение отправляется в поле `Create`диалога `CreateIndirect`во `DoModal` время , или звонки, которые происходят непосредственно перед диалоговое окно отображается.

Переопределить эту функцию члена, если вам нужно выполнить специальную обработку, когда диалоговый ящик инициализирован. В перевернутой версии сначала `OnInitDialog` позвоните в базовый класс, но игнорируйте его значение возврата. Вы, как правило, вернуться TRUE от переопределенной функции члена.

Windows называет `OnInitDialog` функцию через стандартную глобальную процедуру диалог-бокс, общую для всех диалоговых коробок Microsoft Foundation Class Library, а не через карту сообщений, так что вам не нужна запись на карту сообщений для этой функции участника.

## <a name="cdhtmldialogonnavigatecomplete"></a><a name="onnavigatecomplete"></a>CDHtmlDialog::OnNavigatecomplete

Вызов фреймворка после навигации по указанному URL-адресу завершен.

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>Параметры

*pDisp*<br/>
Указатель на объект `IDispatch`.

*szUrl*<br/>
Указатель на строку, содержащую URL,который был перемещаться.

## <a name="cdhtmldialogresizeborder"></a><a name="resizeborder"></a>CDHtmlДиалог::ResizeBorder

Предупреждает объект о том, что он должен изменить размер своего пограничного пространства.

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>Параметры

*prcBorder*<br/>
Смотрите *prcBorder* в [IDocHostUIHandler::ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\)) в Windows SDK.

*pUIWindow*<br/>
Смотрите *pUIWindow* в `IDocHostUIHandler::ResizeBorder` Windows SDK.

*fFrameWindow*<br/>
Смотрите *fFrameWindow* в `IDocHostUIHandler::ResizeBorder` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

## <a name="cdhtmldialogsetcontrolproperty"></a><a name="setcontrolproperty"></a>CDHtmlДиалог::SetControlProperty

Устанавливает свойство элемента управления ActiveX на новое значение.

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

*szЭлементИд*<br/>
HTML ID управления ActiveX.

*Dispid*<br/>
Идентификатор отправки свойства для установки.

*pVar*<br/>
Указатель на VARIANT, содержащий новое значение свойства.

*pdispControl*<br/>
Указатель на `IDispatch` интерфейс управления ActiveX.

*szPropName*<br/>
Строка, содержащая название свойства для установки.

## <a name="cdhtmldialogsetelementhtml"></a><a name="setelementhtml"></a>CDHtmlДиалог::SetElementHtml

Устанавливает `innerHTML` свойство элемента HTML.

```
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Параметры

*szЭлементИд*<br/>
Идентификатор html элемента.

*bstrText*<br/>
Новое значение свойства `innerHTML`.

*панкЭлем*<br/>
Указатель `IUnknown` элемента HTML.

## <a name="cdhtmldialogsetelementproperty"></a><a name="setelementproperty"></a>CDHtmlДиалог::SetElementProperty

Устанавливает свойство html элемента.

```
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);
```

### <a name="parameters"></a>Параметры

*szЭлементИд*<br/>
Идентификатор html элемента.

*Dispid*<br/>
Идентификатор отправки свойства для установки.

*pVar*<br/>
Новое значение свойства.

## <a name="cdhtmldialogsetelementtext"></a><a name="setelementtext"></a>CDHtmlДиалог::SetElementText

Устанавливает `innerText` свойство элемента HTML.

```
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>Параметры

*szЭлементИд*<br/>
Идентификатор html элемента.

*bstrText*<br/>
Новое значение свойства `innerText`.

*панкЭлем*<br/>
Указатель `IUnknown` элемента HTML.

## <a name="cdhtmldialogsetexternaldispatch"></a><a name="setexternaldispatch"></a>CDHtmlДиалог::SetExternalDispatch

Устанавливает `IDispatch` интерфейс хоста.

```
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>Параметры

*pdispВнешний*<br/>
Новый `IDispatch` интерфейс.

## <a name="cdhtmldialogsethostflags"></a><a name="sethostflags"></a>CDHtmlДиалог::SetHostFlags

Устанавливает флаги разбивки uI.

```
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Для возможных [значений см.](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753277\(v=vs.85\))

## <a name="cdhtmldialogshowcontextmenu"></a><a name="showcontextmenu"></a>CDHtmlДиалог::ShowContextMenu

Вызывается, когда меню контекста вот-вот будет отображаться.

```
STDMETHOD(ShowContextMenu)(
    DWORD dwID,
    POINT* ppt,
    IUnknown* pcmdtReserved,
    IDispatch* pdispReserved);
```

### <a name="parameters"></a>Параметры

*dwID*<br/>
Смотрите *dwID* в [IDocHostUIHandler::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)) в Windows SDK.

*Ppt*<br/>
Смотрите *ppt* в `IDocHostUIHandler::ShowContextMenu` Windows SDK.

*PCmdtReserved*<br/>
Смотрите *pcmdtReserved* в `IDocHostUIHandler::ShowContextMenu` Windows SDK.

*pdispReserved*<br/>
Смотрите *pdispReserved* в `IDocHostUIHandler::ShowContextMenu` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Remarks

Эта функция является CDHtmlDialog реализации [IDocHostUIHandler::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialogshowui"></a><a name="showui"></a>CDHtmlDialog::ShowUI

Отображается ui-разбивка.

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
Смотрите *dwID* в [IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)) в Windows SDK.

*pActiveObject*<br/>
Смотрите *d pActiveObject* в `IDocHostUIHandler::ShowUI` Windows SDK.

*pCommandTarget*<br/>
Смотрите *pCommandTarget* в `IDocHostUIHandler::ShowUI` Windows SDK.

*pFrame*<br/>
Смотрите *pFrame* в `IDocHostUIHandler::ShowUI` Windows SDK.

*pDoc*<br/>
Смотрите *pDoc* в `IDocHostUIHandler::ShowUI` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialogtranslateaccelerator"></a><a name="translateaccelerator"></a>CDHtmlДиалог::TranslateAccelerator

Вызывается для обработки акселератора меню-ключ сообщений.

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>Параметры

*lpMsg*<br/>
Смотрите *lpMsg* в [IDocHostUIHandler::TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)) в Windows SDK.

*pguidCmdGroup*<br/>
Смотрите *pguidCmdGroup* в `IDocHostUIHandler::TranslateAccelerator` Windows SDK.

*nCmdID*<br/>
Смотрите *nCmdID* в `IDocHostUIHandler::TranslateAccelerator` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialogtranslateurl"></a><a name="translateurl"></a>CDHtmlДиалог::TranslateUrl

Вызывается для изменения URL-адреса для загрузки.

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>Параметры

*dwПеревод*<br/>
Смотрите *dwTranslate* в [IDocHostUIHandler::TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)) в Windows SDK.

*pchURLIn*<br/>
*См. pchURLIn* в `IDocHostUIHandler::TranslateUrl` Windows SDK.

*ppchURLOut*<br/>
Смотрите *ppchURLOut* в `IDocHostUIHandler::TranslateUrl` Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_FALSE.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)), как описано в Windows SDK.

## <a name="cdhtmldialogupdateui"></a><a name="updateui"></a>CDHtmlДиалог::UpdateUI

Вызывается, чтобы уведомить узла об изменении состояния команды.

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Remarks

Эта функция члена является cdHtmlDialog реализации [IDocHostUIHandler::UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\)), как описано в Windows SDK.

## <a name="see-also"></a>См. также раздел

[MFC Образец DHtmlExplore](../../overview/visual-cpp-samples.md)<br/>
[Вспомогательные макросы DDX_DHtml](#ddx_dhtml_helper_macros)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
