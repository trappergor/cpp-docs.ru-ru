---
title: "CFrameWnd-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWnd
- AFXWIN/CFrameWnd
- AFXWIN/CFrameWnd::CFrameWnd
- AFXWIN/CFrameWnd::ActivateFrame
- AFXWIN/CFrameWnd::BeginModalState
- AFXWIN/CFrameWnd::Create
- AFXWIN/CFrameWnd::CreateView
- AFXWIN/CFrameWnd::DockControlBar
- AFXWIN/CFrameWnd::EnableDocking
- AFXWIN/CFrameWnd::EndModalState
- AFXWIN/CFrameWnd::FloatControlBar
- AFXWIN/CFrameWnd::GetActiveDocument
- AFXWIN/CFrameWnd::GetActiveFrame
- AFXWIN/CFrameWnd::GetActiveView
- AFXWIN/CFrameWnd::GetControlBar
- AFXWIN/CFrameWnd::GetDockState
- AFXWIN/CFrameWnd::GetMenuBarState
- AFXWIN/CFrameWnd::GetMenuBarVisibility
- AFXWIN/CFrameWnd::GetMessageBar
- AFXWIN/CFrameWnd::GetMessageString
- AFXWIN/CFrameWnd::GetTitle
- AFXWIN/CFrameWnd::InitialUpdateFrame
- AFXWIN/CFrameWnd::InModalState
- AFXWIN/CFrameWnd::IsTracking
- AFXWIN/CFrameWnd::LoadAccelTable
- AFXWIN/CFrameWnd::LoadBarState
- AFXWIN/CFrameWnd::LoadFrame
- AFXWIN/CFrameWnd::NegotiateBorderSpace
- AFXWIN/CFrameWnd::OnBarCheck
- AFXWIN/CFrameWnd::OnContextHelp
- AFXWIN/CFrameWnd::OnSetPreviewMode
- AFXWIN/CFrameWnd::OnUpdateControlBarMenu
- AFXWIN/CFrameWnd::RecalcLayout
- AFXWIN/CFrameWnd::SaveBarState
- AFXWIN/CFrameWnd::SetActivePreviewView
- AFXWIN/CFrameWnd::SetActiveView
- AFXWIN/CFrameWnd::SetDockState
- AFXWIN/CFrameWnd::SetMenuBarState
- AFXWIN/CFrameWnd::SetMenuBarVisibility
- AFXWIN/CFrameWnd::SetMessageText
- AFXWIN/CFrameWnd::SetProgressBarPosition
- AFXWIN/CFrameWnd::SetProgressBarRange
- AFXWIN/CFrameWnd::SetProgressBarState
- AFXWIN/CFrameWnd::SetTaskbarOverlayIcon
- AFXWIN/CFrameWnd::SetTitle
- AFXWIN/CFrameWnd::ShowControlBar
- AFXWIN/CFrameWnd::ShowOwnedWindows
- AFXWIN/CFrameWnd::OnCreateClient
- AFXWIN/CFrameWnd::OnHideMenuBar
- AFXWIN/CFrameWnd::OnShowMenuBar
- AFXWIN/CFrameWnd::m_bAutoMenuEnable
- AFXWIN/CFrameWnd::rectDefault
dev_langs:
- C++
helpviewer_keywords:
- frame window classes, base class
- single document interface (SDI), frame windows
- frame windows, creating
- CFrameWnd class
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
caps.latest.revision: 21
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 06becdd593028e02d45ed68fb8fa5687e1e2dbd1
ms.lasthandoff: 04/04/2017

