---
title: "Класс CHtmlView | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "браузеры, поддержка MFC для"
  - "Класс CHtmlView"
  - "WebBrowser - элемент управления"
  - "элемент управления WebBrowser, поддержка MFC"
ms.assetid: 904976af-73de-4aba-84ac-cfae8e2be09a
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# Класс CHtmlView
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности элемента управления WebBrowser в контексте архитектуры документов или представлений MFC.  
  
## Синтаксис  
  
```  
class CHtmlView : public CFormView  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHtmlView::Create](../Topic/CHtmlView::Create.md)|Создает элемент управления WebBrowser.|  
|[CHtmlView::CreateControlSite](../Topic/CHtmlView::CreateControlSite.md)|Переопределяемый класс, используемый для создания экземпляра сайта элемента управления для размещения элемента управления на форме.|  
|[CHtmlView::ExecFormsCommand](../Topic/CHtmlView::ExecFormsCommand.md)|Выполняет указанную команду с помощью метода `IOleCommandTarget::Exec`.|  
|[CHtmlView::ExecWB](../Topic/CHtmlView::ExecWB.md)|Выполняет команду.|  
|[CHtmlView::GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)|Определяет, видима ли адресная строка объекта Internet Explorer. \(Элемент управления WebBrowser игнорирует; только Internet Explorer.\)|  
|[CHtmlView::GetApplication](../Topic/CHtmlView::GetApplication.md)|Возвращает объект приложения, который представляет приложение, содержащее текущий экземпляр приложения Internet Explorer.|  
|[CHtmlView::GetBusy](../Topic/CHtmlView::GetBusy.md)|Возвращает значение, указывающее на то, выполняется ли все еще скачивание или другой процесс.|  
|[CHtmlView::GetContainer](../Topic/CHtmlView::GetContainer.md)|Возвращает контейнер элемента управления WebBrowser.|  
|[CHtmlView::GetFullName](../Topic/CHtmlView::GetFullName.md)|Извлекает полное имя, включая путь ресурса, отображаемого в веб\-браузере. \(Элемент управления WebBrowser игнорирует; только Internet Explorer.\)|  
|[CHtmlView::GetFullScreen](../Topic/CHtmlView::GetFullScreen.md)|Указывает, работает ли элемент управления WebBrowser в полноэкранном режиме или в обычном режиме окна.|  
|[CHtmlView::GetHeight](../Topic/CHtmlView::GetHeight.md)|Получает высоту главного окна Internet Explorer.|  
|[CHtmlView::GetHtmlDocument](../Topic/CHtmlView::GetHtmlDocument.md)|Получает активный документ HTML.|  
|[CHtmlView::GetLeft](../Topic/CHtmlView::GetLeft.md)|Получает координату левого края главного окна Internet Explorer.|  
|[CHtmlView::GetLocationName](../Topic/CHtmlView::GetLocationName.md)|Получает имя ресурса, который в данный момент отображается элементом управления WebBrowser.|  
|[CHtmlView::GetLocationURL](../Topic/CHtmlView::GetLocationURL.md)|Получает URL\-адрес ресурса, который в данный момент отображается элементом управления WebBrowser.|  
|[CHtmlView::GetMenuBar](../Topic/CHtmlView::GetMenuBar.md)|Получает значение, указывающее, является ли строка меню видимой.|  
|[CHtmlView::GetOffline](../Topic/CHtmlView::GetOffline.md)|Получает значение, указывающее, находится ли элемент управления в автономном режиме.|  
|[CHtmlView::GetParentBrowser](../Topic/CHtmlView::GetParentBrowser.md)|Получает указатель на интерфейс `IDispatch`. Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](http://msdn.microsoft.com/ru-ru/0e171f7f-0022-4e9b-ac8e-98192828e945).|  
|[CHtmlView::GetProperty](../Topic/CHtmlView::GetProperty.md)|Возвращает текущее значение свойства, связанного с данным объектом.|  
|[CHtmlView::GetReadyState](../Topic/CHtmlView::GetReadyState.md)|Получает состояние готовности объекта веб\-браузера.|  
|[CHtmlView::GetRegisterAsBrowser](../Topic/CHtmlView::GetRegisterAsBrowser.md)|Указывает, зарегистрирован ли элемент управления WebBrowser в качестве браузера верхнего уровня для разрешения целевых имен.|  
|[CHtmlView::GetRegisterAsDropTarget](../Topic/CHtmlView::GetRegisterAsDropTarget.md)|Указывает, зарегистрирован ли элемент управления WebBrowser в качестве целевого объекта перетаскивания для навигации.|  
|[CHtmlView::GetSilent](../Topic/CHtmlView::GetSilent.md)|Указывает, могут ли отображаться какие\-либо диалоговые окна.|  
|[CHtmlView::GetSource](../Topic/CHtmlView::GetSource.md)|Исходный код HTML веб\-страницы.|  
|[CHtmlView::GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)|Указывает, является ли строка состояния Internet Explorer видимой. \(Элемент управления WebBrowser игнорирует; только Internet Explorer.\)|  
|[CHtmlView::GetTheaterMode](../Topic/CHtmlView::GetTheaterMode.md)|Указывает, находится ли элемент управления WebBrowser в режиме театра.|  
|[CHtmlView::GetToolBar](../Topic/CHtmlView::GetToolBar.md)|Получает значение, указывающее, является ли панель инструментов видимой.|  
|[CHtmlView::GetTop](../Topic/CHtmlView::GetTop.md)|Получает координату верхнего края главного окна Internet Explorer.|  
|[CHtmlView::GetTopLevelContainer](../Topic/CHtmlView::GetTopLevelContainer.md)|Получает значение, указывающее, является ли текущий объект контейнером верхнего уровня для элемента управления WebBrowser.|  
|[CHtmlView::GetType](../Topic/CHtmlView::GetType.md)|Получает имя типа объекта документа.|  
|[CHtmlView::GetVisible](../Topic/CHtmlView::GetVisible.md)|Получает значение, указывающее, является ли объект видимым или скрытым.|  
|[CHtmlView::GetWidth](../Topic/CHtmlView::GetWidth.md)|Получает ширину главного окна Internet Explorer.|  
|[CHtmlView::GoBack](../Topic/CHtmlView::GoBack.md)|Переходит к предыдущему элементу в списке журнала.|  
|[CHtmlView::GoForward](../Topic/CHtmlView::GoForward.md)|Переходит к следующему элементу в списке журнала.|  
|[CHtmlView::GoHome](../Topic/CHtmlView::GoHome.md)|Переходит к текущей домашней или начальной странице.|  
|[CHtmlView::GoSearch](../Topic/CHtmlView::GoSearch.md)|Переходит к текущей странице поиска.|  
|[CHtmlView::LoadFromResource](../Topic/CHtmlView::LoadFromResource.md)|Загружает ресурс в элементе управления WebBrowser.|  
|[CHtmlView::Navigate](../Topic/CHtmlView::Navigate.md)|Переходит к ресурсу, определяемому URL\-адресом.|  
|[CHtmlView::Navigate2](../Topic/CHtmlView::Navigate2.md)|Переходит к ресурсу, определяемому URL\-адресом, или файлу, определяемому полным путем.|  
|[CHtmlView::OnBeforeNavigate2](../Topic/CHtmlView::OnBeforeNavigate2.md)|Вызывается до того, как начинается переход в данном элементе управления WebBrowser \(в окне или элементе набора фреймов\).|  
|[CHtmlView::OnCommandStateChange](../Topic/CHtmlView::OnCommandStateChange.md)|Вызывается для уведомления приложения о том, что состояние выполнения команды веб\-браузера изменилось.|  
|[CHtmlView::OnDocumentComplete](../Topic/CHtmlView::OnDocumentComplete.md)|Вызывается для уведомления приложения о том, что документ достиг состояния `READYSTATE_COMPLETE`.|  
|[CHtmlView::OnDocWindowActivate](../Topic/CHtmlView::OnDocWindowActivate.md)|Вызывается из реализованного в Internet Explorer или MSHTML метода [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281), который уведомляет активный встроенный объект об активации или отключении окна документа контейнера.|  
|[CHtmlView::OnDownloadBegin](../Topic/CHtmlView::OnDownloadBegin.md)|Вызывается для уведомления приложения о том, что начинается операция перехода.|  
|[CHtmlView::OnDownloadComplete](../Topic/CHtmlView::OnDownloadComplete.md)|Вызывается, когда операция перехода закончилась, была остановлена или завершилась с ошибкой.|  
|[CHtmlView::OnEnableModeless](../Topic/CHtmlView::OnEnableModeless.md)|Вызывается для включения или отключения безрежимных диалоговых окон, когда контейнер создает или уничтожает модальное диалоговое окно.|  
|[CHtmlView::OnFilterDataObject](../Topic/CHtmlView::OnFilterDataObject.md)|Вызывается Internet Explorer или MSHTML в основном приложении, чтобы разрешить ему заменить объект данных Internet Explorer или MSHTML.|  
|[CHtmlView::OnFrameWindowActivate](../Topic/CHtmlView::OnFrameWindowActivate.md)|Вызывается из [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969), чтобы уведомить объект об активации или отключении окна фрейма верхнего уровня контейнера.|  
|[CHtmlView::OnFullScreen](../Topic/CHtmlView::OnFullScreen.md)|Вызывается после изменения свойства FullScreen.|  
|[CHtmlView::OnGetDropTarget](../Topic/CHtmlView::OnGetDropTarget.md)|Вызывается Internet Explorer или MSHTML при использовании в качестве целевого объекта перетаскивания, чтобы разрешить основному приложению предоставить альтернативный интерфейс [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[CHtmlView::OnGetExternal](../Topic/CHtmlView::OnGetExternal.md)|Вызывается Internet Explorer или MSHTML для получения интерфейса `IDispatch` основного приложения.|  
|[CHtmlView::OnGetHostInfo](../Topic/CHtmlView::OnGetHostInfo.md)|Возвращает возможности пользовательского интерфейса основного приложения Internet Explorer или MSHTML.|  
|[CHtmlView::OnGetOptionKeyPath](../Topic/CHtmlView::OnGetOptionKeyPath.md)|Возвращает раздел реестра, в котором хранятся пользовательские настройки Internet Explorer или MSHTML.|  
|[CHtmlView::OnHideUI](../Topic/CHtmlView::OnHideUI.md)|Вызывается при удалении меню и панелей инструментов Internet Explorer или MSHTML.|  
|[CHtmlView::OnMenuBar](../Topic/CHtmlView::OnMenuBar.md)|Вызывается после изменения свойства MenuBar.|  
|[CHtmlView::OnNavigateComplete2](../Topic/CHtmlView::OnNavigateComplete2.md)|Вызывается после того, как выполнен переход по гиперссылке \(в окне или элементе набора фреймов\).|  
|[CHtmlView::OnNavigateError](../Topic/CHtmlView::OnNavigateError.md)|Вызывается платформой, если переход по гиперссылке завершается ошибкой.|  
|[CHtmlView::OnNewWindow2](../Topic/CHtmlView::OnNewWindow2.md)|Вызывается, если для отображения ресурса должно быть создано окно.|  
|[CHtmlView::OnProgressChange](../Topic/CHtmlView::OnProgressChange.md)|Вызывается для уведомления приложения о том, что ход операции скачивания был обновлен.|  
|[CHtmlView::OnPropertyChange](../Topic/CHtmlView::OnPropertyChange.md)|Вызывается для уведомления приложения о том, что метод [PutProperty](../Topic/CHtmlView::PutProperty.md) изменил значение свойства.|  
|[CHtmlView::OnQuit](../Topic/CHtmlView::OnQuit.md)|Вызывается для уведомления приложения о том, что приложение Internet Explorer готово закрыться. \(Применяется только в Internet Explorer.\)|  
|[CHtmlView::OnResizeBorder](../Topic/CHtmlView::OnResizeBorder.md)|Вызывается из реализованного в Internet Explorer или MSHTML метода [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053), который оповещает объект о необходимости изменить размер пространства вокруг границы.|  
|[CHtmlView::OnShowContextMenu](../Topic/CHtmlView::OnShowContextMenu.md)|Вызывается из Internet Explorer или MSHTML перед отображением контекстного меню.|  
|[CHtmlView::OnShowUI](../Topic/CHtmlView::OnShowUI.md)|Вызывается перед отображением меню и панелей инструментов в Internet Explorer или MSHTML.|  
|[CHtmlView::OnStatusBar](../Topic/CHtmlView::OnStatusBar.md)|Вызывается после изменения свойства StatusBar.|  
|[CHtmlView::OnStatusTextChange](../Topic/CHtmlView::OnStatusTextChange.md)|Вызывается для уведомления приложения о том, что текст строки состояния, связанной с элементом управления WebBrowser, изменился.|  
|[CHtmlView::OnTheaterMode](../Topic/CHtmlView::OnTheaterMode.md)|Вызывается после изменения свойства TheaterMode.|  
|[CHtmlView::OnTitleChange](../Topic/CHtmlView::OnTitleChange.md)|Вызывается для уведомления приложения о том, что заголовок документа в элементе управления WebBrowser стал доступен или изменился.|  
|[CHtmlView::OnToolBar](../Topic/CHtmlView::OnToolBar.md)|Вызывается после изменения свойства ToolBar.|  
|[CHtmlView::OnTranslateAccelerator](../Topic/CHtmlView::OnTranslateAccelerator.md)|Вызывается Internet Explorer или MSHTML при вызове метода [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) или [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) для обработки сообщений об использовании сочетаний клавиш, связанных с меню, из очереди сообщений контейнера.|  
|[CHtmlView::OnTranslateUrl](../Topic/CHtmlView::OnTranslateUrl.md)|Вызывается Internet Explorer или MSHTML, чтобы разрешить основному приложению изменять URL\-адрес, который нужно загрузить.|  
|[CHtmlView::OnUpdateUI](../Topic/CHtmlView::OnUpdateUI.md)|Уведомляет основное приложение об изменении состояния команды.|  
|[CHtmlView::OnVisible](../Topic/CHtmlView::OnVisible.md)|Вызывается, когда окно элемента управления WebBrowser должно быть показано или скрыто.|  
|[CHtmlView::PutProperty](../Topic/CHtmlView::PutProperty.md)|Задает значение свойства, связанного с данным объектом.|  
|[CHtmlView::QueryFormsCommand](../Topic/CHtmlView::QueryFormsCommand.md)|Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.|  
|[CHtmlView::QueryStatusWB](../Topic/CHtmlView::QueryStatusWB.md)|Запрашивает состояние команды, обрабатываемой элементом управления WebBrowser.|  
|[CHtmlView::Refresh](../Topic/CHtmlView::Refresh.md)|Перезагружает текущий файл.|  
|[CHtmlView::Refresh2](../Topic/CHtmlView::Refresh2.md)|Перезагружает текущий файл и при необходимости блокирует отправку заголовка `pragma:nocache`.|  
|[CHtmlView::SetAddressBar](../Topic/CHtmlView::SetAddressBar.md)|Отображает или скрывает адресную строку объекта Internet Explorer. \(Элемент управления WebBrowser игнорирует; только Internet Explorer.\)|  
|[CHtmlView::SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)|Задает значение, которое указывает, работает ли элемент управления в полноэкранном режиме или в обычном режиме окна. \(Элемент управления WebBrowser игнорирует; только Internet Explorer.\)|  
|[CHtmlView::SetHeight](../Topic/CHtmlView::SetHeight.md)|Задает высоту главного окна Internet Explorer.|  
|[CHtmlView::SetLeft](../Topic/CHtmlView::SetLeft.md)|Задает положение главного окна Internet Explorer по горизонтали.|  
|[CHtmlView::SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)|Задает значение, указывающее, является ли строка меню элемента управления видимой. \(Элемент управления WebBrowser игнорирует; только Internet Explorer.\)|  
|[CHtmlView::SetOffline](../Topic/CHtmlView::SetOffline.md)|Задает значение, указывающее, находится ли элемент управления в автономном режиме.|  
|[CHtmlView::SetRegisterAsBrowser](../Topic/CHtmlView::SetRegisterAsBrowser.md)|Задает значение, которое указывает, зарегистрирован ли элемент управления WebBrowser в качестве браузера верхнего уровня для разрешения целевых имен.|  
|[CHtmlView::SetRegisterAsDropTarget](../Topic/CHtmlView::SetRegisterAsDropTarget.md)|Задает значение, которое указывает, зарегистрирован ли элемент управления WebBrowser в качестве целевого объекта перетаскивания для навигации.|  
|[CHtmlView::SetSilent](../Topic/CHtmlView::SetSilent.md)|Задает значение, указывающее, будет ли элемент управления выводить диалоговые окна.|  
|[CHtmlView::SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)|Задает значение, которое указывает, является ли строка состояния Internet Explorer видимой. \(Элемент управления WebBrowser игнорирует; только Internet Explorer.\)|  
|[CHtmlView::SetTheaterMode](../Topic/CHtmlView::SetTheaterMode.md)|Задает значение, которое указывает, находится ли элемент управления WebBrowser в режиме театра.|  
|[CHtmlView::SetToolBar](../Topic/CHtmlView::SetToolBar.md)|Задает значение, указывающее, является ли панель инструментов элемента управления видимой. \(Элемент управления WebBrowser игнорирует; только Internet Explorer.\)|  
|[CHtmlView::SetTop](../Topic/CHtmlView::SetTop.md)|Задает положение главного окна Internet Explorer по вертикали.|  
|[CHtmlView::SetVisible](../Topic/CHtmlView::SetVisible.md)|Задает значение, указывающее, является ли объект видимым или скрытым.|  
|[CHtmlView::SetWidth](../Topic/CHtmlView::SetWidth.md)|Задает ширину главного окна Internet Explorer.|  
|[CHtmlView::Stop](../Topic/CHtmlView::Stop.md)|Останавливает открытие файла.|  
  
## Заметки  
 Элемент управления WebBrowser — это окно, в котором пользователь может просматривать сайты в Интернете, а также папки в локальной файловой системе и в сети. Элемент управления WebBrowser поддерживает гиперссылки и переход по URL\-адресам. Кроме того, в нем ведется список журнала.  
  
## Использование класса CHtmlView в приложении MFC  
 В стандартном приложении платформы MFC \(на основе SDI или MDI\) объект представления обычно является производным от специального набора классов. Эти классы, производные от `CView`, предоставляют специальные возможности, которые отсутствуют у класса `CView`.  
  
 Если класс представления приложения основан на `CHtmlView`, представление обеспечивается элементом управления WebBrowser. Это фактически делает приложение веб\-браузером. Предпочтительным способом создания приложений в стиле веб\-браузера является использование мастера приложений MFC и указание `CHtmlView` в качестве класса представления. Дополнительные сведения о реализации и использовании элемента управления WebBrowser в приложениях MFC см. в разделе [Создание приложения в стиле веб\-браузера](../../mfc/reference/creating-a-web-browser-style-mfc-application.md).  
  
> [!NOTE]
>  Элемент ActiveX WebBrowser \(и, следовательно, `CHtmlView`\) доступен только для программ, выполняемых под управлением ОС Windows NT версии 4.0 или более поздней, в которой установлен Internet Explorer 4.0 или более поздней версии.  
  
 `CHtmlView` предназначен для приложений, получающих доступ к Интернету \(или документам HTML\). Перечисленные ниже функции\-члены `CHtmlView` относятся только к приложению Internet Explorer. Они будут успешно выполняться в элементе управления WebBrowser, но не будут иметь никакого видимого эффекта.  
  
-   [GetAddressBar](../Topic/CHtmlView::GetAddressBar.md)  
  
-   [GetFullName](../Topic/CHtmlView::GetFullName.md)  
  
-   [GetStatusBar](../Topic/CHtmlView::GetStatusBar.md)  
  
-   [SetAddressBar](../Topic/CHtmlView::SetAddressBar.md)  
  
-   [SetFullScreen](../Topic/CHtmlView::SetFullScreen.md)  
  
-   [SetMenuBar](../Topic/CHtmlView::SetMenuBar.md)  
  
-   [SetStatusBar](../Topic/CHtmlView::SetStatusBar.md)  
  
-   [SetToolBar](../Topic/CHtmlView::SetToolBar.md)  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CHtmlView`  
  
## Требования  
 **Заголовок:** afxhtml.h  
  
## См. также  
 [Пример MFC MFCIE](../../top/visual-cpp-samples.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx)