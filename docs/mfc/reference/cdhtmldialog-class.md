---
title: "Класс CDHtmlDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CDHtmlDialog class
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: adf3664da1ecd1bdde9a1bd13e5b43ab7695e4d7
ms.lasthandoff: 02/24/2017

---
# <a name="cdhtmldialog-class"></a>Класс CDHtmlDialog
Используется для создания диалоговых окон, использующих HTML вместо ресурсов диалогового окна для своей реализации интерфейса пользователя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDHtmlDialog : public CDialog, public CDHtmlEventSink  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|Создает объект CDHtmlDialog.|  
|[CDHtmlDialog:: ~ CDHtmlDialog](#cdhtmldialog__~cdhtmldialog)|Уничтожает объект CDHtmlDialog.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|Overridable, вызывается как проверку доступа для просмотра, возможен ли доступ к внешней распределения узла управления сценариев объектов на странице загрузки. Проверяет, что перенаправления позволяет безопасно для сценариев либо текущей зоны объекты, которые не являются безопасными для использования в сценариях.|  
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|Overridable используется для создания экземпляра элемента управления узла для размещения элемента управления WebBrowser в диалоговом окне.|  
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|Обмен данными между переменной-члена и значение свойства элемента управления ActiveX HTML-страницы.|  
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|Обмен данными между переменной-члена и флажок на странице HTML.|  
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|Обмен данными между переменной-члена и любое свойство элемента HTML на странице HTML.|  
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|Обмен данными между переменной-члена и переключатель на странице HTML.|  
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|Возвращает или задает индекс в списке на странице HTML.|  
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|Возвращает или задает отображаемый текст записи поле списка (на основе текущего индекса) на странице HTML.|  
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|Возвращает или задает значение записи поле списка (на основе текущего индекса) на странице HTML.|  
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|Уничтожает немодального диалогового окна.|  
|[CDHtmlDialog::EnableModeless](#enablemodeless)|Позволяет немодальных диалоговых окон.|  
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|Позволяет диалогового окна, чтобы отфильтровать объекты данных буфера обмена, созданные в размещенной браузера.|  
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|Извлекает `IDispatch` интерфейса на элемент управления ActiveX, внедренные в документ HTML.|  
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|Возвращает запрошенное свойство указанного элемента управления ActiveX.|  
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|Получает унифицированный указатель ресурса (URL) связанный с текущим документом.|  
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|Получает интерфейс IHTMLDocument2 в текущем загруженном документе HTML.|  
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|Вызывается содержащегося элемента управления WebBrowser, когда он используется в качестве объекта-приемника разрешающее диалогового окна, чтобы указать альтернативный [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CDHtmlDialog::GetElement](#getelement)|Возвращает интерфейс для элемента HTML.|  
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|Извлекает **innerHTML** свойство элемента HTML.|  
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|Получает указатель на запрошенный интерфейс из HTML-элемента.|  
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|Извлекает значение свойства элемента HTML.|  
|[CDHtmlDialog::GetElementText](#getelementtext)|Извлекает **innerText** свойство элемента HTML.|  
|[CDHtmlDialog::GetEvent](#getevent)|Возвращает **IHTMLEventObj** указатель на текущий объект события.|  
|[CDHtmlDialog::GetExternal](#getexternal)|Получает узел `IDispatch` интерфейса.|  
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|Возвращает возможности пользовательского интерфейса узла.|  
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|Получает раздел реестра, в которой хранятся пользовательские настройки.|  
|[CDHtmlDialog::HideUI](#hideui)|Скрывает пользовательский Интерфейс узла.|  
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|Указывает, является ли узла `IDispatch` интерфейс безопасные.|  
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|Загружает указанный ресурс в элемент управления WebBrowser.|  
|[CDHtmlDialog::Navigate](#navigate)|Переходит к указанному URL-АДРЕСУ.|  
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|Вызывается средой перед события навигации.|  
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|Вызывается платформой для уведомления приложения при достижении документа `READYSTATE_COMPLETE` состояния.|  
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|Вызывается платформой, когда включается или отключается в окне документа.|  
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|Вызывается платформой, если окно активируется или деактивируется.|  
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|Вызывается в ответ на **WM_INITDIALOG** сообщение.|  
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|Вызывается платформой после завершения события навигации.|  
|[CDHtmlDialog::ResizeBorder](#resizeborder)|Предупреждения, если нужно изменить размер пространства границы объекта.|  
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|Задает для свойства элемента управления ActiveX на новое значение.|  
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|Наборы **innerHTML** свойство элемента HTML.|  
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|Задает свойство элемента HTML.|  
|[CDHtmlDialog::SetElementText](#setelementtext)|Наборы **innerText** свойство элемента HTML.|  
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|Задает узел `IDispatch` интерфейса.|  
|[CDHtmlDialog::SetHostFlags](#sethostflags)|Задает флаги пользовательского интерфейса узла.|  
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|Вызывается сразу перед отображением контекстного меню.|  
|[CDHtmlDialog::ShowUI](#showui)|Показан пользовательский Интерфейс узла.|  
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|Вызывается для обработки сообщений сочетаний клавиш меню.|  
|[CDHtmlDialog::TranslateUrl](#translateurl)|Вызывается, чтобы изменить URL-адрес для загрузки.|  
|[CDHtmlDialog::UpdateUI](#updateui)|Вызывается для уведомления узла об изменении состояния команды.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|Указывает, следует ли использовать название документа HTML в качестве заголовка диалогового окна.|  
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|Ресурс ресурсов код HTML для отображения.|  
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Указатель для приложения веб-браузера.|  
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|Указатель на документ HTML.|  
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|Текущий URL-адрес.|  
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|Строковая версия идентификатора ресурса HTML.|  
  
## <a name="remarks"></a>Примечания  
 **CDHtmlDialog** можно загрузить код HTML для отображения из ресурс HTML или URL-адрес.  
  
 `CDHtmlDialog`Можно также данные exchange с HTML-элементы управления и обработки событий от HTML-элементы управления, например при нажатии кнопки.  
  
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
  
##  <a name="ddx_dhtml_helper_macros"></a>Макросы вспомогательные DDX_DHtml  
 Макросы вспомогательный DDX_DHtml обеспечивают простой доступ к часто используемые свойства элементов управления на странице HTML.  
  
### <a name="data-exchange-macros"></a>Макросы данных Exchange  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|Задает или получает значение свойства выбранного элемента управления.|  
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|Задает или получает текст между тегами начала и окончания для текущего элемента.|  
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|Устанавливает или извлекает HTML между открывающий и закрывающий теги текущего элемента.|  
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|Задает или получает конечная точка URL-адрес или привязки.|  
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|Задает или получает целевое окно или фрейм.|  
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|Задает или получает имя изображения или видеоклипа в документ.|  
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|Задает или получает URL-адрес связанного фрейма.|  
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|Задает или получает URL-адрес связанного фрейма.|  
  
##  <a name="canaccessexternal"></a>CDHtmlDialog::CanAccessExternal  
 Overridable, вызывается как проверку доступа для просмотра, возможен ли доступ к внешней распределения узла управления сценариев объектов на странице загрузки. Проверяет, что перенаправления позволяет безопасно для сценариев либо текущей зоны объекты, которые не являются безопасными для использования в сценариях.  
  
```  
virtual BOOL CanAccessExternal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="cdhtmldialog"></a>CDHtmlDialog::CDHtmlDialog  
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
 `lpszTemplateName`  
 Завершающим нулем строка, представляющая имя ресурс шаблона диалоговых окон.  
  
 `szHtmlResID`  
 Завершающим нулем строка, представляющая имя ресурса HTML.  
  
 `pParentWnd`  
 Указатель на объект окна родительского или владелец (типа [CWnd](../../mfc/reference/cwnd-class.md)), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского окна объекта диалогового окна.  
  
 `nIDTemplate`  
 Содержит идентификатор ресурс шаблона диалоговых окон.  
  
 `nHtmlResID`  
 Содержит идентификатор ресурса HTML.  
  
### <a name="remarks"></a>Примечания  
 Вторая форма конструктора предоставляет доступ к ресурс диалогового окна через имя шаблона. Третья форма конструктора предоставляет доступ к ресурс через идентификатор ресурса шаблона диалогового окна. Как правило, идентификатор начинается с **IDD_** префикс.  
  
##  <a name="_dtorcdhtmldialog"></a>CDHtmlDialog:: ~ CDHtmlDialog  
 Уничтожает объект CDHtmlDialog.  
  
```  
virtual ~CDHtmlDialog();
```  
  
### <a name="remarks"></a>Примечания  
 [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) функция-член, необходимо использовать для уничтожения безрежимные диалоговые окна, созданные [CDialog::Create](../../mfc/reference/cdialog-class.md#create).  
  
##  <a name="createcontrolsite"></a>CDHtmlDialog::CreateControlSite  
 Overridable используется для создания экземпляра элемента управления узла для размещения элемента управления WebBrowser в диалоговом окне.  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT /* nID */,  
    REFCLSID /* clsid */);
```  
  
### <a name="parameters"></a>Параметры  
 `pContainer`  
 Указатель на [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) объекта  
  
 `ppSite`  
 Указатель на указатель на [COleControlSite](../../mfc/reference/colecontrolsite-class.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить эту функцию-член для возврата экземпляра класса сайта собственного элемента управления.  
  
##  <a name="ddx_dhtml_axcontrol"></a>CDHtmlDialog::DDX_DHtml_AxControl  
 Обмен данными между переменной-члена и значение свойства элемента управления ActiveX HTML-страницы.  
  
```  
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    VARIANT& var);

 
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    LPCTSTR szPropName,  
    VARIANT& var);
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `szId`  
 Значение параметра ID тега object в источнике HTML для элемента управления ActiveX.  
  
 `dispid`  
 Идентификатор диспетчеризации свойство, с которым вы хотите обмениваться данными.  
  
 `szPropName`  
 Имя свойства.  
  
 `var`  
 Элемент данных типа `VARIANT`, [COleVariant](../../mfc/reference/colevariant-class.md), или [CComVariant](../../atl/reference/ccomvariant-class.md), которая содержит значение, обмен которыми осуществляется с помощью свойства элемента управления ActiveX.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCHtmlHttp&#1;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]  
  
##  <a name="ddx_dhtml_checkbox"></a>CDHtmlDialog::DDX_DHtml_CheckBox  
 Обмен данными между переменной-члена и флажок на странице HTML.  
  
```  
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    int& value);
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `szId`  
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 *value*  
 Значение при обмене.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCHtmlHttp&#2;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]  
  
##  <a name="ddx_dhtml_elementtext"></a>CDHtmlDialog::DDX_DHtml_ElementText  
 Обмен данными между переменной-члена и любое свойство элемента HTML на странице HTML.  
  
```  
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    CString& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    short& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    int& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    long& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    DWORD& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    float& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `szId`  
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 *Идентификатор DISPID*  
 Идентификатор отправки HTML-элемента, с которым вы хотите обмениваться данными.  
  
 *value*  
 Значение при обмене.  
  
##  <a name="ddx_dhtml_radio"></a>CDHtmlDialog::DDX_DHtml_Radio  
 Обмен данными между переменной-члена и переключатель на странице HTML.  
  
```  
void DDX_DHtml_Radio(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `szId`  
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 *value*  
 Значение при обмене.  
  
##  <a name="ddx_dhtml_selectindex"></a>CDHtmlDialog::DDX_DHtml_SelectIndex  
 Возвращает или задает индекс в списке на странице HTML.  
  
```  
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `szId`  
 Значение, указанное для параметра id HTML-элемент управления.  
  
 *value*  
 Значение при обмене.  
  
##  <a name="ddx_dhtml_selectstring"></a>CDHtmlDialog::DDX_DHtml_SelectString  
 Возвращает или задает отображаемый текст записи поле списка (на основе текущего индекса) на странице HTML.  
  
```  
void DDX_DHtml_SelectString(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `szId`  
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 *value*  
 Значение при обмене.  
  
##  <a name="ddx_dhtml_selectvalue"></a>CDHtmlDialog::DDX_DHtml_SelectValue  
 Возвращает или задает значение записи поле списка (на основе текущего индекса) на странице HTML.  
  
```  
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>Параметры  
 `pDX`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `szId`  
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 *value*  
 Значение при обмене.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCHtmlHttp&#3;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]  
  
##  <a name="destroymodeless"></a>CDHtmlDialog::DestroyModeless  
 Отсоединяет немодальное диалоговое окно `CDHtmlDialog` объекта и удаляет объект.  
  
```  
void DestroyModeless();
```  
  
##  <a name="enablemodeless"></a>CDHtmlDialog::EnableModeless  
 Позволяет немодальных диалоговых окон.  
  
```  
STDMETHOD(EnableModeless)(BOOL fEnable);
```  
  
### <a name="parameters"></a>Параметры  
 `fEnable`  
 В разделе `fEnable` в [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="filterdataobject"></a>CDHtmlDialog::FilterDataObject  
 Позволяет диалогового окна, чтобы отфильтровать объекты данных буфера обмена, созданные в размещенной браузера.  
  
```  
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,  
    IDataObject** ppDORet);
```  
  
### <a name="parameters"></a>Параметры  
 `pDO`  
 В разделе `pDO` в [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppDORet`  
 В разделе `ppDORet` в **IDocHostUIHandler::FilterDataObject** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **S_FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcontroldispatch"></a>CDHtmlDialog::GetControlDispatch  
 Извлекает `IDispatch` интерфейса на элемент управления ActiveX, внедренные в документ HTML, возвращаемый [GetDHtmlDocument](#getdhtmldocument).  
  
```  
HRESULT GetControlDispatch(
    LPCTSTR szId,  
    IDispatch** ppdisp);
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 HTML-идентификатор элемента управления ActiveX.  
  
 *ppdisp*  
 `IDispatch` Интерфейса элемента управления Если найти на веб-странице.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="getcontrolproperty"></a>CDHtmlDialog::GetControlProperty  
 Возвращает запрошенное свойство указанного элемента управления ActiveX.  
  
```  
VARIANT GetControlProperty(
    LPCTSTR szId,  
    LPCTSTR szPropName);

 
VARIANT GetControlProperty(
    LPCTSTR szId,  
    DISPID dispid);

 
VARIANT GetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `szId`  
 HTML-идентификатор элемента управления ActiveX.  
  
 `szPropName`  
 Имя свойства на языке по умолчанию текущего пользователя.  
  
 `pdispControl`  
 `IDispatch` Указатель элемента управления ActiveX.  
  
 `dispid`  
 Идентификатор диспетчеризации свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение типа variant, содержащий запрошенное свойство или пустое значение типа variant, если не удалось найти элемент управления или свойства.  
  
### <a name="remarks"></a>Примечания  
 Перегрузки перечисляются от наименее эффективным в верхней для наиболее эффективного внизу.  
  
##  <a name="getcurrenturl"></a>CDHtmlDialog::GetCurrentUrl  
 Получает унифицированный указатель ресурса (URL) связанный с текущим документом.  
  
```  
void GetCurrentUrl(CString& szUrl);
```  
  
### <a name="parameters"></a>Параметры  
 `szUrl`  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий URL-адрес для получения.  
  
##  <a name="getdhtmldocument"></a>CDHtmlDialog::GetDHtmlDocument  
 Извлекает [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) интерфейса на текущем загруженном документе HTML.  
  
```  
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```  
  
### <a name="parameters"></a>Параметры  
 *\*\*pphtmlDoc*  
 Указатель на указатель на документ HTML.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`. Возвращает значение `S_OK` в случае успешного выполнения.  
  
##  <a name="getdroptarget"></a>CDHtmlDialog::GetDropTarget  
 Вызывается содержащегося элемента управления WebBrowser, когда он используется в качестве объекта-приемника разрешающее диалогового окна, чтобы указать альтернативный [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).  
  
```  
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,  
    IDropTarget** ppDropTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pDropTarget`  
 В разделе `pDropTarget` в [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppDropTarget`  
 В разделе `ppDropTarget` в **IDocHostUIHandler::GetDropTarget** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getelement"></a>CDHtmlDialog::GetElement  
 Возвращает интерфейс элемента HTML, определяемого `szElementId`.  
  
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
 `szElementId`  
 Идентификатор HTML-элемента.  
  
 *ppdisp*  
 `IDispatch` Указатель на запрошенный элемент или коллекцию элементов.  
  
 *pbCollection*  
 Объект **BOOL** , указывающее, является ли объект, представленный *ppdisp* одного элемента или коллекции элементов.  
  
 *pphtmlElement*  
 **IHTMLElement** указатель на запрошенный элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Первая перегрузка используется, если необходимо обрабатывать ситуации, в которых может быть более одного элемента с указанным идентификатором. Последний параметр позволяет определить ли возвращаемый указатель интерфейса на коллекцию или один элемент. Если указатель интерфейса на коллекцию, вы можете запрашивать **IHTMLElementCollection** и использовать его **элемент** свойство для ссылки на элементы по порядковому номеру.  
  
 Вторая перегрузка завершится ошибкой, если имеется более одного элемента с тем же Идентификатором страницы.  
  
##  <a name="getelementhtml"></a>CDHtmlDialog::GetElementHtml  
 Извлекает **innerHTML** свойство элемента HTML, определяемого с помощью `szElementId`.  
  
```  
BSTR GetElementHtml(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>Параметры  
 `szElementId`  
 Идентификатор HTML-элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **InnerHTML** свойство элемента HTML, определяемого с помощью `szElementId` или **NULL** Если элемент не найден.  
  
##  <a name="getelementinterface"></a>CDHtmlDialog::GetElementInterface  
 Получает указатель на запрошенный интерфейс из HTML-элемент, идентифицируемый `szElementId`.  
  
```  
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    Q** ppvObj);

 
HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    REFIID riid,  
    void** ppvObj);
```  
  
### <a name="parameters"></a>Параметры  
 `szElementId`  
 Идентификатор HTML-элемента.  
  
 `ppvObj`  
 Адрес указателя, будет заполняться указатель на запрошенный интерфейс найденный элемент и запрос выполняется успешно.  
  
 `riid`  
 Интерфейс идентификатор IID запрошенного интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCHtmlHttp&#4;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]  
  
##  <a name="getelementproperty"></a>CDHtmlDialog::GetElementProperty  
 Возвращает значение свойства, идентифицируемого по `dispid` из HTML-элемент, идентифицируемый `szElementId`.  
  
```  
VARIANT GetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `szElementId`  
 Идентификатор HTML-элемента.  
  
 `dispid`  
 Идентификатор диспетчеризации свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение свойства или пустой вариант, если не удалось найти свойство или элемент.  
  
##  <a name="getelementtext"></a>CDHtmlDialog::GetElementText  
 Извлекает **innerText** свойство элемента HTML, определяемого с помощью `szElementId`.  
  
```  
BSTR GetElementText(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>Параметры  
 `szElementId`  
 Идентификатор HTML-элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **InnerText** свойство элемента HTML, определяемого с помощью `szElementId` или **NULL** Если свойство или элемент не найден.  
  
##  <a name="getevent"></a>CDHtmlDialog::GetEvent  
 Возвращает **IHTMLEventObj** указатель на текущий объект события.  
  
```  
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```  
  
### <a name="parameters"></a>Параметры  
 `ppEventObj`  
 Адрес указателя, будет заполняться **IHTMLEventObj** указатель на интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Эта функция должна вызываться только из обработчика событий DHTML.  
  
##  <a name="getexternal"></a>CDHtmlDialog::GetExternal  
 Получает узел `IDispatch` интерфейса.  
  
```  
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```  
  
### <a name="parameters"></a>Параметры  
 *ppDispatch*  
 В разделе *ppDispatch* в [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` в случае успешного выполнения или **E_NOTIMPL** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gethostinfo"></a>CDHtmlDialog::GetHostInfo  
 Возвращает возможности пользовательского интерфейса узла.  
  
```  
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `pInfo`  
 В разделе `pInfo` в [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getoptionkeypath"></a>CDHtmlDialog::GetOptionKeyPath  
 Получает раздел реестра, в которой хранятся пользовательские настройки.  
  
```  
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,  
    DWORD dw);
```  
  
### <a name="parameters"></a>Параметры  
 `pchKey`  
 В разделе `pchKey` в [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dw`  
 В разделе `dw` в **IDocHostUIHandler::GetOptionKeyPath** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="hideui"></a>CDHtmlDialog::HideUI  
 Скрывает пользовательский Интерфейс узла.  
  
```  
STDMETHOD(HideUI)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="isexternaldispatchsafe"></a>CDHtmlDialog::IsExternalDispatchSafe  
 Указывает, является ли узла `IDispatch` интерфейс безопасные.  
  
```  
virtual BOOL IsExternalDispatchSafe();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **FALSE**.  
  
##  <a name="loadfromresource"></a>CDHtmlDialog::LoadFromResource  
 Загружает указанный ресурс в элемент управления WebBrowser в диалоговое окно DHTML.  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszResource`  
 Указатель на строку, содержащую имя ресурса для загрузки.  
  
 `nRes`  
 Идентификатор ресурса для загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** при успехе; в противном случае **FALSE**.  
  
##  <a name="m_busehtmltitle"></a>CDHtmlDialog::m_bUseHtmlTitle  
 Указывает, следует ли использовать название документа HTML в качестве заголовка диалогового окна.  
  
```  
BOOL m_bUseHtmlTitle;  
```  
  
### <a name="remarks"></a>Примечания  
 Если **m**_ **bUseHtmlTitle** — **true**, заголовок диалогового окна задано равным заголовок документа HTML; в противном случае, используется заголовок на ресурс диалогового окна.  
  
##  <a name="m_nhtmlresid"></a>CDHtmlDialog::m_nHtmlResID  
 Ресурс ресурсов код HTML для отображения.  
  
```  
UINT m_nHtmlResID;  
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCHtmlHttp&#5;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]  
  
##  <a name="m_pbrowserapp"></a>CDHtmlDialog::m_pBrowserApp  
 Указатель для приложения веб-браузера.  
  
```  
CComPtr <IWebBrowser2> m_pBrowserApp;  
```  
  
##  <a name="m_sphtmldoc"></a>CDHtmlDialog::m_spHtmlDoc  
 Указатель на документ HTML.  
  
```  
CComPtr<IHTMLDocument2> m_spHtmlDoc;  
```  
  
##  <a name="m_strcurrenturl"></a>CDHtmlDialog::m_strCurrentUrl  
 Текущий URL-адрес.  
  
```  
CString m_strCurrentUrl;  
```  
  
##  <a name="m_szhtmlresid"></a>CDHtmlDialog::m_szHtmlResID  
 Строковая версия идентификатора ресурса HTML.  
  
```  
LPTSTR m_szHtmlResID;  
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCHtmlHttp №&6;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]  
  
##  <a name="navigate"></a>CDHtmlDialog::Navigate  
 Переходит к ресурсу, определяемому URL-адрес, который задается параметром `lpszURL`.  
  
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
 `lpszURL`  
 Указатель на строку, содержащую URL-адрес целевой.  
  
 `dwFlags`  
 Флаги переменную, которая указывает, следует ли добавить ресурс в список журнала, в кэш чтения или записи из кэша и для отображения ресурса в новом окне. Переменная может быть сочетанием значений, определенных в [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) перечисления.  
  
 `lpszTargetFrameName`  
 Указатель на строку, содержащую имя кадра, в которой отображаются ресурса.  
  
 `lpszHeaders`  
 Указатель на значение, указывающее, заголовки HTTP для отправки на сервер. Эти заголовки добавляются к заголовкам Internet Explorer по умолчанию. Заголовки можно указать такие сведения, как действия, необходимые на сервере, тип данных, передаваемых на сервер или код состояния. Этот параметр игнорируется, если URL-адрес не является URL-адрес HTTP.  
  
 `lpvPostData`  
 Указатель на данные для отправки с помощью операции HTTP POST. Например транзакция POST используется для отправки данных, собранных HTML-форму. Если этот параметр не указан, все данные post **перехода** выдает операции HTTP GET. Этот параметр игнорируется, если URL-адрес не является URL-адрес HTTP.  
  
 `dwPostDataLen`  
 Данные для отправки с помощью операции HTTP POST. Например транзакция POST используется для отправки данных, собранных HTML-форму. Если этот параметр не указан, все данные post **перехода** выдает операции HTTP GET. Этот параметр игнорируется, если URL-адрес не является URL-адрес HTTP.  
  
##  <a name="onbeforenavigate"></a>CDHtmlDialog::OnBeforeNavigate  
 Вызывается платформой для события, возникающего перед его выполнением.  
  
```  
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 Указатель на объект `IDispatch` .  
  
 `szUrl`  
 Указатель на строку, содержащую URL-адрес для перехода.  
  
##  <a name="ondocumentcomplete"></a>CDHtmlDialog::OnDocumentComplete  
 Вызывается платформой для оповещения приложения, когда документ выполнен `READYSTATE_COMPLETE` состояния.  
  
```  
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 Указатель на объект `IDispatch` .  
  
 `szUrl`  
 Указатель на строку, содержащую URL-адрес, по которому был осуществлен переход.  
  
##  <a name="ondocwindowactivate"></a>CDHtmlDialog::OnDocWindowActivate  
 Вызывается платформой, когда включается или отключается в окне документа.  
  
```  
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>Параметры  
 `fActivate`  
 В разделе `fActivate` в [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацию в CDHtmlDialog [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onframewindowactivate"></a>CDHtmlDialog::OnFrameWindowActivate  
 Вызывается платформой, если окно активируется или деактивируется.  
  
```  
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>Параметры  
 `fActivate`  
 В разделе `fActivate` в [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="oninitdialog"></a>CDHtmlDialog::OnInitDialog  
 Вызывается в ответ на **WM_INITDIALOG** сообщение.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает **TRUE**.  
  
### <a name="remarks"></a>Примечания  
 Это сообщение отправляется в окно во время **создать**, `CreateIndirect`, или `DoModal` вызовы, которые происходят непосредственно перед откроется диалоговое окно.  
  
 Переопределите эту функцию-член, если необходимо выполнять специальную обработку при инициализации диалоговое окно. Переопределенные версии сначала вызвать базовый класс `OnInitDialog` , но не принимать во внимание возвращаемого значения. Обычно будет возвращать **TRUE** из переопределяемого члена функции.  
  
 Вызовы Windows `OnInitDialog` функции через стандартные глобальные диалогового процедуру, общие для всех диалоговых окнах библиотеки классов Microsoft Foundation, а не через карту сообщения так не требуется запись сопоставления сообщения для этой функции-члена.  
  
##  <a name="onnavigatecomplete"></a>CDHtmlDialog::OnNavigateComplete  
 Вызывается платформой после завершения перехода на указанный URL-адрес.  
  
```  
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>Параметры  
 `pDisp`  
 Указатель на объект `IDispatch` .  
  
 `szUrl`  
 Указатель на строку, содержащую URL-адрес, по которому был осуществлен переход.  
  
##  <a name="resizeborder"></a>CDHtmlDialog::ResizeBorder  
 Предупреждения, если нужно изменить размер пространства границы объекта.  
  
```  
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,  
    IOleInPlaceUIWindow* pUIWindow,  
    BOOL fRameWindow);
```  
  
### <a name="parameters"></a>Параметры  
 `prcBorder`  
 В разделе `prcBorder` в [IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pUIWindow`  
 В разделе `pUIWindow` в **IDocHostUIHandler::ResizeBorder** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `fFrameWindow`  
 В разделе *fFrameWindow* в **IDocHostUIHandler::ResizeBorder** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
##  <a name="setcontrolproperty"></a>CDHtmlDialog::SetControlProperty  
 Задает для свойства элемента управления ActiveX на новое значение.  
  
```  
void SetControlProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    LPCTSTR szElementId,  
    LPCTSTR szPropName,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>Параметры  
 `szElementId`  
 HTML-идентификатор элемента управления ActiveX.  
  
 `dispid`  
 Идентификатор диспетчеризации задаваемое свойство.  
  
 *pVar*  
 Указатель на **VARIANT** содержащий новое значение свойства.  
  
 `pdispControl`  
 Указатель на элемент управления ActiveX `IDispatch` интерфейса.  
  
 `szPropName`  
 Строка, содержащая имя свойства.  
  
##  <a name="setelementhtml"></a>CDHtmlDialog::SetElementHtml  
 Наборы **innerHTML** свойство элемента HTML.  
  
```  
void SetElementHtml(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementHtml(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>Параметры  
 `szElementId`  
 Идентификатор HTML-элемента.  
  
 `bstrText`  
 Новое значение **innerHTML** свойство.  
  
 `punkElem`  
 **IUnknown** указатель элемента HTML.  
  
##  <a name="setelementproperty"></a>CDHtmlDialog::SetElementProperty  
 Задает свойство элемента HTML.  
  
```  
void SetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>Параметры  
 `szElementId`  
 Идентификатор HTML-элемента.  
  
 `dispid`  
 Идентификатор диспетчеризации задаваемое свойство.  
  
 *pVar*  
 Новое значение свойства.  
  
##  <a name="setelementtext"></a>CDHtmlDialog::SetElementText  
 Наборы **innerText** свойство элемента HTML.  
  
```  
void SetElementText(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementText(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>Параметры  
 `szElementId`  
 Идентификатор HTML-элемента.  
  
 `bstrText`  
 Новое значение **innerText** свойство.  
  
 `punkElem`  
 **IUnknown** указатель элемента HTML.  
  
##  <a name="setexternaldispatch"></a>CDHtmlDialog::SetExternalDispatch  
 Задает узел `IDispatch` интерфейса.  
  
```  
void SetExternalDispatch(IDispatch* pdispExternal);
```  
  
### <a name="parameters"></a>Параметры  
 *pdispExternal*  
 Новый `IDispatch` интерфейса.  
  
##  <a name="sethostflags"></a>CDHtmlDialog::SetHostFlags  
 Задает флаги пользовательского интерфейса узла.  
  
```  
void SetHostFlags(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Возможные значения см. в разделе [DOCHOSTUIFLAG](https://msdn.microsoft.com/library/aa753277.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="showcontextmenu"></a>CDHtmlDialog::ShowContextMenu  
 Вызывается сразу перед отображением контекстного меню.  
  
```  
STDMETHOD(ShowContextMenu)(
    DWORD dwID,  
    POINT* ppt,  
    IUnknown* pcmdtReserved,  
    IDispatch* pdispReserved);
```  
  
### <a name="parameters"></a>Параметры  
 `dwID`  
 В разделе `dwID` в [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppt`  
 В разделе `ppt` в **IDocHostUIHandler::ShowContextMenu** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pcmdtReserved`  
 В разделе `pcmdtReserved` в **IDocHostUIHandler::ShowContextMenu** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pdispReserved`  
 В разделе `pdispReserved` в **IDocHostUIHandler::ShowContextMenu** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **S_FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="showui"></a>CDHtmlDialog::ShowUI  
 Показан пользовательский Интерфейс узла.  
  
```  
STDMETHOD(ShowUI)(
    DWORD dwID,  
    IOleInPlaceActiveObject* pActiveObject,  
    IOleCommandTarget* pCommandTarget,  
    IOleInPlaceFrame* pFrame,  
    IOleInPlaceUIWindow* pDoc);
```  
  
### <a name="parameters"></a>Параметры  
 `dwID`  
 В разделе `dwID` в [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pActiveObject`  
 В разделе *d pActiveObject* в **IDocHostUIHandler::ShowUI** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pCommandTarget`  
 В разделе `pCommandTarget` в **IDocHostUIHandler::ShowUI** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pFrame`  
 В разделе `pFrame` в **IDocHostUIHandler::ShowUI** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pDoc`  
 В разделе `pDoc` в **IDocHostUIHandler::ShowUI** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **S_FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="translateaccelerator"></a>CDHtmlDialog::TranslateAccelerator  
 Вызывается для обработки сообщений сочетаний клавиш меню.  
  
```  
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMsg`  
 В разделе `lpMsg` в [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pguidCmdGroup`  
 В разделе `pguidCmdGroup` в **IDocHostUIHandler::TranslateAccelerator** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nCmdID`  
 В разделе `nCmdID` в **IDocHostUIHandler::TranslateAccelerator** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **S_FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="translateurl"></a>CDHtmlDialog::TranslateUrl  
 Вызывается, чтобы изменить URL-адрес для загрузки.  
  
```  
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>Параметры  
 `dwTranslate`  
 В разделе `dwTranslate` в [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pchURLIn`  
 В разделе `pchURLIn` в **IDocHostUIHandler::TranslateUrl** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ppchURLOut`  
 В разделе `ppchURLOut` в **IDocHostUIHandler::TranslateUrl** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **S_FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="updateui"></a>CDHtmlDialog::UpdateUI  
 Вызывается для уведомления узла об изменении состояния команды.  
  
```  
STDMETHOD(UpdateUI)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является реализацией CDHtmlDialog [IDocHostUIHandler::UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Сложный пример MFC](../../visual-cpp-samples.md)   
 [DDX_DHtml вспомогательных макросов](#ddx_dhtml_helper_macros)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