---
# <a name="cframewnd-class"></a>CFrameWnd-класс
Реализует функции однодокументного интерфейса Windows (SDI) с наложенным или всплывающим фреймовым окном с элементами для управления окном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](#cframewnd)|Создает объект `CFrameWnd`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](#activateframe)|Делает кадр видимым и доступным для пользователя.|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|Задает модальное окно фрейма.|  
|[CFrameWnd::Create](#create)|Вызов для создания и инициализации окно фрейма Windows, связанное с `CFrameWnd` объекта.|  
|[CFrameWnd::CreateView](#createview)|Создает представление внутри кадра, который не является производным от `CView`.|  
|[CFrameWnd::DockControlBar](#dockcontrolbar)|Закрепляет панель элементов управления.|  
|[CFrameWnd::EnableDocking](#enabledocking)|Позволяет панель элементов управления можно закреплять.|  
|[CFrameWnd::EndModalState](#endmodalstate)|Завершает модальное состояние окна фрейма. Включает все окна отключено по `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Отображается панель элементов управления.|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Возвращает активное **CDocument** объекта.|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Возвращает активное `CFrameWnd` объекта.|  
|[CFrameWnd::GetActiveView](#getactiveview)|Возвращает активное `CView` объекта.|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|Возвращает значение, на панели управления.|  
|[CFrameWnd::GetDockState](#getdockstate)|Получает состояние закрепления окна фрейма.|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Получает состояние отображения меню в текущем приложении MFC.|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Указывает, является ли поведение по умолчанию меню в текущем приложении MFC видимым или скрытым.|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|Возвращает указатель строки принадлежащего фрейм окна состояния.|  
|[CFrameWnd::GetMessageString](#getmessagestring)|Получает сообщение, соответствующее идентификатору команды.|  
|[CFrameWnd::GetTitle](#gettitle)|Извлекает заголовок панели связанных элементов управления.|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Вызывает `OnInitialUpdate` относящиеся ко всем представлениям в окне фрейма для вызова функции-члена.|  
|[CFrameWnd::InModalState](#inmodalstate)|Возвращает значение, указывающее, является ли окно фрейма в модальное состояние.|  
|[CFrameWnd::IsTracking](#istracking)|Определяет, если разделитель перемещается в данный момент.|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Вызов для загрузки таблицы сочетаний клавиш.|  
|[CFrameWnd::LoadBarState](#loadbarstate)|Вызов, чтобы восстановить параметры панели управления.|  
|[CFrameWnd::LoadFrame](#loadframe)|Вызов для динамического создания окна фрейма из сведений о ресурсах.|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Согласовывает граница места в окне фрейма.|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|Вызывается, когда действие выполняется в строке указанного элемента управления.|  
|[CFrameWnd::OnContextHelp](#oncontexthelp)|Обрабатывает клавиши SHIFT + F1 справки для элементов на месте.|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Задает главное окно приложения, в действие и из режима предварительного просмотра перед печатью.|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|Вызывается платформой при обновлении связанным меню.|  
|[CFrameWnd::RecalcLayout](#recalclayout)|Изменяет положение панелей элементов управления из `CFrameWnd` объекта.|  
|[CFrameWnd::SaveBarState](#savebarstate)|Вызов, чтобы сохранить параметры панели управления.|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Обозначает указанное представление, необходимо активное представление для расширенного просмотра.|  
|[CFrameWnd::SetActiveView](#setactiveview)|Задает активный `CView` объекта.|  
|[CFrameWnd::SetDockState](#setdockstate)|Вызов, чтобы закрепить окно в главном окне.|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Задает состояние отображения меню в текущем приложении MFC для скрытого или отображается.|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Задает поведение по умолчанию меню в текущем приложении MFC, чтобы быть видимым или скрытым.|  
|[CFrameWnd::SetMessageText](#setmessagetext)|Задает текст строки состояния standard.|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Задает текущую позицию для Windows 7 индикатор выполнения отображается на панели задач.|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Задание диапазона для Windows 7 индикатор выполнения отображается на панели задач.|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Задает тип и состояние индикатора, отображаемый на кнопке панели задач.|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Перегружен. Применяет наложенной на кнопку панели задач, чтобы указать состояние приложения или уведомление пользователю.|  
|[CFrameWnd::SetTitle](#settitle)|Задает заголовок панели связанных элементов управления.|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Вызов для отображения на панели управления.|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Показывает все окна, которые являются потомками `CFrameWnd` объекта.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|Создает окно клиента для кадра.|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Вызывается перед меню в текущем приложении MFC скрыто.|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Вызывается перед отображением меню в текущем приложении MFC.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Элементы управления автоматическое включение и отключение функциональные возможности для элементов меню.|  
|[CFrameWnd::rectDefault](#rectdefault)|Передать этот статический `CRect` как параметр при создании `CFrameWnd` объекта, чтобы разрешить операционной системе Windows выберите исходный размер и положение окна.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать окно фрейма полезно для приложения, создайте класс, производный от `CFrameWnd`. Добавьте переменные-члены в производный класс для хранения данных, относящихся к конкретному приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.  
  
 Для создания окна фрейма тремя способами:  
  
-   Непосредственно создать его с помощью [создать](#create).  
  
-   Непосредственно создать его с помощью [LoadFrame](#loadframe).  
  
-   Косвенно создайте его с помощью шаблона документа.  
  
 Перед вызовом метода либо **создать** или `LoadFrame`, необходимо создать объект окна фрейма в куче, с помощью C++ **новый** оператор. Перед вызовом метода **создать**, можно также зарегистрировать класс окна с [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) глобальной функции, чтобы задать значок и класс стили рамки.  
  
 Используйте **создать** функции-члена для передачи как интерпретации аргументов параметры создания фрейма.  
  
 `LoadFrame`требуется меньшее количество аргументов, чем **создать**и вместо этого извлекает большую часть значений по умолчанию из ресурсов, включая заголовок, значок, таблицу сочетаний клавиш и меню опорного кадра. Чтобы быть доступным, `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, **IDR_MAINFRAME**).  
  
 Если `CFrameWnd` объект содержит представления и документы, они создаются неявно платформой вместо программистом. `CDocTemplate` Объект организует Создание фрейма, создания представлений, содержащих и соединение представлений в соответствующий документ. Параметры `CDocTemplate` укажите конструктор `CRuntimeClass` из трех классов участвующих (документа, фрейма и представления). Объект `CRuntimeClass` объект используется платформой для динамического создания новых кадров, задаваемых пользователем (например, с помощью команды создания файла или несколько команду создания окна интерфейса (MDI) документа).  
  
 Окна фрейма класс, производный от `CFrameWnd` должны быть объявлены с `DECLARE_DYNCREATE` в порядке для указанных выше `RUNTIME_CLASS` механизм для правильной работы.  
  
 Объект `CFrameWnd` содержит реализации по умолчанию для выполнения следующих функций главное окно в обычном приложении для Windows:  
  
-   Значение типа `CFrameWnd` фрейм окна отслеживает отслеживания объекта активно представление, которое не зависит от окна Windows или текущий фокус ввода. При возобновлении кадр активное представление уведомляется путем вызова `CView::OnActivateView`.  
  
-   Команда сообщения и много общих сообщения уведомления кадра, включая те обработано `OnSetFocus`, `OnHScroll`, и `OnVScroll` функции `CWnd`, полномочия с `CFrameWnd` фрейма окна для активного представления.  
  
-   В настоящее время активное представление (или в настоящее время активную дочернюю фрейма MDI в случае фрейма MDI) можно определить заголовок окна фрейма. Эту функцию можно отключить, отключив **FWS_ADDTOTITLE** бит стиля рамки окна.  
  
-   Значение типа `CFrameWnd` фрейм окна управляет положение панелей элементов управления, представлений и других дочерних окон в клиентской области окна фрейма. Окна фрейма также выполняет обновление времени простоя панели инструментов и другие кнопки панели элементов управления. Значение типа `CFrameWnd` фрейм окна также имеет реализацию по умолчанию команды для переключения, включение и отключение панели инструментов и состояние.  
  
-   Значение типа `CFrameWnd` фрейм окна управляет главного меню. Когда появится всплывающее меню окна фрейма использует **UPDATE_COMMAND_UI** механизм для определения, какие элементы меню должны быть включены, отключены или проверки. Когда пользователь выбирает пункт меню, в строке состояния окна фрейма обновляет строку сообщения для этой команды.  
  
-   Значение типа `CFrameWnd` фрейм окна содержит таблицу необязательный сочетаний клавиш, который автоматически преобразует сочетания клавиш.  
  
-   Объект `CFrameWnd` фрейм окна имеет идентификатор справки необязательный набор с `LoadFrame` , используемый для контекстной справки. Окна фрейма является главной orchestrator полумодальные состояния, такие как контекстной справки (SHIFT + F1) и режима предварительного просмотра перед печатью.  
  
-   Значение типа `CFrameWnd` фрейм окна откроется файл из диспетчера файлов перетаскивать на фрейм окна. Если расширение файла зарегистрировано и связанные с приложением, фрейм окна отвечает на динамических данных exchange (DDE) откройте запрос, происходит, когда пользователь открывает файл данных в диспетчере файлов или когда **ShellExecute** функция Windows.  
  
-   Если окно фрейма главного окна приложения (то есть `CWinThread::m_pMainWnd`), когда пользователь закрывает приложение, фрейм окна с приглашением сохранить все измененные документы (для `OnClose` и `OnQueryEndSession`).  
  
-   Если окно фрейма главного окна приложения, в область окна является контекст для выполняющегося WinHelp. При закрытии окна фрейма завершит работу WINHELP. Exe-ФАЙЛ, если он был запущен справку для этого приложения.  
  
 Не используйте C++ **удалить** оператор для уничтожения окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow` . `CFrameWnd` Реализация `PostNcDestroy` приведет к удалению объекта C++ при уничтожении окна. Когда пользователь закрывает окно фрейма, значение по умолчанию `OnClose` обработчик вызовет `DestroyWindow`.  
  
 Дополнительные сведения о `CFrameWnd`, в разделе [фреймов](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="activateframe"></a>CFrameWnd::ActivateFrame  
 Вызовите эту функцию-член для активации и восстанавливает фрейм окна, чтобы она была видна и доступные для пользователя.  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>Параметры  
 `nCmdShow`  
 Задает параметр для передачи [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). По умолчанию кадр показано и правильно восстановить.  
  
### <a name="remarks"></a>Примечания  
 Обычно эта функция-член вызывается после события без пользовательского интерфейса, например DDE, OLE и другие события, которое может отображать окна фрейма или его содержимого для пользователя.  
  
 Реализация по умолчанию активирует рамки и переводит ее в верхней части Z-порядке и, при необходимости выполняет те же шаги для фрейма главного окна приложения.  
  
 Переопределите эту функцию-член для изменения способа активации кадра. Например вы можете принудительно дочерних окон MDI и развернуть. Добавьте соответствующие функциональные возможности, а затем вызвать версии базового класса с явным `nCmdShow`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="beginmodalstate"></a>CFrameWnd::BeginModalState  
 Данная функция-член вызывается для преобразования окна фрейма в модальное.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="cframewnd"></a>CFrameWnd::CFrameWnd  
 Создает `CFrameWnd` объекта, но не удалось создать окно видимым кадра.  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите **создать** создание видимого окна.  
  
##  <a name="create"></a>CFrameWnd::Create  
 Вызов для создания и инициализации окно фрейма Windows, связанное с `CFrameWnd` объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CWnd* pParentWnd = NULL,  
    LPCTSTR lpszMenuName = NULL,  
    DWORD dwExStyle = 0,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszClassName`  
 Указывает строку символом null, с именем класса Windows. Имя класса может быть любое имя, зарегистрированное в `AfxRegisterWndClass` глобальной функции или **RegisterClass** функции Windows. Если **NULL**, использует предопределенные по умолчанию `CFrameWnd` атрибуты.  
  
 `lpszWindowName`  
 Указывает завершающуюся значением null строка, представляющая имя окна. Использовать в качестве текста для заголовка окна.  
  
 `dwStyle`  
 Задает окно [стиль](../../mfc/reference/window-styles.md) атрибуты. Включить **FWS_ADDTOTITLE** стиля, если требуется, чтобы в заголовке автоматически отображать имя документа, представленные в окне.  
  
 `rect`  
 Определяет размер и положение окна. `rectDefault` Значение позволяет Windows указать размер и положение нового окна.  
  
 `pParentWnd`  
 Задает родительское окно фрейма окна. Этот параметр должен быть **NULL** для фреймов верхнего уровня.  
  
 *lpszMenuName*  
 Определяет имя ресурса меню для использования с окном. Используйте **MAKEINTRESOURCE** Если меню содержит целочисленный идентификатор вместо строки. Этот параметр может иметь **NULL**.  
  
 `dwExStyle`  
 Задает окно расширенных [стиль](../../mfc/reference/extended-window-styles.md) атрибуты.  
  
 `pContext`  
 Задает указатель [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. Этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создать `CFrameWnd` объекта в два этапа. Во-первых, вызвать конструктор, который создает `CFrameWnd` объекта, а затем вызвать **создать**, который создает окно фрейма Windows и прикрепляет его к `CFrameWnd` объекта. **Создание** инициализирует окна имя класса и имя окна и регистрирует значения по умолчанию для его стиль, родительский и связанным меню.  
  
 Используйте `LoadFrame` вместо **создать** для загрузки фрейм окна из ресурсов, вместо указания аргументов.  
  
##  <a name="createview"></a>CFrameWnd::CreateView  
 Вызовите `CreateView` для создания представления внутри фрейма.  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Параметры  
 `pContext`  
 Указывает тип представления и документа.  
  
 `nID`  
 Идентификатор представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CWnd` объекта, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член для создания «представления», не используйте `CView`-производный внутри фрейма. После вызова метода `CreateView`, необходимо вручную установить активное представление и сделать его видимым; эти задачи не выполняются автоматически по `CreateView`.  
  
##  <a name="dockcontrolbar"></a>CFrameWnd::DockControlBar  
 В результате панель элементов управления закрепить окно фрейма.  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pBar`  
 Указывает на панели управления можно закреплять.  
  
 `nDockBarID`  
 Определяет, какие стороны окна фрейма, рассмотрите возможность закрепления. Может быть 0, или одно или несколько из следующих:  
  
- `AFX_IDW_DOCKBAR_TOP`Закрепить в верхней части окна фрейма.  
  
- **AFX_IDW_DOCKBAR_BOTTOM** закрепления в нижней части окна фрейма.  
  
- `AFX_IDW_DOCKBAR_LEFT`Закрепить в левой части окна фрейма.  
  
- `AFX_IDW_DOCKBAR_RIGHT`Закрепить в правой части окна фрейма.  
  
 Если значение равно 0, панель элементов управления можно прикреплять к любой стороне включено закрепление целевой фрейм окна.  
  
 `lpRect`  
 Определяет, в экранных координатах, место закрепления панели элементов управления в неклиентской области окна фрейма назначения.  
  
### <a name="remarks"></a>Примечания  
 Панель элементов управления будет прикреплен к одной из сторон окна фрейма, заданные в вызовах как [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) и [CFrameWnd::EnableDocking](#enabledocking). Определяется стороне выбран `nDockBarID`.  
  
##  <a name="enabledocking"></a>CFrameWnd::EnableDocking  
 Эта функция вызывается для включения закрепляемых панелей в окне фрейма.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDockStyle`  
 Указывает, какие стороны окна фрейма может служить закрепление сайтов для панелей элементов управления. Может быть один или несколько из следующих:  
  
- `CBRS_ALIGN_TOP`Позволяет закрепления в верхней части клиентской области.  
  
- `CBRS_ALIGN_BOTTOM`Позволяет закрепления в нижней части клиентской области.  
  
- `CBRS_ALIGN_LEFT`Позволяет Закрепление левого края клиентской области.  
  
- `CBRS_ALIGN_RIGHT`Позволяет закрепления в правой части клиентской области.  
  
- `CBRS_ALIGN_ANY`Позволяет в любой части клиентской области закрепления.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию панели элементов управления будет прикреплен к стороне окна фрейма в следующем порядке: сверху, снизу, слева, справа.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CToolBar::Create](../../mfc/reference/ctoolbar-class.md#create).  
  
##  <a name="endmodalstate"></a>CFrameWnd::EndModalState  
 Данная функция-член вызывается для изменения состояния окна с модального на немодальное.  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>Примечания  
 `EndModalState`включает все окна отключено по [BeginModalState](#beginmodalstate).  
  
##  <a name="floatcontrolbar"></a>CFrameWnd::FloatControlBar  
 Вызывайте эту функцию, чтобы вызвать панель элементов управления не закреплено в фрейме окна.  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>Параметры  
 `pBar`  
 Указывает на панели управления, чтобы быть перемещается.  
  
 `point`  
 Расположение, в экранных координатах, где будет размещаться левом верхнем углу панели элементов управления.  
  
 `dwStyle`  
 Указывает выравнивание панели элементов управления по горизонтали или по вертикали в пределах его новый фрейм окна. Он может быть одним из следующих:  
  
- `CBRS_ALIGN_TOP`Ориентирует панели элементов управления по вертикали.  
  
- `CBRS_ALIGN_BOTTOM`Ориентирует панели элементов управления по вертикали.  
  
- `CBRS_ALIGN_LEFT`Ориентирует панели элементов управления по горизонтали.  
  
- `CBRS_ALIGN_RIGHT`Ориентирует панели элементов управления по горизонтали.  
  
 Если стили передаются указание вертикальной или горизонтальной ориентации, панели инструментов будут направлены по горизонтали.  
  
### <a name="remarks"></a>Примечания  
 Как правило это делается при запуске приложения при программа восстанавливает параметры из предыдущего выполнения.  
  
 Эта функция вызывается платформой, когда пользователь вызывает операции drop освободив левой кнопки мыши при перетаскивании в расположении, не доступен для закрепления панели управления.  
  
##  <a name="getactivedocument"></a>CFrameWnd::GetActiveDocument  
 Вызовите эту функцию-член для получения указателя на текущий **CDocument** присоединяется к текущее активное представление.  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий [CDocument](../../mfc/reference/cdocument-class.md). Если нет текущего документа, возвращает **NULL**.  
  
##  <a name="getactiveframe"></a>CFrameWnd::GetActiveFrame  
 Вызовите эту функцию-член для получения указателя на активный дочернего окна многодокументного интерфейса (MDI) окне фрейма MDI.  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активное дочернее окно MDI. Если приложение является приложением SDI или окне фрейма MDI имеет нет активного документа, неявное **это** указатель будет возвращено.  
  
### <a name="remarks"></a>Примечания  
 Если нет активной дочерней MDI-приложения или приложения является однодокументный интерфейс (SDI) неявный **это** возвращается указатель.  
  
##  <a name="getactiveview"></a>CFrameWnd::GetActiveView  
 Вызовите эту функцию-член для получения указателя на активное представление (если таковые имеются), прикрепленный к окну фрейма ( `CFrameWnd`).  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий [CView](../../mfc/reference/cview-class.md). Если нет текущего представления, возвращает **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает **NULL** при вызове для окна главного фрейма MDI ( `CMDIFrameWnd`). В приложении MDI окно главного фрейма MDI не имеет представления, связанные с ним. Вместо этого каждого отдельного дочернего окна ( `CMDIChildWnd`) имеет один или несколько связанных с ним представлений. Активное представление в приложении MDI можно получить, необходимо сначала найти активную дочернюю MDI и выбрав соответствующий активное представление для этого дочернего окна. Активное дочернее окно MDI можно найти путем вызова функции `MDIGetActive` или **GetActiveFrame** как показано в следующем:  
  
 [!code-cpp[NVC_MFCWindowing #2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="getcontrolbar"></a>CFrameWnd::GetControlBar  
 Вызовите `GetControlBar` для получения доступа к панели управления, связанный с идентификатором.  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификационный номер панели элементов управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панели управления, связанный с идентификатором.  
  
### <a name="remarks"></a>Примечания  
 `nID` Параметр ссылается на уникальный идентификатор, переданный **создать** метод панели элементов управления. Дополнительные сведения о панели элементов управления см. в разделе под названием [панелей элементов управления](../../mfc/control-bars.md).  
  
 `GetControlBar`Возвращает панель элементов управления даже в том случае, если он открывается как плавающее окно и таким образом, не в настоящее время дочернее окно фрейма.  
  
##  <a name="getdockstate"></a>CFrameWnd::GetDockState  
 Вызовите эту функцию-член для хранения сведений о фрейм окна панели элементов управления в состоянии `CDockState` объекта.  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `state`  
 Содержит текущее состояние фрейм окна панели элементов управления при возврате.  
  
### <a name="remarks"></a>Примечания  
 После этого можно написать содержимое `CDockState` в хранилище с помощью `CDockState::SaveState` или `Serialize`. Если позднее вы хотите восстановить предыдущее состояние панели элементов управления, загрузить состояние с `CDockState::LoadState` или `Serialize`, затем вызовите `SetDockState` для применения к фрейм окна панели элементов управления в предыдущее состояние.  
  
##  <a name="getmenubarstate"></a>CFrameWnd::GetMenuBarState  
 Получает состояние отображения меню в текущем приложении MFC.  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение может иметь следующие значения:  
  
-   AFX_MBS_VISIBLE (0x01) — меню является видимым.  
  
-   AFX_MBS_HIDDEN (0x02) — меню скрыто.  
  
### <a name="remarks"></a>Примечания  
 Если возникает ошибка времени выполнения, этот метод утверждения в режиме отладки и вызывает исключения, производные от [CException](../../mfc/reference/cexception-class.md) класса.  
  
##  <a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBarVisibility  
 Указывает, является ли состояние по умолчанию меню в текущем приложении MFC скрытыми или видимыми.  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает одно из следующих значений:  
  
-   AFX_MBV_KEEPVISIBLE (0x01) — меню отображается во всех времени и по умолчанию не имеет фокус.  
  
-   AFX_MBV_DISPLAYONFOCUS (0x02) — меню по умолчанию скрыто. Если меню скрыто, нажмите клавишу ALT, чтобы отобразить меню и делает его активным. Если меню отображается, нажмите клавишу ALT или ESC для его скрытия.  
  
-   AFX_MBV_ DISPLAYONFOCUS (0X02) | AFX_MBV_DISPLAYONF10 (0x04) (битовую комбинацию (OR)) — меню по умолчанию скрыто. Если меню скрыто, нажмите клавишу F10, чтобы отобразить меню и делает его активным. Если меню отображается, нажмите клавишу F10, чтобы переключать фокус и отключение меню. Меню отображается до нажатия клавиши ALT или ESC, чтобы скрыть их.  
  
### <a name="remarks"></a>Примечания  
 Если возникает ошибка времени выполнения, этот метод утверждения в режиме отладки и вызывает исключения, производные от [CException](../../mfc/reference/cexception-class.md) класса.  
  
##  <a name="getmessagebar"></a>CFrameWnd::GetMessageBar  
 Вызовите эту функцию-член для получения указателя на строку состояния.  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку состояния окна.  
  
##  <a name="getmessagestring"></a>CFrameWnd::GetMessageString  
 Переопределите эту функцию для передачи пользовательских строк для идентификаторов команд.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор ресурса для нужного сообщения.  
  
 `rMessage`  
 `CString`Объект, в который следует поместить сообщение.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию просто загружает строки, заданной параметром `nID` из файла ресурсов. Эта функция вызывается платформой, когда строку сообщения в строке состояния необходимо обновить.  
  
##  <a name="gettitle"></a>CFrameWnd::GetTitle  
 Извлекает заголовок окна объекта.  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий текущий заголовок окна объекта.  
  
##  <a name="initialupdateframe"></a>CFrameWnd::InitialUpdateFrame  
 Вызовите **IntitialUpdateFrame** после создания новой рамки с **создать**.  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Указывает на документ, с которым связано фрейм окна. Может быть **NULL**.  
  
 `bMakeVisible`  
 Если **TRUE**, указывает, что кадр должен быть видимым и active. Если **FALSE**, которые доступны нет потомков.  
  
### <a name="remarks"></a>Примечания  
 В результате чего все представления этого фрейма окна для получения их `OnInitialUpdate` вызовов.  
  
 Кроме того Если не было ранее активное представление, первичное представление окна фрейма делается активным. Основное представление — это представление с ИД дочернего объекта **AFX_IDW_PANE_FIRST**. Наконец, окно фрейма становится видимым при `bMakeVisible` имеет ненулевое значение. Если `bMakeVisible` равно 0, текущий фокус и видимое состояние окна фрейма останутся без изменений. Вызывайте эту функцию при использовании реализации платформы новый файл и открытие файла необязательно.  
  
##  <a name="inmodalstate"></a>CFrameWnd::InModalState  
 Вызовите эту функцию-член для проверки, если окно фрейма модальные и немодальные.  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если Да; в противном случае — 0.  
  
##  <a name="istracking"></a>CFrameWnd::IsTracking  
 Вызовите эту функцию-член для определения того, если в окне разделитель перемещается в данный момент.  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция разделителей выполняется в данный момент; в противном случае — 0.  
  
##  <a name="loadacceltable"></a>CFrameWnd::LoadAccelTable  
 Вызов для загрузки таблицы сочетание клавиш.  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszResourceName`  
 Определяет имя ресурса сочетаний клавиш. Используйте **MAKEINTRESOURCE** Если ресурс обозначена целочисленный идентификатор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно загружен в таблице сочетаний клавиш; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Только одна таблица может загружаться одновременно.  
  
 Таблицы сочетаний клавиш, загруженных из ресурсов автоматически освобождаются, когда приложение завершает работу.  
  
 При вызове метода `LoadFrame` для создания окна фрейма, платформа загружает таблицу сочетаний клавиш с ресурсами меню и значков, а затем необязателен в последующем вызове функции-члена.  
  
##  <a name="loadbarstate"></a>CFrameWnd::LoadBarState  
 Эта функция вызывается для восстановления параметров каждую панель элементов управления, принадлежащих фрейм окна.  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProfileName`  
 Имя раздела в файле настройки (INI) или ключ в реестре Windows, где хранятся сведения о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Восстановление включает видимость, ориентация по горизонтали и вертикали, состоянием закрепления и положение панелей элементов управления.  
  
 Вы хотите восстановить параметры необходимо записать в реестр перед вызовом метода `LoadBarState`. Записать данные в реестре, вызвав [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Записи этой информации INI-файл, вызвав [SaveBarState](#savebarstate).  
  
##  <a name="loadframe"></a>CFrameWnd::LoadFrame  
 Вызов для динамического создания окна фрейма из сведений о ресурсах.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDResource`  
 Идентификатор общие ресурсы, связанные с окном фрейма.  
  
 *dwDefaultStyle*  
 Опорного кадра [стиль](../../mfc/reference/window-styles.md). Включить **FWS_ADDTOTITLE** стиля, если требуется, чтобы в заголовке автоматически отображать имя документа, представленные в окне.  
  
 `pParentWnd`  
 Указатель на родительский опорного кадра.  
  
 `pContext`  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. Этот параметр может иметь **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Создать `CFrameWnd` объекта в два этапа. Во-первых, вызвать конструктор, который создает `CFrameWnd` объекта, а затем вызвать `LoadFrame`, который загружает окно фрейма Windows и связанных ресурсов и присоединяет окна фрейма для `CFrameWnd` объекта. `nIDResource` Параметр определяет меню, в таблице сочетаний клавиш, значок и ресурс строки заголовка для окна фрейма.  
  
 Используйте **создать** функции-члена вместо `LoadFrame` при необходимости указать все параметры создания окна фрейма.  
  
 Платформа вызывает `LoadFrame` при создании окна фрейма, используя объект шаблона документа.  
  
 Платформа использует `pContext` аргумент, чтобы указать подключение к окну фрейма, включая все объекты, содержащиеся объекты представлений. Можно задать `pContext` аргумент **NULL** при вызове `LoadFrame`.  
  
##  <a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable  
 При включении этого элемента данных (это значение по умолчанию), пункты меню, не имеют `ON_UPDATE_COMMAND_UI` или `ON_COMMAND` обработчики будет автоматически отключена, когда пользователь запрашивает по меню.  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>Примечания  
 Пункты меню, которые имеют `ON_COMMAND` обработчик, но не `ON_UPDATE_COMMAND_UI` обработчик будет включено автоматически.  
  
 Если значение этого элемента данных, элементы меню включаются автоматически таким же образом, что включены кнопки панели инструментов.  
  
> [!NOTE]
> `m_bAutoMenuEnable`не оказывает влияния на пункты меню верхнего уровня.  
  
 Этот элемент данных упрощает реализацию дополнительные команды на основе текущего выбора и уменьшает потребность в написании `ON_UPDATE_COMMAND_UI` обработчики для включения и отключения пунктов меню.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="negotiateborderspace"></a>CFrameWnd::NegotiateBorderSpace  
 Вызовите эту функцию-член для согласования во время активации inplace OLE граница места в окне фрейма.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Параметры  
 *nBorderCmd*  
 Содержит одно из следующих значений из **перечисления BorderCmd**:  
  
- **borderGet** = 1  
  
- **borderRequest** = 2  
  
- **borderSet** = 3  
  
 `lpRectBorder`  
 Указатель на [RECT](../../mfc/reference/rect-structure1.md) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, определяющий координаты границы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является **CFrameWnd** реализации OLE границы пространства согласования.  
  
##  <a name="onbarcheck"></a>CFrameWnd::OnBarCheck  
 Вызывается, когда действие выполняется в строке указанного элемента управления.  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления панели показывается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если появления панели управления. в противном случае — 0.  
  
##  <a name="oncontexthelp"></a>CFrameWnd::OnContextHelp  
 Обрабатывает клавиши SHIFT + F1 справки для элементов на месте.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы включить контекстной справки, необходимо добавить  
  
 [!code-cpp[NVC_MFCDocViewSDI № 16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 инструкции для вашего `CFrameWnd` класса схему сообщений, а также добавить записи в таблице сочетаний клавиш, обычно клавиши SHIFT + F1, чтобы включить эту функцию-член.  
  
 Если приложение является OLE контейнер, `OnContextHelp` помещает все элементы на месте, содержащийся в объекте окна фрейма в режим справки. Курсора примет стрелки и вопросительного знака и пользователь может затем наведите указатель мыши и нажмите левую кнопку мыши для выбора диалоговое окно, окно, меню или кнопки. Эта функция-член вызывает функцию Windows `WinHelp` с контекст справки для объекта под курсором.  
  
##  <a name="oncreateclient"></a>CFrameWnd::OnCreateClient  
 Вызывается средой во время выполнения `OnCreate`.  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Параметры  
 `lpcs`  
 Указатель на Windows [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) структуры.  
  
 `pContext`  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Невозможно вызвать эту функцию.  
  
 Реализация по умолчанию эта функция создает `CView` объекта из сведений, предоставленных в `pContext`, если это возможно.  
  
 Переопределить эту функцию для переопределения значения, передаваемые в `CCreateContext` объекта или изменение создаваемых элементов управления в области главного окна фрейма. `CCreateContext` Можно переопределить элементы, описанные в [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) класса.  
  
> [!NOTE]
>  Не заменяют значения, передаваемые в `CREATESTRUCT` структуры. Они являются только в информационных целях. Если вы хотите переопределить прямоугольник начального окна, например, переопределение `CWnd` функции-члена [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).  
  
##  <a name="onhidemenubar"></a>CFrameWnd::OnHideMenuBar  
 Эта функция вызывается, когда система не собираетесь скрыть строку меню в текущем приложении MFC.  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>Примечания  
 Этот обработчик событий позволяет вашему приложению для выполнения настраиваемых действий, когда система не скрыто в меню. Невозможно запретить меню как скрытые, но могут, например, вызывать другие методы для получения стиль меню или состояния.  
  
##  <a name="onsetpreviewmode"></a>CFrameWnd::OnSetPreviewMode  
 Вызов этой функции-члена переключает окно главного фрейма приложения в режим предварительного просмотра и из него.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Параметры  
 *bPreview*  
 Указывает, следует ли разместить приложение в режиме предварительного просмотра перед печатью. Значение **TRUE** для размещения в режиме предварительного просмотра **FALSE** для выхода из режима предварительного просмотра.  
  
 `pState`  
 Указатель на **CPrintPreviewState** структуры.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию отключает все стандартной панели инструментов и скрывает главного меню и основного окна клиента. Это превращает окна фрейма MDI в временного окна фрейма SDI.  
  
 Переопределите эту функцию-член для настройки скрытие и отображение панелей элементов управления и других частей рамки окна во время предварительного просмотра печати. Вызовите реализацию базового класса из переопределенных версии.  
  
##  <a name="onshowmenubar"></a>CFrameWnd::OnShowMenuBar  
 Эта функция вызывается, когда система не будет отображаться в меню в текущем приложении MFC.  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>Примечания  
 Этот обработчик событий позволяет вашему приложению для выполнения настраиваемых действий, когда отобразится меню. Меню не может запретить отображение, но могут, например, вызывать другие методы для получения стиль меню или состояния.  
  
##  <a name="onupdatecontrolbarmenu"></a>CFrameWnd::OnUpdateControlBarMenu  
 Вызывается платформой при обновлении связанным меню.  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объект, представляющий меню, вызвавшего команду update. Обработчик вызывает метод обновления [включить](../../mfc/reference/ccmdui-class.md#enable) функцию-член `CCmdUI` посредством `pCmdUI` для обновления пользовательского интерфейса.  
  
##  <a name="recalclayout"></a>CFrameWnd::RecalcLayout  
 Вызывается платформой, когда стандартные панели элементов управления включаются или выключаются или при изменении размера окна фрейма.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bNotify`  
 Определяет, получает ли активного окна на месте для окна фрейма уведомления об изменении макета. Если **TRUE**, этот элемент является извещения; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция-член вызывает `CWnd` функции-члена `RepositionBars` для изменения положения всех панелей элементов управления в кадре, а также как основного окна клиента (обычно `CView` или **MDICLIENT**).  
  
 Переопределите эту функцию-член для управления внешний вид и поведение элементов управления после изменения макета окна фрейма. Например вызовите его при выключать панелей элементов управления или добавьте другую панель элементов управления.  
  
##  <a name="rectdefault"></a>CFrameWnd::rectDefault  
 Передать этот статический `CRect` как параметр при создании окна, чтобы разрешить операционной системе Windows выберите исходный размер и положение окна.  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="savebarstate"></a>CFrameWnd::SaveBarState  
 Эта функция используется для хранения информации о каждую панель элементов управления, принадлежащих фрейм окна.  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProfileName`  
 Имя раздела в файле инициализации или ключ в реестре Windows, где хранятся сведения о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Эти сведения могут быть прочитаны из файла инициализации с помощью [LoadBarState](#loadbarstate). Данные, хранящиеся включает видимость Ориентация по горизонтали и вертикали, закрепление, состояние и положение панели управления.  
  
##  <a name="setactivepreviewview"></a>CFrameWnd::SetActivePreviewView  
 Обозначает указанное представление, необходимо активное представление для расширенного просмотра.  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>Параметры  
 `pViewNew`  
 Указатель на представление, чтобы активировать.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setactiveview"></a>CFrameWnd::SetActiveView  
 Вызовите эту функцию-член для задания активное представление.  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *pViewNew*  
 Задает указатель [CView](../../mfc/reference/cview-class.md) объекта, или **NULL** для нет активное представление.  
  
 `bNotify`  
 Указывает, является ли представление для получения уведомлений об активации. Если **TRUE**, `OnActivateView` вызывается для нового представления; Если **FALSE**, это не так.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию автоматически при перемещении пользователем фокуса на представление в фрейме окна. Можно явно вызывать `SetActiveView` для изменения фокуса в указанном представлении.  
  
##  <a name="setdockstate"></a>CFrameWnd::SetDockState  
 Вызовите эту функцию-член для применения сведений о состоянии, хранящихся в `CDockState` объект для панелей элементов управления в область окна.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Параметры  
 `state`  
 Сохраненное состояние касаться панелей элементов управления в область окна.  
  
### <a name="remarks"></a>Примечания  
 Чтобы восстановить предыдущее состояние панелей элементов управления, можно загрузить сохраненное состояние с `CDockState::LoadState` или `Serialize`, затем с помощью `SetDockState` должны касаться панелей элементов управления в область окна. Предыдущее состояние хранится в `CDockState` объекта с`GetDockState`  
  
##  <a name="setmenubarstate"></a>CFrameWnd::SetMenuBarState  
 Задает состояние отображения меню в текущем приложении MFC для скрытого или отображается.  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nState`|Указывает, следует ли отображать или скрывать меню. `nState` Параметр может иметь следующие значения:<br /><br /> -AFX_MBS_VISIBLE (0x01) — отображает меню, если он является скрытым, но имеет смысл, если она отображается.<br />-AFX_MBS_HIDDEN (0x02) — скрывает меню, если она видна, но имеет смысл, если он скрыт.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод успешного изменения состояния меню; в противном случае `false`.  
  
### <a name="remarks"></a>Примечания  
 Если возникает ошибка времени выполнения, этот метод утверждения в режиме отладки и вызывает исключения, производные от [CException](../../mfc/reference/cexception-class.md) класса.  
  
##  <a name="setmenubarvisibility"></a>CFrameWnd::SetMenuBarVisibility  
 Задает поведение по умолчанию меню в текущем приложении MFC, чтобы быть видимым или скрытым.  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nStyle`|Указывает ли меню по умолчанию скрыты, или является видимым и имеет фокус. `nStyle` Параметр может иметь следующие значения:<br /><br /> -AFX_MBV_KEEPVISIBLE (0X01) —<br />     Меню отображается все время и по умолчанию не имеет фокус.<br />-AFX_MBV_DISPLAYONFOCUS (0X02) —<br />     Меню по умолчанию скрыто. Если меню скрыто, нажмите клавишу ALT, чтобы отобразить меню и делает его активным. Если меню отображается, нажмите клавишу ALT или ESC для скрытия меню.<br />-AFX_MBV_ DISPLAYONFOCUS (0X02) | AFX_MBV_DISPLAYONF10 (0X04)<br />     (битовую комбинацию (OR)) — меню по умолчанию скрыто. Если меню скрыто, нажмите клавишу F10, чтобы отобразить меню и делает его активным. Если меню отображается, нажмите клавишу F10, чтобы переключать фокус и отключение меню. Меню отображается до нажатия клавиши ALT или ESC, чтобы скрыть их.|  
  
### <a name="remarks"></a>Примечания  
 Если значение `nStyle` недопустимый параметр, этот метод проверочные утверждения в режиме отладки и вызывает [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) в режиме выпуска. В случае другие ошибки времени выполнения, этот метод утверждения в режиме отладки и вызывает исключения, производные от [CException](../../mfc/reference/cexception-class.md) класса.  
  
 Этот метод влияет на состояние меню в приложениях, разработанных для [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] и более поздних версий.  
  
##  <a name="setmessagetext"></a>CFrameWnd::SetMessageText  
 Вызывайте эту функцию для размещения строки на панели строки состояния с идентификатором 0.  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Указывает на строку, должен располагаться в строке состояния.  
  
 `nID`  
 Идентификатор строкового ресурса строки должен располагаться в строке состояния.  
  
### <a name="remarks"></a>Примечания  
 Обычно это крайний левый и длинная, панели строки состояния.  
  
##  <a name="setprogressbarposition"></a>CFrameWnd::SetProgressBarPosition  
 Задает текущую позицию индикатора Windows 7, отображаются на панели задач.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Параметры  
 `nProgressPos`  
 Задает расположение для установки. Он должен быть в пределах диапазона, заданные `SetProgressBarRange`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setprogressbarrange"></a>CFrameWnd::SetProgressBarRange  
 Задание диапазона для индикатора хода выполнения Windows 7, отображаются на панели задач.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Параметры  
 `nRangeMin`  
 Минимальное значение.  
  
 `nRangeMax`  
 Максимальное значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setprogressbarstate"></a>CFrameWnd::SetProgressBarState  
 Задает тип и состояние индикатора, отображаемый на кнопке панели задач.  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `tbpFlags`  
 Флаги, управляющие текущее состояние кнопки «выполняется». Укажите только один из следующих флагов, так как все состояния являются взаимоисключающими: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settaskbaroverlayicon"></a>CFrameWnd::SetTaskbarOverlayIcon  
 Перегружен. Применяет наложенной на кнопку панели задач для указания состояния приложения или для уведомления пользователя.  
  
```  
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,  
    LPCTSTR lpcszDescr);

 
BOOL SetTaskbarOverlayIcon(
    HICON hIcon,  
    LPCTSTR lpcszDescr);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDResource`  
 Указывает идентификатор ресурса значка для использования в качестве наложения. Описание `hIcon` подробные сведения.  
  
 `lpcszDescr`  
 Указатель строку, которая содержит версию замещающий текст информации, представленной в оверлей специальных возможностей.  
  
 `hIcon`  
 Дескриптор значка для использования в качестве наложения. Это должна быть мелкого значка, измерение 16 x 16 пикселей в 96 точек на дюйм (dpi). Если значок наложения уже применен к кнопки панели задач, что существующие наложения заменяется. Это значение может быть равно `NULL`. Как `NULL` значение, которое обрабатывается зависит от того, представляет ли кнопки панели задач одного окна или группы windows. Отвечает вызывающего приложения, чтобы освободить `hIcon` когда он больше не нужен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; `FALSE` Если версия ОС меньше, чем Windows 7 или если возникает ошибка заданию значка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settitle"></a>CFrameWnd::SetTitle  
 Задает заголовок окна объекта.  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszTitle`  
 Указатель на строку символов, содержащая заголовок окна объекта.  
  
##  <a name="showcontrolbar"></a>CFrameWnd::ShowControlBar  
 Вызовите эту функцию-член для отображения или скрытия панели управления.  
  
```  
void ShowControlBar(
    CControlBar* pBar,  
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>Параметры  
 `pBar`  
 Указатель на панели управления, чтобы быть отображены или скрыты.  
  
 `bShow`  
 Если **TRUE**, указывает, что на панели управления для отображения. Если **FALSE**, указывает, что на панели управления является скрытым.  
  
 *bDelay*  
 Если **TRUE**, задержка отображаются на панели управления. Если **FALSE**, Показать панель элементов управления немедленно.  
  
##  <a name="showownedwindows"></a>CFrameWnd::ShowOwnedWindows  
 Вызовите эту функцию-член для отображения всех окон, которые являются потомками `CFrameWnd` объекта.  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 `bShow`  
 Указывает, будут ли собственные окна отображаться или скрываться.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd-класс](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd-класс](../../mfc/reference/cmdichildwnd-class.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [Структура CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)

