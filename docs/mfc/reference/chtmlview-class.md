---
title: "Класс CHtmlView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlView
- AFXHTML/CHtmlView
- AFXHTML/CHtmlView::Create
- AFXHTML/CHtmlView::CreateControlSite
- AFXHTML/CHtmlView::ExecFormsCommand
- AFXHTML/CHtmlView::ExecWB
- AFXHTML/CHtmlView::GetAddressBar
- AFXHTML/CHtmlView::GetApplication
- AFXHTML/CHtmlView::GetBusy
- AFXHTML/CHtmlView::GetContainer
- AFXHTML/CHtmlView::GetFullName
- AFXHTML/CHtmlView::GetFullScreen
- AFXHTML/CHtmlView::GetHeight
- AFXHTML/CHtmlView::GetHtmlDocument
- AFXHTML/CHtmlView::GetLeft
- AFXHTML/CHtmlView::GetLocationName
- AFXHTML/CHtmlView::GetLocationURL
- AFXHTML/CHtmlView::GetMenuBar
- AFXHTML/CHtmlView::GetOffline
- AFXHTML/CHtmlView::GetParentBrowser
- AFXHTML/CHtmlView::GetProperty
- AFXHTML/CHtmlView::GetReadyState
- AFXHTML/CHtmlView::GetRegisterAsBrowser
- AFXHTML/CHtmlView::GetRegisterAsDropTarget
- AFXHTML/CHtmlView::GetSilent
- AFXHTML/CHtmlView::GetSource
- AFXHTML/CHtmlView::GetStatusBar
- AFXHTML/CHtmlView::GetTheaterMode
- AFXHTML/CHtmlView::GetToolBar
- AFXHTML/CHtmlView::GetTop
- AFXHTML/CHtmlView::GetTopLevelContainer
- AFXHTML/CHtmlView::GetType
- AFXHTML/CHtmlView::GetVisible
- AFXHTML/CHtmlView::GetWidth
- AFXHTML/CHtmlView::GoBack
- AFXHTML/CHtmlView::GoForward
- AFXHTML/CHtmlView::GoHome
- AFXHTML/CHtmlView::GoSearch
- AFXHTML/CHtmlView::LoadFromResource
- AFXHTML/CHtmlView::Navigate
- AFXHTML/CHtmlView::Navigate2
- AFXHTML/CHtmlView::OnBeforeNavigate2
- AFXHTML/CHtmlView::OnCommandStateChange
- AFXHTML/CHtmlView::OnDocumentComplete
- AFXHTML/CHtmlView::OnDocWindowActivate
- AFXHTML/CHtmlView::OnDownloadBegin
- AFXHTML/CHtmlView::OnDownloadComplete
- AFXHTML/CHtmlView::OnEnableModeless
- AFXHTML/CHtmlView::OnFilterDataObject
- AFXHTML/CHtmlView::OnFrameWindowActivate
- AFXHTML/CHtmlView::OnFullScreen
- AFXHTML/CHtmlView::OnGetDropTarget
- AFXHTML/CHtmlView::OnGetExternal
- AFXHTML/CHtmlView::OnGetHostInfo
- AFXHTML/CHtmlView::OnGetOptionKeyPath
- AFXHTML/CHtmlView::OnHideUI
- AFXHTML/CHtmlView::OnMenuBar
- AFXHTML/CHtmlView::OnNavigateComplete2
- AFXHTML/CHtmlView::OnNavigateError
- AFXHTML/CHtmlView::OnNewWindow2
- AFXHTML/CHtmlView::OnProgressChange
- AFXHTML/CHtmlView::OnPropertyChange
- AFXHTML/CHtmlView::OnQuit
- AFXHTML/CHtmlView::OnResizeBorder
- AFXHTML/CHtmlView::OnShowContextMenu
- AFXHTML/CHtmlView::OnShowUI
- AFXHTML/CHtmlView::OnStatusBar
- AFXHTML/CHtmlView::OnStatusTextChange
- AFXHTML/CHtmlView::OnTheaterMode
- AFXHTML/CHtmlView::OnTitleChange
- AFXHTML/CHtmlView::OnToolBar
- AFXHTML/CHtmlView::OnTranslateAccelerator
- AFXHTML/CHtmlView::OnTranslateUrl
- AFXHTML/CHtmlView::OnUpdateUI
- AFXHTML/CHtmlView::OnVisible
- AFXHTML/CHtmlView::PutProperty
- AFXHTML/CHtmlView::QueryFormsCommand
- AFXHTML/CHtmlView::QueryStatusWB
- AFXHTML/CHtmlView::Refresh
- AFXHTML/CHtmlView::Refresh2
- AFXHTML/CHtmlView::SetAddressBar
- AFXHTML/CHtmlView::SetFullScreen
- AFXHTML/CHtmlView::SetHeight
- AFXHTML/CHtmlView::SetLeft
- AFXHTML/CHtmlView::SetMenuBar
- AFXHTML/CHtmlView::SetOffline
- AFXHTML/CHtmlView::SetRegisterAsBrowser
- AFXHTML/CHtmlView::SetRegisterAsDropTarget
- AFXHTML/CHtmlView::SetSilent
- AFXHTML/CHtmlView::SetStatusBar
- AFXHTML/CHtmlView::SetTheaterMode
- AFXHTML/CHtmlView::SetToolBar
- AFXHTML/CHtmlView::SetTop
- AFXHTML/CHtmlView::SetVisible
- AFXHTML/CHtmlView::SetWidth
- AFXHTML/CHtmlView::Stop
dev_langs:
- C++
helpviewer_keywords:
- browsers, MFC support for
- CHtmlView class
- WebBrowser control
- WebBrowser control, MFC support
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d9d96ab02a0c49a2ece12c933f5d550a46204a39
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="chtmlview-class"></a>Класс CHtmlView
Предоставляет функциональные возможности элемента управления WebBrowser в контексте архитектуры документов или представлений MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHtmlView : public CFormView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHtmlView::Create](#create)|Создает элемент управления WebBrowser.|  
|[CHtmlView::CreateControlSite](#createcontrolsite)|Переопределяемый класс, используемый для создания экземпляра сайта элемента управления для размещения элемента управления на форме.|  
|[CHtmlView::ExecFormsCommand](#execformscommand)|Выполняет указанную команду с помощью метода `IOleCommandTarget::Exec` .|  
|[CHtmlView::ExecWB](#execwb)|Выполняет команду.|  
|[CHtmlView::GetAddressBar](#getaddressbar)|Определяет, видима ли адресная строка объекта Internet Explorer. (Элемент управления WebBrowser игнорирует; только Internet Explorer.)|  
|[CHtmlView::GetApplication](#getapplication)|Возвращает объект приложения, который представляет приложение, содержащее текущий экземпляр приложения Internet Explorer.|  
|[CHtmlView::GetBusy](#getbusy)|Возвращает значение, указывающее на то, выполняется ли все еще скачивание или другой процесс.|  
|[CHtmlView::GetContainer](#getcontainer)|Возвращает контейнер элемента управления WebBrowser.|  
|[CHtmlView::GetFullName](#getfullname)|Извлекает полное имя, включая путь ресурса, отображаемого в веб-браузере. (Элемент управления WebBrowser игнорирует; только Internet Explorer.)|  
|[CHtmlView::GetFullScreen](#getfullscreen)|Указывает, работает ли элемент управления WebBrowser в полноэкранном режиме или в обычном режиме окна.|  
|[CHtmlView::GetHeight](#getheight)|Получает высоту главного окна Internet Explorer.|  
|[CHtmlView::GetHtmlDocument](#gethtmldocument)|Получает активный документ HTML.|  
|[CHtmlView::GetLeft](#getleft)|Получает координату левого края главного окна Internet Explorer.|  
|[CHtmlView::GetLocationName](#getlocationname)|Получает имя ресурса, который в данный момент отображается элементом управления WebBrowser.|  
|[CHtmlView::GetLocationURL](#getlocationurl)|Получает URL-адрес ресурса, который в данный момент отображается элементом управления WebBrowser.|  
|[CHtmlView::GetMenuBar](#getmenubar)|Получает значение, указывающее, является ли строка меню видимой.|  
|[CHtmlView::GetOffline](#getoffline)|Получает значение, указывающее, находится ли элемент управления в автономном режиме.|  
|[CHtmlView::GetParentBrowser](#getparentbrowser)|Получает указатель на интерфейс `IDispatch` . Дополнительные сведения см. в разделе [реализации интерфейса IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).|  
|[CHtmlView::GetProperty](#getproperty)|Возвращает текущее значение свойства, связанного с данным объектом.|  
|[CHtmlView::GetReadyState](#getreadystate)|Получает состояние готовности объекта веб-браузера.|  
|[CHtmlView::GetRegisterAsBrowser](#getregisterasbrowser)|Указывает, зарегистрирован ли элемент управления WebBrowser в качестве браузера верхнего уровня для разрешения целевых имен.|  
|[CHtmlView::GetRegisterAsDropTarget](#getregisterasdroptarget)|Указывает, зарегистрирован ли элемент управления WebBrowser в качестве целевого объекта перетаскивания для навигации.|  
|[CHtmlView::GetSilent](#getsilent)|Указывает, могут ли отображаться какие-либо диалоговые окна.|  
|[CHtmlView::GetSource](#getsource)|Исходный код HTML веб-страницы.|  
|[CHtmlView::GetStatusBar](#getstatusbar)|Указывает, является ли строка состояния Internet Explorer видимой. (Элемент управления WebBrowser игнорирует; только Internet Explorer.)|  
|[CHtmlView::GetTheaterMode](#gettheatermode)|Указывает, находится ли элемент управления WebBrowser в режиме театра.|  
|[CHtmlView::GetToolBar](#gettoolbar)|Получает значение, указывающее, является ли панель инструментов видимой.|  
|[CHtmlView::GetTop](#gettop)|Получает координату верхнего края главного окна Internet Explorer.|  
|[CHtmlView::GetTopLevelContainer](#gettoplevelcontainer)|Получает значение, указывающее, является ли текущий объект контейнером верхнего уровня для элемента управления WebBrowser.|  
|[CHtmlView::GetType](#gettype)|Получает имя типа объекта документа.|  
|[CHtmlView::GetVisible](#getvisible)|Получает значение, указывающее, является ли объект видимым или скрытым.|  
|[CHtmlView::GetWidth](#getwidth)|Получает ширину главного окна Internet Explorer.|  
|[CHtmlView::GoBack](#goback)|Переходит к предыдущему элементу в списке журнала.|  
|[CHtmlView::GoForward](#goforward)|Переходит к следующему элементу в списке журнала.|  
|[CHtmlView::GoHome](#gohome)|Переходит к текущей домашней или начальной странице.|  
|[CHtmlView::GoSearch](#gosearch)|Переходит к текущей странице поиска.|  
|[CHtmlView::LoadFromResource](#loadfromresource)|Загружает ресурс в элементе управления WebBrowser.|  
|[CHtmlView::Navigate](#navigate)|Переходит к ресурсу, определяемому URL-адресом.|  
|[CHtmlView::Navigate2](#navigate2)|Переходит к ресурсу, определяемому URL-адресом, или файлу, определяемому полным путем.|  
|[CHtmlView::OnBeforeNavigate2](#onbeforenavigate2)|Вызывается до того, как начинается переход в данном элементе управления WebBrowser (в окне или элементе набора фреймов).|  
|[CHtmlView::OnCommandStateChange](#oncommandstatechange)|Вызывается для уведомления приложения о том, что состояние выполнения команды веб-браузера изменилось.|  
|[CHtmlView::OnDocumentComplete](#ondocumentcomplete)|Вызывается для уведомления приложения о том, что документ достиг состояния `READYSTATE_COMPLETE` .|  
|[CHtmlView::OnDocWindowActivate](#ondocwindowactivate)|Вызывается из Internet Explorer или MSHTML реализацию [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281), который информирует активный объект в месте контейнера окна документа, активируется или деактивируется.|  
|[CHtmlView::OnDownloadBegin](#ondownloadbegin)|Вызывается для уведомления приложения о том, что начинается операция перехода.|  
|[CHtmlView::OnDownloadComplete](#ondownloadcomplete)|Вызывается, когда операция перехода закончилась, была остановлена или завершилась с ошибкой.|  
|[CHtmlView::OnEnableModeless](#onenablemodeless)|Вызывается для включения или отключения безрежимных диалоговых окон, когда контейнер создает или уничтожает модальное диалоговое окно.|  
|[CHtmlView::OnFilterDataObject](#onfilterdataobject)|Вызывается Internet Explorer или MSHTML в основном приложении, чтобы разрешить ему заменить объект данных Internet Explorer или MSHTML.|  
|[CHtmlView::OnFrameWindowActivate](#onframewindowactivate)|Вызывается из [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) уведомлять объект контейнера верхнего уровня окно активируется или деактивируется.|  
|[CHtmlView::OnFullScreen](#onfullscreen)|Вызывается после изменения свойства FullScreen.|  
|[CHtmlView::OnGetDropTarget](#ongetdroptarget)|Вызывается Internet Explorer или MSHTML, когда он используется в качестве объекта-приемника позволяет ведущему приложению указать альтернативный [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CHtmlView::OnGetExternal](#ongetexternal)|Вызывается Internet Explorer или MSHTML для получения интерфейса `IDispatch` основного приложения.|  
|[CHtmlView::OnGetHostInfo](#ongethostinfo)|Возвращает возможности пользовательского интерфейса основного приложения Internet Explorer или MSHTML.|  
|[CHtmlView::OnGetOptionKeyPath](#ongetoptionkeypath)|Возвращает раздел реестра, в котором хранятся пользовательские настройки Internet Explorer или MSHTML.|  
|[CHtmlView::OnHideUI](#onhideui)|Вызывается при удалении меню и панелей инструментов Internet Explorer или MSHTML.|  
|[CHtmlView::OnMenuBar](#onmenubar)|Вызывается после изменения свойства MenuBar.|  
|[CHtmlView::OnNavigateComplete2](#onnavigatecomplete2)|Вызывается после того, как выполнен переход по гиперссылке (в окне или элементе набора фреймов).|  
|[CHtmlView::OnNavigateError](#onnavigateerror)|Вызывается платформой, если переход по гиперссылке завершается ошибкой.|  
|[CHtmlView::OnNewWindow2](#onnewwindow2)|Вызывается, если для отображения ресурса должно быть создано окно.|  
|[CHtmlView::OnProgressChange](#onprogresschange)|Вызывается для уведомления приложения о том, что ход операции скачивания был обновлен.|  
|[CHtmlView::OnPropertyChange](#onpropertychange)|Вызывается для оповещения приложения, [PutProperty](#putproperty) метод изменилось значение свойства.|  
|[CHtmlView::OnQuit](#onquit)|Вызывается для уведомления приложения о том, что приложение Internet Explorer готово закрыться. (Применяется только в Internet Explorer.)|  
|[CHtmlView::OnResizeBorder](#onresizeborder)|Вызывается из Internet Explorer или MSHTML реализацию [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), предупреждающее, если нужно изменить размер пространства границы объекта.|  
|[CHtmlView::OnShowContextMenu](#onshowcontextmenu)|Вызывается из Internet Explorer или MSHTML перед отображением контекстного меню.|  
|[CHtmlView::OnShowUI](#onshowui)|Вызывается перед отображением меню и панелей инструментов в Internet Explorer или MSHTML.|  
|[CHtmlView::OnStatusBar](#onstatusbar)|Вызывается после изменения свойства StatusBar.|  
|[CHtmlView::OnStatusTextChange](#onstatustextchange)|Вызывается для уведомления приложения о том, что текст строки состояния, связанной с элементом управления WebBrowser, изменился.|  
|[CHtmlView::OnTheaterMode](#ontheatermode)|Вызывается после изменения свойства TheaterMode.|  
|[CHtmlView::OnTitleChange](#ontitlechange)|Вызывается для уведомления приложения о том, что заголовок документа в элементе управления WebBrowser стал доступен или изменился.|  
|[CHtmlView::OnToolBar](#ontoolbar)|Вызывается после изменения свойства ToolBar.|  
|[CHtmlView::OnTranslateAccelerator](#ontranslateaccelerator)|Вызывается Internet Explorer или MSHTML при [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) или [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) вызывается для обработки сообщений сочетаний клавиш меню из контейнера очереди сообщений.|  
|[CHtmlView::OnTranslateUrl](#ontranslateurl)|Вызывается Internet Explorer или MSHTML, чтобы разрешить основному приложению изменять URL-адрес, который нужно загрузить.|  
|[CHtmlView::OnUpdateUI](#onupdateui)|Уведомляет основное приложение об изменении состояния команды.|  
|[CHtmlView::OnVisible](#onvisible)|Вызывается, когда окно элемента управления WebBrowser должно быть показано или скрыто.|  
|[CHtmlView::PutProperty](#putproperty)|Задает значение свойства, связанного с данным объектом.|  
|[CHtmlView::QueryFormsCommand](#queryformscommand)|Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.|  
|[CHtmlView::QueryStatusWB](#querystatuswb)|Запрашивает состояние команды, обрабатываемой элементом управления WebBrowser.|  
|[CHtmlView::Refresh](#refresh)|Перезагружает текущий файл.|  
|[CHtmlView::Refresh2](#refresh2)|Перезагружает текущий файл и при необходимости блокирует отправку заголовка `pragma:nocache` .|  
|[CHtmlView::SetAddressBar](#setaddressbar)|Отображает или скрывает адресную строку объекта Internet Explorer. (Элемент управления WebBrowser игнорирует; только Internet Explorer.)|  
|[CHtmlView::SetFullScreen](#setfullscreen)|Задает значение, которое указывает, работает ли элемент управления в полноэкранном режиме или в обычном режиме окна. (Элемент управления WebBrowser игнорирует; только Internet Explorer.)|  
|[CHtmlView::SetHeight](#setheight)|Задает высоту главного окна Internet Explorer.|  
|[CHtmlView::SetLeft](#setleft)|Задает положение главного окна Internet Explorer по горизонтали.|  
|[CHtmlView::SetMenuBar](#setmenubar)|Задает значение, указывающее, является ли строка меню элемента управления видимой. (Элемент управления WebBrowser игнорирует; только Internet Explorer.)|  
|[CHtmlView::SetOffline](#setoffline)|Задает значение, указывающее, находится ли элемент управления в автономном режиме.|  
|[CHtmlView::SetRegisterAsBrowser](#setregisterasbrowser)|Задает значение, которое указывает, зарегистрирован ли элемент управления WebBrowser в качестве браузера верхнего уровня для разрешения целевых имен.|  
|[CHtmlView::SetRegisterAsDropTarget](#setregisterasdroptarget)|Задает значение, которое указывает, зарегистрирован ли элемент управления WebBrowser в качестве целевого объекта перетаскивания для навигации.|  
|[CHtmlView::SetSilent](#setsilent)|Задает значение, указывающее, будет ли элемент управления выводить диалоговые окна.|  
|[CHtmlView::SetStatusBar](#setstatusbar)|Задает значение, которое указывает, является ли строка состояния Internet Explorer видимой. (Элемент управления WebBrowser игнорирует; только Internet Explorer.)|  
|[CHtmlView::SetTheaterMode](#settheatermode)|Задает значение, которое указывает, находится ли элемент управления WebBrowser в режиме театра.|  
|[CHtmlView::SetToolBar](#settoolbar)|Задает значение, указывающее, является ли панель инструментов элемента управления видимой. (Элемент управления WebBrowser игнорирует; только Internet Explorer.)|  
|[CHtmlView::SetTop](#settop)|Задает положение главного окна Internet Explorer по вертикали.|  
|[CHtmlView::SetVisible](#setvisible)|Задает значение, указывающее, является ли объект видимым или скрытым.|  
|[CHtmlView::SetWidth](#setwidth)|Задает ширину главного окна Internet Explorer.|  
|[CHtmlView::Stop](#stop)|Останавливает открытие файла.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления WebBrowser — это окно, в котором пользователь может просматривать сайты в Интернете, а также папки в локальной файловой системе и в сети. Элемент управления WebBrowser поддерживает гиперссылки и переход по URL-адресам. Кроме того, в нем ведется список журнала.  
  
## <a name="using-the-chtmlview-class-in-an-mfc-application"></a>Использование класса CHtmlView в приложении MFC  
 В стандартном приложении платформы MFC (на основе SDI или MDI) объект представления обычно является производным от специального набора классов. Эти классы, производные от `CView`, предоставляют специальные возможности, которые отсутствуют у класса `CView`.  
  
 Если класс представления приложения основан на `CHtmlView` , представление обеспечивается элементом управления WebBrowser. Это фактически делает приложение веб-браузером. Предпочтительным способом создания приложений в стиле веб-браузера является использование мастера приложений MFC и указание `CHtmlView` в качестве класса представления. Дополнительные сведения о реализации и использовании управления WebBrowser в приложениях MFC см. в разделе [Создание веб-приложения обозревателя](../../mfc/reference/creating-a-web-browser-style-mfc-application.md).  
  
> [!NOTE]
>  Элемент ActiveX WebBrowser (и, следовательно, `CHtmlView`) доступен только для программ, выполняемых под управлением ОС Windows NT версии 4.0 или более поздней, в которой установлен Internet Explorer 4.0 или более поздней версии.  
  
 `CHtmlView`предназначен для приложений, доступ к Интернету (или HTML-документы). Перечисленные ниже функции-члены `CHtmlView` относятся только к приложению Internet Explorer. Они будут успешно выполняться в элементе управления WebBrowser, но не будут иметь никакого видимого эффекта.  
  
- [GetAddressBar](#getaddressbar)  
  
- [GetFullName](#getfullname)  
  
- [GetStatusBar](#getstatusbar)  
  
- [SetAddressBar](#setaddressbar)  
  
- [SetFullScreen](#setfullscreen)  
  
- [SetMenuBar](#setmenubar)  
  
- [SetStatusBar](#setstatusbar)  
  
- [SetToolBar](#settoolbar)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxhtml.h  
  
##  <a name="create"></a>CHtmlView::Create  
 Вызовите эту функцию-член для создания элемента управления WebBrowser или контейнер для Internet Explorer исполняемого файла.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszClassName`  
 Указывает строку символом null, что имена классов Windows. Имя класса может быть любое имя, зарегистрированное в [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) глобальной функции или **RegisterClass** функции Windows. Если **NULL**, использует предопределенные по умолчанию [CFrameWnd](../../mfc/reference/cframewnd-class.md) атрибуты.  
  
 `lpszWindowName`  
 Указывает символ нулем строка, представляющая имя окна.  
  
 `dwStyle`  
 Задает атрибуты стилей окна. По умолчанию **WS_VISIBLE** и **WS_CHILD** заданы стили Windows.  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, определяя размер и положение окна. `rectDefault` Значение позволяет Windows указать размер и положение нового окна.  
  
 `pParentWnd`  
 Указатель на родительское окно элемента управления.  
  
 `nID`  
 Идентификатор представления. По умолчанию значение **AFX_IDW_PANE_FIRST**.  
  
 `pContext`  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md). **Значение NULL,** по умолчанию.  
  
##  <a name="createcontrolsite"></a>CHtmlView::CreateControlSite  
 Переопределяемый класс, используемый для создания экземпляра сайта элемента управления для размещения элемента управления на форме.  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT nID,  
    REFCLSID clsid);
```  
  
### <a name="parameters"></a>Параметры  
 `pContainer`  
 Указатель на [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) объекта, содержащего элемент управления.  
  
 `ppSite`  
 Указатель на указатель на [COleControlSite](../../mfc/reference/colecontrolsite-class.md) объекта, предоставляя сайта для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления для размещения.  
  
 `clsid`  
 Идентификатор CLSID для размещения элемента управления  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить эту функцию-член для возврата экземпляра класса сайта собственного элемента управления.  
  
##  <a name="execformscommand"></a>CHtmlView::ExecFormsCommand  
 Выполняет указанную команду с помощью метода `IOleCommandTarget::Exec` .  
  
```  
HRESULT ExecFormsCommand(
    DWORD dwCommandID,  
    VARIANT* pVarIn,  
    VARIANT* pVarOut);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCommandID`  
 Команда для выполнения. Эта команда должна принадлежать **CMDSETID3_Forms3** группы.  
  
 *pVarIn*  
 Указатель на **VARIANT** структуру, содержащую входные аргументы. Может быть **NULL**.  
  
 *pVarOut*  
 Указатель на **VARIANT** структуру для получения выходных данных команды. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` . Полный список возможных значений см. в разделе [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 **ExecFormsCommand** реализует поведение [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300) метод.  
  
##  <a name="execwb"></a>CHtmlView::ExecWB  
 Вызовите эту функцию-член для выполнения команды WebBrowser или Internet Explorer.  
  
```  
void ExecWB(
    OLECMDID cmdID,  
    OLECMDEXECOPT cmdexecopt,  
    VARIANT* pvaIn,  
    VARIANT* pvaOut);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Команда для выполнения.  
  
 *cmdexecopt*  
 Набор параметров для выполнения команды.  
  
 `pvaIn`  
 Значение типа variant, определяет входные аргументы команды.  
  
 *pvaOut*  
 Вариант, используемый для указания выходные аргументы команды.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IWebBrowser2::ExecWB](https://msdn.microsoft.com/library/aa752117.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getaddressbar"></a>CHtmlView::GetAddressBar  
 Вызовите эту функцию-член для получения адресной строки обозревателя Internet Explorer.  
  
```  
BOOL GetAddressBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в адресной строке является видимым. в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется к Internet Explorer. При использовании этот вызов с помощью элемента управления WebBrowser, ошибка не возвращается, но он будет игнорировать этот вызов.  
  
##  <a name="getapplication"></a>CHtmlView::GetApplication  
 Вызовите эту функцию-член для получения объекта автоматизации, поддерживаемых приложением, который содержит элемент управления WebBrowser.  
  
```  
LPDISPATCH GetApplication() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `IDispatch` интерфейс объекта активного документа. Дополнительные сведения см. в разделе [реализации интерфейса IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getbusy"></a>CHtmlView::GetBusy  
 Вызовите эту функцию-член для определения, участвует ли элемент управления WebBrowser в навигации или операции загрузки.  
  
```  
BOOL GetBusy() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если веб-обозреватель занята; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getcontainer"></a>CHtmlView::GetContainer  
 Вызовите эту функцию-член для получения объекта, результатом которого является контейнер веб-браузера.  
  
```  
LPDISPATCH GetContainer() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `IDispatch` интерфейс объекта активного документа.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getfullname"></a>CHtmlView::GetFullName  
 Вызов этой функции-члена для получения полного пути файла, который в данный момент отображает Internet Explorer.  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий путь и имя файла, выделенного в настоящий момент. Если существует не путь и имя файла, `GetFullName` возвращает пустую коллекцию `CString`.  
  
### <a name="remarks"></a>Примечания  
 Применяется к Internet Explorer. При использовании этот вызов с помощью элемента управления WebBrowser, ошибка не возвращается, но он будет игнорировать этот вызов.  
  
##  <a name="getfullscreen"></a>CHtmlView::GetFullScreen  
 Вызовите эту функцию-член, чтобы определить, работает ли элемент управления WebBrowser в полноэкранном режиме или в режиме обычного окна.  
  
```  
BOOL GetFullScreen() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если браузер работает в полноэкранном режиме. в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 В полноэкранном режиме развернуто главного окна Internet Explorer и строки состояния, панели инструментов, меню и заголовок окна скрыты.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getheight"></a>CHtmlView::GetHeight  
 Вызовите эту функцию-член для получения высоту в пикселях фрейм окна элемента управления WebBrowser.  
  
```  
long GetHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота элемента управления фрейм окна, в пикселях.  
  
##  <a name="gethtmldocument"></a>CHtmlView::GetHtmlDocument  
 Вызовите эту функцию-член для получения HTML-документ для активного документа.  
  
```  
LPDISPATCH GetHtmlDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `IDispatch` интерфейс объекта активного документа.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getleft"></a>CHtmlView::GetLeft  
 Вызовите эту функцию-член для получения расстояние между внутренним левым краем элемента управления WebBrowser и левым краем его контейнера.  
  
```  
long GetLeft() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Левый край расстояние в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getlocationname"></a>CHtmlView::GetLocationName  
 Вызовите эту функцию-член для получения имени ресурса, отображаемый в браузер.  
  
```  
CString GetLocationName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий имя ресурса, отображаемый в текущий момент в браузер.  
  
### <a name="remarks"></a>Примечания  
 Если ресурсом является HTML-страницы в Интернете, имя представляет собой название этой страницы. Если ресурс является папки или файла в сети или локального компьютера, имя является UNC-путь или полный путь к папке или файлу.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getlocationurl"></a>CHtmlView::GetLocationURL  
 Вызовите эту функцию-член для получения URL-адрес ресурса, который в данный момент отображает элемент управления WebBrowser.  
  
```  
CString GetLocationURL() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий URL-адрес ресурса, отображаемый в текущий момент в браузер.  
  
### <a name="remarks"></a>Примечания  
 Если ресурс является папки или файла в сети или локального компьютера, имя является UNC-путь или полный путь к папке или файлу.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getmenubar"></a>CHtmlView::GetMenuBar  
 Вызовите эту функцию-член для определения того, отображается ли меню.  
  
```  
BOOL GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если меню является видимым. в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getoffline"></a>CHtmlView::GetOffline  
 Вызовите эту функцию-член для определения, работает ли веб-браузере вне сети.  
  
```  
BOOL GetOffline() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если веб-браузера в автономном режиме; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getparentbrowser"></a>CHtmlView::GetParentBrowser  
 Вызовите эту функцию-член, чтобы получить указатель на родительский объект элемента управления WebBrowser.  
  
```  
LPDISPATCH GetParentBrowser() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `IDispatch` интерфейс объекта, который является родительским для элемента управления WebBrowser.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getproperty"></a>CHtmlView::GetProperty  
 Вызовите эту функцию-член для получения значения свойства, которые в данный момент связанный с элементом управления.  
  
```  
BOOL GetProperty(
    LPCTSTR lpszProperty,  
    CString& strValue);  
  
COleVariant GetProperty(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProperty`  
 Указатель на строку, содержащую извлекаемого свойства.  
  
 `strValue`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, который получает текущее значение свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой версии ненулевое значение, если успешно завершена; в противном случае — нуль. Во второй версии [COleVariant](../../mfc/reference/colevariant-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getreadystate"></a>CHtmlView::GetReadyState  
 Вызовите эту функцию-член для получения состояния готовности объекта WebBrowser.  
  
```  
READYSTATE GetReadyState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [READYSTATE](https://msdn.microsoft.com/library/aa768362.aspx) значения, как описано в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getregisterasbrowser"></a>CHtmlView::GetRegisterAsBrowser  
 Вызовите эту функцию-член для определения того, зарегистрирован ли объект WebBrowser в качестве обозревателя верхнего уровня для разрешения имен целевой.  
  
```  
BOOL GetRegisterAsBrowser() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если браузер в качестве обозревателя верхнего уровня; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getregisterasdroptarget"></a>CHtmlView::GetRegisterAsDropTarget  
 Вызовите эту функцию-член, чтобы определить, зарегистрирован ли элемент управления WebBrowser в качестве назначения для навигации.  
  
```  
BOOL GetRegisterAsDropTarget() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если браузер регистрируется как цель перетаскивания; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getsilent"></a>CHtmlView::GetSilent  
 Вызовите эту функцию-член для определения, может ли отображаться в элементе управления WebBrowser все диалоговые окна.  
  
```  
BOOL GetSilent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если не удается отобразить диалоговые окна из элемента управления WebBrowser; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getsource"></a>CHtmlView::GetSource  
 Вызовите эту функцию-член для получения исходного кода HTML, веб-страницы.  
  
```  
BOOL GetSource(CString& strRef);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="parameters"></a>Параметры  
 `refString`  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , будет содержать исходный код.  
  
### <a name="remarks"></a>Примечания  
 Эта функция эквивалентна команде «Просмотр исходного кода» в Internet Explorer, за исключением того, что исходный код возвращается в `CString`.  
  
##  <a name="getstatusbar"></a>CHtmlView::GetStatusBar  
 Вызовите эту функцию-член для определения того, отображается ли элемент управления WebBrowser в строке состояния.  
  
```  
BOOL GetStatusBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если может отображаться в строке состояния; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется к Internet Explorer. При использовании этот вызов с помощью элемента управления WebBrowser, ошибка не возвращается, но он будет игнорировать этот вызов.  
  
##  <a name="gettheatermode"></a>CHtmlView::GetTheaterMode  
 Вызовите эту функцию-член, чтобы определить, является ли веб-браузера в режиме театра.  
  
```  
BOOL GetTheaterMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если веб-браузера находится в режиме театра. в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 При веб-браузера находится в режиме театра, главное окно обозревателя занимает весь экран, появляется панель инструментов с минимальным набором средств навигации и в строке состояния отображается в правом верхнем углу экрана.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="gettoolbar"></a>CHtmlView::GetToolBar  
 Вызовите эту функцию-член для определения, видима ли панель инструментов.  
  
```  
int GetToolBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, указывающее, видима ли панель инструментов. Ненулевое значение, если панель инструментов отображается на экране; в противном случае — нуль.  
  
##  <a name="gettop"></a>CHtmlView::GetTop  
 Вызовите эту функцию-член для получения координаты экрана верхнего края элемента управления WebBrowser главного окна.  
  
```  
long GetTop() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес переменной, которая получает координат экрана верхнего края главного окна.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="gettoplevelcontainer"></a>CHtmlView::GetTopLevelContainer  
 Вызовите эту функцию-член для определения верхнего уровня контейнера элемента управления WebBrowser Internet Explorer.  
  
```  
BOOL GetTopLevelContainer() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, контейнер является контейнером верхнего уровня; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="gettype"></a>CHtmlView::GetType  
 Вызовите эту функцию-член для получения имени типа автономной активного документа.  
  
```  
CString GetType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий имя типа автономной активного документа.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getvisible"></a>CHtmlView::GetVisible  
 Вызовите эту функцию-член для определения, является ли видимым содержащегося объекта.  
  
```  
BOOL GetVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект является видимым; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="getwidth"></a>CHtmlView::GetWidth  
 Получает ширину главного окна Internet Explorer.  
  
```  
long GetWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая ширина окна в пикселях.  
  
##  <a name="goback"></a>CHtmlView::GoBack  
 Переходит назад один элемент в списке журнала.  
  
```  
void GoBack();
```  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="goforward"></a>CHtmlView::GoForward  
 Переход вперед один элемент в списке журнала.  
  
```  
void GoForward();
```  
  
##  <a name="gohome"></a>CHtmlView::GoHome  
 Переходит к текущей домашней или начальной странице, указанной в диалоговом окне "Свойства браузера" в Internet Explorer или в диалоговом окне "Свойства Интернета", доступном из панели управления.  
  
```  
void GoHome();
```  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="gosearch"></a>CHtmlView::GoSearch  
 Переходит к текущей странице поиска, как указано в диалоговом окне Свойства обозревателя Internet Explorer или в диалоговом окне Свойства Интернета доступны из панели управления.  
  
```  
void GoSearch();
```  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="loadfromresource"></a>CHtmlView::LoadFromResource  
 Вызовите эту функцию-член для загрузки указанного ресурса в элемент управления WebBrowser.  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszResource`  
 Указатель на строку, содержащую имя ресурса для загрузки.  
  
 `nRes`  
 Идентификатор буфер, содержащий имя ресурса для загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="navigate"></a>CHtmlView::Navigate  
 Вызовите эту функцию-член для перехода к ресурсу, определяемому URL-адрес.  
  
```  
void Navigate(
    LPCTSTR URL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *URL-АДРЕС*  
 Строка, содержащая URL-адрес для перехода к выделенный вызывающим объектом, или полный путь файла для отображения.  
  
 `dwFlags`  
 Флаги переменную, которая указывает, следует ли добавить ресурс в список журнала, чтение или запись из кэша и для отображения ресурса в новом окне. Переменная может быть сочетанием значений, определенных в [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) перечисления.  
  
 `lpszTargetFrameName`  
 Указатель на строку, содержащую имя кадра, в которой отображаются ресурса.  
  
 `lpszHeaders`  
 Указатель на значение, указывающее, заголовки HTTP для отправки на сервер. Эти заголовки добавляются к заголовкам Internet Explorer по умолчанию. Заголовки можно указать такие элементы, как действия, необходимые на сервере, тип данных, передаваемых на сервер или код состояния. Этот параметр учитывается, если *URL-адрес* не является URL-адрес HTTP.  
  
 `lpvPostData`  
 Указатель на данные для отправки с помощью операции HTTP POST. Например транзакция POST используется для отправки данных, собранных HTML-форму. Если этот параметр не указан, все данные post **перехода** выдает операции HTTP GET. Этот параметр учитывается, если *URL-адрес* не является URL-адрес HTTP.  
  
 `dwPostDataLen`  
 Данные для отправки с помощью операции HTTP POST. Например транзакция POST используется для отправки данных, собранных HTML-форму. Если этот параметр не указан, все данные post **перехода** выдает операции HTTP GET. Этот параметр учитывается, если *URL-адрес* не является URL-адрес HTTP.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="navigate2"></a>CHtmlView::Navigate2  
 Вызовите эту функцию-член для перемещения ресурса, указанного в URL-адрес или файл, указанный параметром полный путь.  
  
```  
void Navigate2(
    LPITEMIDLIST pIDL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);

 
void Navigate2(
    LPCTSTR lpszURL,  
    DWORD dwFlags,  
    CByteArray& baPostedData,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeader = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pIDL*  
 Указатель на [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) структуры.  
  
 `dwFlags`  
 Флаги переменную, которая указывает, следует ли добавить ресурс в список журнала, чтение или запись из кэша и для отображения ресурса в новом окне. Переменная может быть сочетанием значений, определенных в [BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx) перечисления.  
  
 `lpszTargetFrameName`  
 Указатель на строку, содержащую имя кадра, в которой отображаются ресурса.  
  
 `lpszURL`  
 Указатель на строку, содержащую URL-адрес.  
  
 `lpvPostData`  
 Данные для отправки с помощью операции HTTP POST. Например транзакция POST используется для отправки данных, собранных HTML-форму. Если этот параметр не указан, все данные post `Navigate2` выдает операции HTTP GET. Этот параметр учитывается, если *URL-адрес* не является HTTP или HTTPS URL-адрес.  
  
 `dwPostDataLen`  
 Размер в байтах данных, на который указывает `lpvPostData` параметр.  
  
 `lpszHeaders`  
 Указатель на значение, указывающее, заголовки HTTP или HTTPS для отправки на сервер. Эти заголовки добавляются к заголовкам Internet Explorer по умолчанию. Заголовки можно указать такие элементы, как действия, необходимые на сервере, тип данных, передаваемых на сервер или код состояния. Этот параметр учитывается, если *URL-адрес* не является HTTP или HTTPS URL-адрес.  
  
 `baPostedData`  
 Ссылку на [CByteArray](../../mfc/reference/cbytearray-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член расширяет **перехода** функция-член, поддерживая страниц на специальные папки, такие как рабочий стол и Мой компьютер, представленный параметром *pIDL*.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCHtmlHttp&#7;](../../mfc/reference/codesnippet/cpp/chtmlview-class_1.cpp)]  
  
##  <a name="onbeforenavigate2"></a>CHtmlView::OnBeforeNavigate2  
 Эта функция-член вызывается платформой для вызывают события, возникающего перед его выполнением в веб-браузере.  
  
```  
virtual void OnBeforeNavigate2(
    LPCTSTR lpszURL,  
    DWORD nFlags,  
    LPCTSTR lpszTargetFrameName,  
    CByteArray& baPostedData,  
    LPCTSTR lpszHeaders,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszURL`  
 Указатель на строку, содержащую URL-адрес для перехода.  
  
 `nFlags`  
 Зарезервировано для будущего использования.  
  
 `lpszTargetFrameName`  
 Строка, содержащая имя фрейма, для отображения ресурсов, или **NULL** Если нет именованный фрейм предназначена для ресурса.  
  
 `baPostedData`  
 Ссылку на `CByteArray` объект, содержащий данные для отправки на сервер, если используется транзакции HTTP POST.  
  
 `lpszHeaders`  
 Указатель на строку, содержащую дополнительные заголовки HTTP для отправки на сервер (HTTP URL-адреса только). Заголовки можно указать такие элементы, как действия, необходимые на сервере, тип данных, передаваемых на сервер или код состояния.  
  
 `pbCancel`  
 Указатель на флаг "Отмена". Приложение может задать этот параметр на ненулевое значение, для отмены операции навигации или равным нулю, чтобы позволить приложению продолжить.  
  
##  <a name="oncommandstatechange"></a>CHtmlView::OnCommandStateChange  
 Эта функция-член вызывается платформой для оповещения приложения, что изменилось состояние команды браузера веб-узел.  
  
```  
virtual void OnCommandStateChange(
    long nCommand,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 *nCommand*  
 Идентификатор команды включено состояние которого изменилось.  
  
 `bEnable`  
 Состояние включения. Этот параметр имеет ненулевое значение, если команда включена, или нуль, если она отключена.  
  
##  <a name="ondocumentcomplete"></a>CHtmlView::OnDocumentComplete  
 Эта функция-член вызывается платформой для оповещения приложения, что документ был достигнут `READYSTATE_COMPLETE` состояния.  
  
```  
virtual void OnDocumentComplete(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszURL`  
 Указатель на строку, результатом которого является URL-адрес, UNC файла имя, или PIDL (указатель на идентификатор элемента списка), к которому был осуществлен переход.  
  
### <a name="remarks"></a>Примечания  
 Не каждый кадр запустит это событие, но каждого кадра, который запускает [OnDownloadBegin](#ondownloadbegin) событий будут срабатывать соответствующий `OnDocumentComplete` события.  
  
 Указывает URL-адрес `lpszURL` может отличаться от URL-адрес, браузер посоветовали перейдите к, поскольку этот URL-адрес является каноническому и полные URL-адрес. Например, если приложение указывает URL-адрес «www.microsoft.com» при обращении к [перехода](#navigate) или [Navigate2](#navigate2), URL-адрес, передаваемый по `OnNavigateComplete2` будет «http://www.microsoft.com/». Кроме того Если сервер обозреватель перенаправлен на другой URL-адрес, URL-адреса перенаправления будут отражены здесь.  
  
##  <a name="ondocwindowactivate"></a>CHtmlView::OnDocWindowActivate  
 Вызывается из реализованного в Internet Explorer или MSHTML метода **IOleInPlaceActiveObject::OnDocWindowActivate**, который уведомляет активный встроенный объект об активации или отключении окна документа контейнера.  
  
```  
virtual HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>Параметры  
 `fActivate`  
 Указывает состояние окна документа. Если это значение отлично от нуля, окно активируется. Если это значение равно нулю, окно выключается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успеха или код ошибки OLE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnDocWindowActivate` реагировать на `OnDocWindowActivate` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="ondownloadbegin"></a>CHtmlView::OnDownloadBegin  
 Эта функция-член вызывается платформой для начала загрузки документа.  
  
```  
virtual void OnDownloadBegin();
```  
  
### <a name="remarks"></a>Примечания  
 Это событие возникает сразу после [OnBeforeNavigate2](#onbeforenavigate2) событие, если переход отменяется. Любой анимации или «занят» означает, что необходимо отобразить контейнер должен быть подключен к этому событию.  
  
##  <a name="ondownloadcomplete"></a>CHtmlView::OnDownloadComplete  
 Эта функция-член вызывается платформой для указания, что операция перехода закончилась, была остановлена или не удалось.  
  
```  
virtual void OnDownloadComplete();
```  
  
##  <a name="onenablemodeless"></a>CHtmlView::OnEnableModeless  
 Вызывается, когда Internet Explorer или MSHTML отображает модальный пользовательский Интерфейс.  
  
```  
virtual HRESULT OnEnableModeless(BOOL fEnable);
```  
  
### <a name="parameters"></a>Параметры  
 `fEnable`  
 Указывает, если безрежимные диалоговые окна узла включены или отключены. Если это значение не равно нулю, безрежимные диалоговые окна будут включены. Если это значение равно нулю, безрежимные диалоговые окна будут отключены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успеха или код ошибки OLE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Включает или отключает безрежимные диалоговые окна, когда контейнер создает или удаляет модального диалогового окна. Переопределение `OnEnableModeless` реагировать на `EnableModeless` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="onfilterdataobject"></a>CHtmlView::OnFilterDataObject  
 Вызывается Internet Explorer или MSHTML в основном приложении, чтобы разрешить ему заменить объект данных Internet Explorer или MSHTML.  
  
```  
virtual HRESULT OnFilterDataObject(
    LPDATAOBJECT pDataObject,  
    LPDATAOBJECT* ppDataObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pDataObject`  
 Адрес [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Internet Explorer или MSHTML.  
  
 *ppDataObject*  
 Адрес, который получает `IDataObject` указатель интерфейса, предоставляемого узлом. Содержимое этого параметра всегда должен быть инициализирован для **NULL**, даже если происходит сбой метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`При замене объекта данных, **S_FALSE** Если объект данных не заменяет, или код ошибки, определенное OLE, если произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnFilterDataObject` реагировать на `FilterDataObject` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="onframewindowactivate"></a>CHtmlView::OnFrameWindowActivate  
 Вызывается из [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) уведомлять объект контейнера верхнего уровня окно активируется или деактивируется.  
  
```  
virtual HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="parameters"></a>Параметры  
 `fActivate`  
 Указывает состояние окна верхнего уровня кадра контейнера. Если это значение отлично от нуля, окно активируется. Если это значение равно нулю, окно выключается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успеха или код ошибки OLE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnFrameWindowActivate` реагировать на `OnFrameWindowActivate` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="onfullscreen"></a>CHtmlView::OnFullScreen  
 Эта функция-член вызывается инфраструктурой при [во весь экран](https://msdn.microsoft.com/library/aa752119.aspx) измененное свойство.  
  
```  
virtual void OnFullScreen(BOOL bFullScreen);
```  
  
### <a name="parameters"></a>Параметры  
 *bFullScreen*  
 Ненулевое значение, если Internet Explorer в полноэкранном режиме; в противном случае — нуль.  
  
##  <a name="ongetdroptarget"></a>CHtmlView::OnGetDropTarget  
 Вызывается Internet Explorer или MSHTML при использовании в качестве целевого объекта перетаскивания, чтобы разрешить основному приложению предоставить альтернативный интерфейс `IDropTarget`.  
  
```  
virtual HRESULT OnGetDropTarget(
    LPDROPTARGET pDropTarget,  
    LPDROPTARGET* ppDropTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pDropTarget`  
 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) Internet Explorer или MSHTML предлагает для использования.  
  
 `ppDropTarget`  
 Адрес `IDropTarget` , который получает `IDropTarget` указатель интерфейса, которые требуется предоставить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В разделе [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список кодов возврата.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnGetDropTarget` реагировать на `GetDropTarget` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="ongetexternal"></a>CHtmlView::OnGetExternal  
 Вызывается Internet Explorer или MSHTML для получения интерфейса `IDispatch` основного приложения.  
  
```  
virtual HRESULT OnGetExternal(LPDISPATCH* lppDispatch);
```  
  
### <a name="parameters"></a>Параметры  
 *lppDispatch*  
 Указатель на адрес, который получает `IDispatch` указатель интерфейса ведущего приложения. Если узел предоставляет доступ к интерфейсу автоматизации, он предоставляет ссылку на Internet Explorer или MSHTML при помощи этого параметра. Содержимое этого параметра всегда должен быть инициализирован для **NULL**, даже если происходит сбой метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успеха или код ошибки OLE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnGetExternal` реагировать на `GetExternal` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="ongethostinfo"></a>CHtmlView::OnGetHostInfo  
 Возвращает возможности пользовательского интерфейса основного приложения Internet Explorer или MSHTML.  
  
```  
virtual HRESULT OnGetHostInfo(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `pInfo`  
 Адрес [DOCHOSTUIINFO](https://msdn.microsoft.com/library/aa770044.aspx) структуру, которая получает возможности пользовательского интерфейса узла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успеха или код ошибки OLE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnGetHostInfo` реагировать на `GetHostInfo` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="ongetoptionkeypath"></a>CHtmlView::OnGetOptionKeyPath  
 Вызовите эту функцию-член для получения раздела реестра, в котором Internet Explorer или MSHTML сохраняет настройки пользователя.  
  
```  
virtual HRESULT OnGetOptionKeyPath(
    LPOLESTR* pchKey,  
    DWORD dwReserved);
```  
  
### <a name="parameters"></a>Параметры  
 `pchKey`  
 Адрес `LPOLESTR` , который получает строку подраздела реестра, где узел сохраняет свои параметры по умолчанию. Этот раздел будет в разделе HKEY_CURRENT_USER. Выделить эту память с помощью [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727). Вызывающее приложение отвечает за освобождение этого памяти с помощью [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722). Этот параметр всегда должен быть инициализирован для **NULL**, даже если происходит сбой метода.  
  
 `dwReserved`  
 Зарезервировано для будущего использования. Сейчас не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успешного выполнения или **S_FALSE** в противном случае. Если **S_FALSE**, Internet Explorer или MSHTML по умолчанию для параметров пользователя.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnGetOptionKeyPath` реагировать на `GetOptionKeyPath` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="onhideui"></a>CHtmlView::OnHideUI  
 Эта функция-член вызывается платформой, когда Internet Explorer или MSHTML удаляет его меню и панели инструментов.  
  
```  
virtual HRESULT OnHideUI();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успеха или код ошибки OLE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnHideUI` реагировать на `HideUI` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="onmenubar"></a>CHtmlView::OnMenuBar  
 Эта функция-член вызывается инфраструктурой при [MenuBar](https://msdn.microsoft.com/library/aa752131.aspx) измененное свойство.  
  
```  
virtual void OnMenuBar(BOOL bMenuBar);
```  
  
### <a name="parameters"></a>Параметры  
 *bMenuBar*  
 Ненулевое значение, если Internet Explorer меню является видимым. в противном случае — нуль.  
  
##  <a name="onnavigatecomplete2"></a>CHtmlView::OnNavigateComplete2  
 Эта функция-член вызывается платформой после завершения перехода по гиперссылке (в элементе окно или рамка).  
  
```  
virtual void OnNavigateComplete2(LPCTSTR strURL);
```  
  
### <a name="parameters"></a>Параметры  
 *strURL*  
 Строковое выражение, результатом которого является URL-адрес, UNC имя файла, или PIDL (указатель на идентификатор элемента списка), к которому был осуществлен переход.  
  
### <a name="remarks"></a>Примечания  
 Параметр URL-адреса может быть PIDL в случае сущности пространства имени оболочки, для которого нет нет URL-адрес представления.  
  
 Обратите внимание, что URL-адрес содержится в *strURL* может отличаться от URL-адрес, браузер посоветовали перейдите к, поскольку этот URL-адрес является каноническому и полные URL-адрес. Например, если приложение указывает URL-адрес «www.microsoft.com» при обращении к [перехода](#navigate) или [Navigate2](#navigate2), URL-адрес, передаваемый по `OnNavigateComplete2` будет «http://www.microsoft.com/». Кроме того Если сервер обозреватель перенаправлен на другой URL-адрес, URL-адреса перенаправления будут отражены здесь.  
  
##  <a name="onnavigateerror"></a>CHtmlView::OnNavigateError  
 Вызывается платформой, если переход по гиперссылке завершается ошибкой.  
  
```  
virtual void OnNavigateError(
    LPCTSTR lpszURL,  
    LPCTSTR lpszFrame,  
    DWORD dwError,  
    BOOL* pbCancel);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszURL`  
 URL-адрес, для которых не удалось навигации.  
  
 *lpszFrame*  
 Имя кадра, в котором будет отображаться или значение NULL, если ресурс был направлен без рамки именованного ресурса.  
  
 `dwError`  
 Ошибка код состояния, если он доступен. Список возможных кодов состояния HRESULT и HTTP см. в разделе [NavigateError коды состояния события.](https://msdn.microsoft.com/library/aa768365.aspx)  
  
 `pbCancel`  
 Указывает необходимость отмены перехода на страницу ошибки или любые дополнительные автоматического. Если **TRUE** (по умолчанию), продолжить переход к странице ошибки или автоматического; Если **FALSE**, Отмена перехода к странице ошибки или автоматического.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для предоставления пользовательских переходов обработки ошибок.  
  
 Дополнительные сведения см. в разделе [DWebBrowserEvents2::NavigateError](https://msdn.microsoft.com/library/aa768286.aspx)  
  
##  <a name="onnewwindow2"></a>CHtmlView::OnNewWindow2  
 Эта функция-член вызывается инфраструктурой при новом окне должны быть созданы для отображения ресурса.  
  
```  
virtual void OnNewWindow2(
    LPDISPATCH* ppDisp,  
    BOOL* Cancel);
```  
  
### <a name="parameters"></a>Параметры  
 `ppDisp`  
 Указатель на указатель интерфейса, при необходимости, получает `IDispatch` указатель на интерфейс нового объекта WebBrowser или Internet Explorer.  
  
 `Cancel`  
 Указатель на флаг "Отмена". Приложение может задать этот параметр на ненулевое значение, для отмены операции навигации или равным нулю, чтобы позволить приложению продолжить.  
  
### <a name="remarks"></a>Примечания  
 Это событие предшествует созданию нового окна из элемента управления WebBrowser.  
  
##  <a name="onprogresschange"></a>CHtmlView::OnProgressChange  
 Эта функция-член вызывается платформой для оповещения приложения, что ход выполнения операции загрузки был обновлен.  
  
```  
virtual void OnProgressChange(
    long nProgress,  
    long nProgressMax);
```  
  
### <a name="parameters"></a>Параметры  
 *nProgress*  
 Сумма общего прогресса показ или -1, если завершен.  
  
 *nProgressMax*  
 Текущее максимальное значение.  
  
### <a name="remarks"></a>Примечания  
 Контейнер можно использовать сведения, предоставляемые это событие для отображения количество загруженных байт или обновлять индикатор хода выполнения.  
  
##  <a name="onpropertychange"></a>CHtmlView::OnPropertyChange  
 Эта функция-член вызывается платформой для оповещения приложения, [PutProperty](#putproperty) изменилось значение свойства.  
  
```  
virtual void OnPropertyChange(LPCTSTR lpszProperty);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProperty`  
 Указатель на строку, содержащую имя свойства.  
  
##  <a name="onquit"></a>CHtmlView::OnQuit  
 Эта функция-член вызывается платформой для оповещения приложения, что приложение Internet Explorer Готово закрыться.  
  
```  
virtual void OnQuit();
```  
  
##  <a name="onresizeborder"></a>CHtmlView::OnResizeBorder  
 Вызывается из Internet Explorer или MSHTML реализацию [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), предупреждающее, если нужно изменить размер пространства границы объекта.  
  
```  
virtual HRESULT OnResizeBorder(
    LPCRECT prcBorder,  
    LPOLEINPLACEUIWINDOW pUIWindow,  
    BOOL fFrameWindow);
```  
  
### <a name="parameters"></a>Параметры  
 `prcBorder`  
 Новый внешний прямоугольник границы пространства.  
  
 `pUIWindow`  
 Указатель на интерфейс для объекта окна фрейма или документа, границу которого изменилось.  
  
 `fFrameWindow`  
 **Значение TRUE,** при вызове окна фрейма [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), в противном случае **FALSE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успеха или код ошибки OLE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnResizeBorder` реагировать на `ResizeBorder` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="onshowcontextmenu"></a>CHtmlView::OnShowContextMenu  
 Вызывается из Internet Explorer или MSHTML перед отображением контекстного меню.  
  
```  
virtual HRESULT OnShowContextMenu(
    DWORD dwID,  
    LPPOINT ppt,  
    LPUNKNOWN pcmdtReserved,  
    LPDISPATCH pdispReserved);
```  
  
### <a name="parameters"></a>Параметры  
 `dwID`  
 Идентификатор для отображения контекстного меню. В разделе **IDocHostUIHandler::ShowContextMenu** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список значений.  
  
 `ppt`  
 Экранные координаты для меню.  
  
 `pcmdtReserved`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797) интерфейс, используемый для запроса состояния команды и выполнения команд на этот объект.  
  
 `pdispReserved`  
 Интерфейс IDispatch объекта с экранными координатами. Это позволяет узла для различения конкретные объекты для предоставления более конкретным контекстом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В разделе [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список значений.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnShowContextMenu` реагировать на `ShowContextMenu` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="onshowui"></a>CHtmlView::OnShowUI  
 Вызывается перед отображением меню и панелей инструментов в Internet Explorer или MSHTML.  
  
```  
virtual HRESULT OnShowUI(
    DWORD dwID,  
    LPOLEINPLACEACTIVEOBJECT pActiveObject,  
    LPOLECOMMANDTARGET pCommandTarget,  
    LPOLEINPLACEFRAME pFrame,  
    LPOLEINPLACEUIWINDOW pDoc);
```  
  
### <a name="parameters"></a>Параметры  
 `dwID`  
 Зарезервировано для будущего использования.  
  
 `pActiveObject`  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) интерфейс активного объекта.  
  
 `pCommandTarget`  
 [IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797) интерфейс объекта.  
  
 `pFrame`  
 [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) интерфейс объекта. Это необходимо для меню и панелей инструментов.  
  
 `pDoc`  
 [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) интерфейс для объекта. Это необходимо для панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В разделе [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список значений.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnShowUI` реагировать на `ShowUI` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="onstatusbar"></a>CHtmlView::OnStatusBar  
 Эта функция-член вызывается инфраструктурой при [StatusBar](https://msdn.microsoft.com/library/aa768270.aspx) измененное свойство.  
  
```  
virtual void OnStatusBar(BOOL bStatusBar);
```  
  
### <a name="parameters"></a>Параметры  
 *bStatusBar*  
 Ненулевое значение, если отображается в строке состояния Internet Explorer или в противном случае — нуль.  
  
##  <a name="onstatustextchange"></a>CHtmlView::OnStatusTextChange  
 Эта функция-член вызывается платформой для уведомления приложения, измененного текста в строке состояния, связанный с элементом управления WebBrowser.  
  
```  
virtual void OnStatusTextChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Строка, содержащая новый текст строки состояния.  
  
##  <a name="ontheatermode"></a>CHtmlView::OnTheaterMode  
 Эта функция-член вызывается инфраструктурой при [TheaterMode](https://msdn.microsoft.com/library/aa768273.aspx) измененное свойство.  
  
```  
virtual void OnTheaterMode(BOOL bTheaterMode);
```  
  
### <a name="parameters"></a>Параметры  
 *bTheaterMode*  
 Ненулевое значение, если Internet Explorer находится в режиме театра. в противном случае — нуль.  
  
##  <a name="ontitlechange"></a>CHtmlView::OnTitleChange  
 Эта функция-член вызывается платформой для оповещения приложения, если заголовок документа в элементе управления WebBrowser становится доступным или изменения.  
  
```  
virtual void OnTitleChange(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Новый заголовок документа.  
  
### <a name="remarks"></a>Примечания  
 Заголовок для HTML, может измениться; пока еще загружается HTML, URL-адрес документа задается как заголовок. После реальных title (если таковой имеется) анализируется от HTML, заголовок изменены фактическое название.  
  
##  <a name="ontoolbar"></a>CHtmlView::OnToolBar  
 Эта функция-член вызывается инфраструктурой при [инструментов](https://msdn.microsoft.com/library/aa768274.aspx) измененное свойство.  
  
```  
virtual void OnToolBar(BOOL bToolBar);
```  
  
### <a name="parameters"></a>Параметры  
 *bToolBar*  
 Ненулевое значение, если отображается панель инструментов Internet Explorer или в противном случае — нуль.  
  
##  <a name="ontranslateaccelerator"></a>CHtmlView::OnTranslateAccelerator  
 Вызывается Internet Explorer или MSHTML при [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) или [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) вызывается для обработки сообщений сочетаний клавиш меню из контейнера очереди сообщений.  
  
```  
virtual HRESULT OnTranslateAccelerator(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMsg`  
 Указывает сообщение, которое необходимо преобразовать.  
  
 `pguidCmdGroup`  
 Идентификатор группы команд.  
  
 `nCmdID`  
 Идентификатор команды.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успешного выполнения или **S_FALSE** в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnTranslateAccelerator` реагировать на `TranslateAccelerator` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="ontranslateurl"></a>CHtmlView::OnTranslateUrl  
 Вызывается Internet Explorer или MSHTML, чтобы разрешить основному приложению изменять URL-адрес, который нужно загрузить.  
  
```  
virtual HRESULT OnTranslateUrl(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>Параметры  
 `dwTranslate`  
 Зарезервировано для будущего использования.  
  
 `pchURLIn`  
 Адрес, предоставляемые Internet Explorer или MSHTML, представляющий URL-адрес перевода строки.  
  
 `ppchURLOut`  
 Адрес указатель на строку, принимающая адрес переведенные URL-адрес. Узел выделяет буфер с помощью распределения памяти для задач. Содержимое этого параметра всегда должен быть инициализирован для **NULL**, даже если URL-адрес не преобразуется, или происходит сбой метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`Если URL-адрес был преобразован, **S_FALSE** Если URL-адрес не был преобразован, или код ошибки OLE, если произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `OnTranslateUrl` реагировать на `TranslateUrl` уведомления из элемента управления веб-обозревателем Майкрософт. В разделе [IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
##  <a name="onupdateui"></a>CHtmlView::OnUpdateUI  
 Уведомляет основное приложение об изменении состояния команды.  
  
```  
virtual HRESULT OnUpdateUI();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`в случае успеха или код ошибки OLE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Узел должен обновить состояние кнопки панели инструментов. Этот метод вызывается независимо от возвращаемого значения из `ShowUI`. Переопределение `OnUpdateUI` реагировать на `UpdateUI` уведомления из элемента управления веб-обозревателем Майкрософт.  
  
##  <a name="onvisible"></a>CHtmlView::OnVisible  
 Эта функция-член вызывается инфраструктурой при окна для элемента управления WebBrowser должны быть отображены или скрыты.  
  
```  
virtual void OnVisible(BOOL bVisible);
```  
  
### <a name="parameters"></a>Параметры  
 `bVisible`  
 Ненулевое значение, если объект является видимым или в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет главного окна управления объекта вести себя так же, как будет вести себя окно Internet Explorer.  
  
##  <a name="putproperty"></a>CHtmlView::PutProperty  
 Вызовите эту функцию-член для задания свойства, связанные с данным объектом.  
  
```  
void PutProperty(
    LPCTSTR lpszProperty,  
    const VARIANT& vtValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    double dValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    long lValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    LPCTSTR lpszValue);

 
void PutProperty(
    LPCTSTR lpszPropertyName,  
    short nValue);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProperty`  
 Строка, содержащая свойства.  
  
 *vtValue*  
 Указывает новое значение свойства `lpszProperty`.  
  
 *lpszPropertyName*  
 Указатель на строку, содержащую имя свойства.  
  
 *dValue*  
 Новое значение свойства.  
  
 `lValue`  
 Новое значение свойства.  
  
 `lpszValue`  
 Указатель на строку, содержащую новое значение свойства.  
  
 `nValue`  
 Новое значение свойства.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="queryformscommand"></a>CHtmlView::QueryFormsCommand  
 Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.  
  
```  
HRESULT QueryFormsCommand(
    DWORD dwCommandID,  
    BOOL* pbSupported,  
    BOOL* pbEnabled,  
    BOOL* pbChecked);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCommandID`  
 Идентификатор команды, для которого запрашивается.  
  
 *pbSupported*  
 Указатель на **BOOL** указание Если команда (идентифицируются `dwCommandID`) поддерживается. Значение TRUE, если команда поддерживается; в противном случае — значение FALSE.  
  
 `pbEnabled`  
 Указатель на **BOOL** указание Если команда (идентифицируются `dwCommandID`) включен. Значение TRUE, если команда поддерживается; в противном случае — значение FALSE.  
  
 *pbChecked*  
 Указатель на **BOOL** указание Если команда (идентифицируются `dwCommandID`) установлен. Значение TRUE, если команда поддерживается; в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` . Полный список возможных значений см. в разделе [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 `QueryFormsCommand`реализует поведение [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) метод.  
  
##  <a name="querystatuswb"></a>CHtmlView::QueryStatusWB  
 Вызовите эту функцию-член для запроса состояния команды.  
  
```  
OLECMDF QueryStatusWB(OLECMDID cmdID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 [OLECMDID](http://msdn.microsoft.com/library/windows/desktop/ms691264) значение команды, для которых вызывающему объекту необходимо сведения о состоянии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237) значение, которое получает состояние команды.  
  
### <a name="remarks"></a>Примечания  
 `QueryStatusWB`реализует поведение [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) метод.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="refresh"></a>CHtmlView::Refresh  
 Перезагружает URL-адрес или файл, который веб-браузера в настоящее время отображения.  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Примечания  
 **Обновить** не содержит параметров для задания уровня обновления.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="refresh2"></a>CHtmlView::Refresh2  
 Повторно загружает файл, который в данный момент отображает Internet Explorer.  
  
```  
void Refresh2(int nLevel);
```  
  
### <a name="parameters"></a>Параметры  
 `nLevel`  
 Адрес переменной, указывающие уровень обновления. Возможные переменные определяются в [RefreshConstants](https://msdn.microsoft.com/library/aa768363.aspx)в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 В отличие от [обновление](#refresh), `Refresh2` содержит параметр, определяющий уровень обновления.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="setaddressbar"></a>CHtmlView::SetAddressBar  
 Вызовите эту функцию-член для отображения или скрытия в адресной строке Internet Explorer объекта.  
  
```  
void SetAddressBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Ненулевое значение, чтобы показать адресной строкой. в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется к Internet Explorer. При использовании этот вызов с помощью элемента управления WebBrowser, ошибка не возвращается, но он будет игнорировать этот вызов.  
  
##  <a name="setfullscreen"></a>CHtmlView::SetFullScreen  
 Вызовите эту функцию-член для установки Internet Explorer в либо окно Полноэкранный или обычный режим.  
  
```  
void SetFullScreen(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Ненулевое значение для полноэкранного режима; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 В полноэкранном режиме развернуто главного окна Internet Explorer и строки состояния, панели инструментов, меню и заголовок окна скрыты.  
  
 Применяется к Internet Explorer. При использовании этот вызов с помощью элемента управления WebBrowser, ошибка не возвращается, но он будет игнорировать этот вызов.  
  
##  <a name="setheight"></a>CHtmlView::SetHeight  
 Вызовите эту функцию-член устанавливать высоту главного окна Internet Explorer.  
  
```  
void SetHeight(long nNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewValue`  
 Высота в пикселях главного окна.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="setleft"></a>CHtmlView::SetLeft  
 Задает положение главного окна Internet Explorer по горизонтали.  
  
```  
void SetLeft(long nNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewValue`  
 Экранная координата левой части главного окна.  
  
##  <a name="setmenubar"></a>CHtmlView::SetMenuBar  
 Вызовите эту функцию-член для отображения или скрытия меню Internet Explorer.  
  
```  
void SetMenuBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Ненулевое значение, чтобы отобразить меню; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется к Internet Explorer. При использовании этот вызов с помощью элемента управления WebBrowser, ошибка не возвращается, но он будет игнорировать этот вызов.  
  
##  <a name="setoffline"></a>CHtmlView::SetOffline  
 Эта функция элемента значение, указывающее, работает ли в данный момент элемента управления WebBrowser в автономном режиме.  
  
```  
void SetOffline(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Ненулевое значение для чтения из локального кэша; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 В автономном режиме обозреватель считывает HTML-страницы из локального кэша, а не из исходного документа.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="setregisterasbrowser"></a>CHtmlView::SetRegisterAsBrowser  
 Эта функция элемента значение, указывающее, зарегистрирован ли элемент управления WebBrowser верхнего уровня браузера для разрешения имен целевой.  
  
```  
void SetRegisterAsBrowser(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Определяет, зарегистрирован ли Internet Explorer в качестве обозревателя верхнего уровня. Если значение ненулевое, веб-браузер зарегистрирован в качестве обозревателя верхнего уровня; Если значение равно нулю, это не обозревателя верхнего уровня. Значение по умолчанию равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Обозревателя верхнего уровня является обозревателем, установить в реестре как браузер по умолчанию.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="setregisterasdroptarget"></a>CHtmlView::SetRegisterAsDropTarget  
 Эта функция элемента значение, указывающее, зарегистрирован ли элемент управления WebBrowser в качестве назначения для навигации.  
  
```  
void SetRegisterAsDropTarget(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Определяет, зарегистрирован ли элемент управления WebBrowser местом назначения для навигации. Если значение ненулевое, объект зарегистрирован как цель перетаскивания; Если значение равно нулю, это не цели перетаскивания.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="setsilent"></a>CHtmlView::SetSilent  
 Эта функция элемента значение, указывающее, может ли отображаться все диалоговые окна.  
  
```  
void SetSilent(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Если значение ненулевое, диалоговые окна не отображается; Если значение равно нулю, будет отображаться диалоговые окна. Значение по умолчанию равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="setstatusbar"></a>CHtmlView::SetStatusBar  
 Вызовите эту функцию-член для отображения в строке состояния.  
  
```  
void SetStatusBar(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Ненулевое значение, если в строке состояния отображается; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется к Internet Explorer. При использовании этот вызов с помощью элемента управления WebBrowser, ошибка не возвращается, но он будет игнорировать этот вызов.  
  
##  <a name="settheatermode"></a>CHtmlView::SetTheaterMode  
 Эта функция элемента значение, указывающее, является ли элемент управления WebBrowser в режиме театра.  
  
```  
void SetTheaterMode(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Ненулевое значение, чтобы задать элемент управления WebBrowser в режиме театра. в противном случае — нуль. Значение по умолчанию равно нулю.  
  
### <a name="remarks"></a>Примечания  
 При веб-браузера находится в режиме театра, главное окно обозревателя занимает весь экран, появляется панель инструментов с минимальным набором средств навигации и в строке состояния отображается в правом верхнем углу экрана.  
  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="settoolbar"></a>CHtmlView::SetToolBar  
 Вызовите эту функцию-член для отображения или скрытия панели инструментов Internet Explorer.  
  
```  
void SetToolBar(int nNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewValue`  
 Указывает, следует ли отображать панель инструментов. Ненулевое значение, если панель инструментов для отображения; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется к Internet Explorer. При использовании этот вызов с помощью элемента управления WebBrowser, ошибка не возвращается, но он будет игнорировать этот вызов.  
  
##  <a name="settop"></a>CHtmlView::SetTop  
 Эта функция члена, чтобы задать расстояние между внутренним верхним краем элемента управления WebBrowser и верхним краем его контейнера  
  
```  
void SetTop(long nNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewValue`  
 Координата экрана верхнего края главного окна.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="setvisible"></a>CHtmlView::SetVisible  
 Вызовите эту функцию-член для задания состояния видимости элемента управления WebBrowser.  
  
```  
void SetVisible(BOOL bNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bNewValue`  
 Ненулевое значение, если элемент управления является видимым; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
##  <a name="setwidth"></a>CHtmlView::SetWidth  
 Задает ширину главного окна Internet Explorer.  
  
```  
void SetWidth(long nNewValue);
```  
  
### <a name="parameters"></a>Параметры  
 `nNewValue`  
 Ширина в пикселях главного окна Internet Explorer.  
  
##  <a name="stop"></a>CHtmlView::Stop  
 Вызовите эту функцию-член для отмены все незаконченные переходы или загрузки операции и остановить все динамические элементы страниц, такие как фоновые звуки и анимации.  
  
```  
void Stop();
```  
  
### <a name="remarks"></a>Примечания  
 Применяется в Internet Explorer и WebBrowser.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MFCIE](../../visual-cpp-samples.md)   
 [Класс CFormView](../../mfc/reference/cformview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx)


