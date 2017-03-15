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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a8df28ed10208973832476b68140594c206bc22b
ms.lasthandoff: 02/24/2017

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
|[CFrameWnd::BeginModalState](#beginmodalstate)|Задает модальные окна фрейма.|  
|[CFrameWnd::Create](#create)|Вызов для создания и инициализации Windows окно, связанное с `CFrameWnd` объекта.|  
|[CFrameWnd::CreateView](#createview)|Создает представление внутри кадра, который не является производным от `CView`.|  
|[CFrameWnd::DockControlBar](#dockcontrolbar)|Закрепляет панель элементов управления.|  
|[CFrameWnd::EnableDocking](#enabledocking)|Позволяет закреплять панели элементов управления.|  
|[CFrameWnd::EndModalState](#endmodalstate)|Завершает модальное состояние окна фрейма. Включает все окна отключено по `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Отображается панель элементов управления.|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Возвращает активный **CDocument** объекта.|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Возвращает активный `CFrameWnd` объекта.|  
|[CFrameWnd::GetActiveView](#getactiveview)|Возвращает активный `CView` объекта.|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|Извлекает панели управления.|  
|[CFrameWnd::GetDockState](#getdockstate)|Получает состояние закрепления окна фрейма.|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Получает состояние отображения меню в текущем приложении MFC.|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Указывает, является ли текущее приложение MFC в меню по умолчанию видимым или скрытым.|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|Возвращает указатель строки принадлежащих фрейме окна состояния.|  
|[CFrameWnd::GetMessageString](#getmessagestring)|Получает сообщение, соответствующее идентификатор команды.|  
|[CFrameWnd::GetTitle](#gettitle)|Извлекает заголовок панели связанных элементов управления.|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Вызывает `OnInitialUpdate` относящихся ко всем представлениям в окне фрейма для вызова функции-члена.|  
|[CFrameWnd::InModalState](#inmodalstate)|Возвращает значение, указывающее, является ли рамка окна в модальном состоянии.|  
|[CFrameWnd::IsTracking](#istracking)|Определяет, если разделитель перемещается в данный момент.|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Вызов для загрузки таблицы сочетаний клавиш.|  
|[CFrameWnd::LoadBarState](#loadbarstate)|Вызов, чтобы восстановить параметры панели управления.|  
|[CFrameWnd::LoadFrame](#loadframe)|Вызов для динамического создания фрейма окна из сведений о ресурсах.|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Согласовывает граница места в окне фрейма.|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|Вызывается, когда действие выполняется по строке указанным элементом управления.|  
|[CFrameWnd::OnContextHelp](#oncontexthelp)|Обрабатывает клавиши SHIFT + F1 справка для элементов на месте.|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Задает фрейма главного окна приложения, в и из режима предварительного просмотра печати.|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|Вызывается инфраструктурой при обновлении связанным меню.|  
|[CFrameWnd::RecalcLayout](#recalclayout)|Перемещает на панелях управления `CFrameWnd` объекта.|  
|[CFrameWnd::SaveBarState](#savebarstate)|Вызов сохранить параметры панели управления.|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Обозначает указанное представление для активного представления для расширенного просмотра.|  
|[CFrameWnd::SetActiveView](#setactiveview)|Задает активный `CView` объекта.|  
|[CFrameWnd::SetDockState](#setdockstate)|Вызов, чтобы закрепить окно в главном окне.|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Задает состояние отображения меню в текущем приложении MFC для скрытых или отображаемых.|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Задает поведение по умолчанию меню в текущем приложении MFC, чтобы быть видимым или скрытым.|  
|[CFrameWnd::SetMessageText](#setmessagetext)|Задает текст строки состояния standard.|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Задает текущую позицию для Windows 7 индикатор выполнения отображается на панели задач.|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Задает диапазон для Windows 7 индикатор выполнения отображается на панели задач.|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Задает тип и состояние индикатора хода выполнения, отображаемый на кнопке панели задач.|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Перегружен. Применяет наложение кнопки на панели задач для обозначения состояния приложений или уведомления пользователя.|  
|[CFrameWnd::SetTitle](#settitle)|Задает заголовок панели связанных элементов управления.|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Вызов для отображения панели управления.|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Показывает все окна, которые являются потомками `CFrameWnd` объекта.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|Создает окно клиента для фрейма.|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Вызывается перед меню в текущем приложении MFC скрыто.|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Вызывается перед отображением меню в текущем приложении MFC.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Элементы управления автоматическое включение и отключение функциональные возможности для элементов меню.|  
|[CFrameWnd::rectDefault](#rectdefault)|Передать этот статический `CRect` как параметр при создании `CFrameWnd` объекта, чтобы разрешить операционной системе Windows выберите исходный размер и положение окна.|  
  
## <a name="remarks"></a>Примечания  
 Для создания полезных окно приложения, создайте класс, производный от `CFrameWnd`. Добавьте переменные-члены для производного класса для хранения данных, относящихся к конкретному приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.  
  
 Для создания окна фрейма тремя способами:  
  
-   Непосредственно создавать его с помощью [создать](#create).  
  
-   Непосредственно создавать его с помощью [LoadFrame](#loadframe).  
  
-   Косвенно создайте его с помощью шаблона документа.  
  
 Перед вызовом метода либо **создать** или `LoadFrame`, необходимо создать объект фреймового окна в куче C++ с помощью **новый** оператор. Перед вызовом метода **создать**, также можно зарегистрировать класс окна с [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) глобальные функции для установки значок и класс стили рамки.  
  
 Используйте **создать** для передачи параметров создания фрейма как интерпретации аргументов функции-члена.  
  
 `LoadFrame`требуется меньшее число аргументов, чем **создать**и вместо этого получает большую часть значений по умолчанию из ресурсов, включая заголовок, значок, таблицы сочетаний клавиш и меню фрейма. Должны быть доступны `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, **IDR_MAINFRAME**).  
  
 Если `CFrameWnd` объект содержит представления и документы, они создаются неявно платформой вместо программистом. `CDocTemplate` Объект организует Создание рамки, создавать представления, содержащего и подключение представлений для соответствующих документов. Параметры `CDocTemplate` конструктор указывать `CRuntimeClass` трех классов участвующих (документа, рамки и представления). Объект `CRuntimeClass` объект используется платформой для динамического создания новых кадров, задаваемых пользователем (например, с помощью команды Создать файл или несколько окно Новая команда интерфейса (MDI) документа).  
  
 Окна фрейма класс, производный от `CFrameWnd` должны быть объявлены с `DECLARE_DYNCREATE` в порядке для указанных выше `RUNTIME_CLASS` механизм для правильной работы.  
  
 Объект `CFrameWnd` содержит реализации по умолчанию для выполнения следующих функций главного окна в обычном приложении для Windows:  
  
-   Значение типа `CFrameWnd` фрейм окна данные о текущей активной представление, которое не зависит от активного окна Windows или текущий фокус ввода. При повторной активации кадра активное представление получает уведомления путем вызова `CView::OnActivateView`.  
  
-   Команды сообщений и многие общие сообщения кадра уведомлений, включая те обрабатываются `OnSetFocus`, `OnHScroll`, и `OnVScroll` функции `CWnd`, полномочия с `CFrameWnd` фрейм окна для активного представления.  
  
-   В настоящее время активного представления (или текущего активного MDI дочернем фрейме окна в случае фрейма MDI) можно определить заголовок окна фрейма. Эту функцию можно отключить, отключив **FWS_ADDTOTITLE** бит стиля окна фрейма.  
  
-   Значение типа `CFrameWnd` фрейм окна управляет размещением панелей элементов управления, представлений и других дочерних окон в клиентской области окна фрейма. Рамка окна также делает времени простоя обновления инструментов и другие кнопки панели элементов управления. Значение типа `CFrameWnd` фрейм окна также имеет реализации по умолчанию команд для переключения Включение и отключение панели инструментов и строки состояния.  
  
-   Значение типа `CFrameWnd` фрейм окна управляет главного меню. Когда появится всплывающее меню, окна фрейма использует **UPDATE_COMMAND_UI** механизм, чтобы определить, какие элементы меню должны быть включены, отключены или проверки. Когда пользователь выбирает пункт меню, окна фрейма обновляет строку сообщения для этой команды в строке состояния.  
  
-   Значение типа `CFrameWnd` фрейм окна имеет таблицу необязательный сочетаний клавиш, которая автоматически преобразует сочетания клавиш.  
  
-   Объект `CFrameWnd` окно имеет идентификатор справки необязательный набор с `LoadFrame` , используемый для контекстной справки. Рамка окна является основной orchestrator полумодальные состояний, таких как контекстной справки (SHIFT + F1) и режима предварительного просмотра печати.  
  
-   Значение типа `CFrameWnd` фрейм окна откроется файл из диспетчера файлов перетаскивать на фрейме окна. Если расширение файла, зарегистрировано и связанные с приложением, окна фрейма реагирует на динамических данных exchange (DDE) откройте запрос, который возникает при открытии файла данных в диспетчере файлов или **ShellExecute** вызывается функция Windows.  
  
-   Если окно фрейма главного окна приложения (то есть, `CWinThread::m_pMainWnd`), когда пользователь закрывает приложение, фрейме окна с приглашением сохранить все измененные документы (для `OnClose` и `OnQueryEndSession`).  
  
-   Если окно фрейма главного окна приложения, фрейме окна является контекст для выполнения WinHelp. При закрытии окна фрейма завершит работу WINHELP. Exe-ФАЙЛ, если он был запущен для справки для этого приложения.  
  
 Не используйте C++ **удаление** оператор уничтожении окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow` . `CFrameWnd` Реализацию `PostNcDestroy` приведет к удалению объекта C++ при уничтожении окна. Когда пользователь закрывает окно области по умолчанию `OnClose` обработчик вызовет `DestroyWindow`.  
  
 Дополнительные сведения о `CFrameWnd`, в разделе [окна фрейма](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-nameactivateframea--cframewndactivateframe"></a><a name="activateframe"></a>CFrameWnd::ActivateFrame  
 Вызовите эту функцию-член для активации и восстанавливает рамку окна, чтобы было видимым и доступным для пользователя.  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>Параметры  
 `nCmdShow`  
 Задает параметр для передачи [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). По умолчанию кадр показано и правильно восстановить.  
  
### <a name="remarks"></a>Примечания  
 Обычно эта функция-член вызывается после события без пользовательского интерфейса, такие как DDE, OLE или другие события, которое может показывать пользователю окна фрейма или его содержимое.  
  
 Реализация по умолчанию активирует кадр и переводит ее в верхней части Z-порядок и, при необходимости, выполняет те же действия для фрейма главного окна приложения.  
  
 Переопределите эту функцию-член для изменения способа активации кадра. Например вы можете принудительно дочерних окон MDI и развернуть. Добавить соответствующие функциональные возможности, а затем вызовите версию базового класса с явным `nCmdShow`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#1;](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="a-namebeginmodalstatea--cframewndbeginmodalstate"></a><a name="beginmodalstate"></a>CFrameWnd::BeginModalState  
 Данная функция-член вызывается для преобразования окна фрейма в модальное.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="a-namecframewnda--cframewndcframewnd"></a><a name="cframewnd"></a>CFrameWnd::CFrameWnd  
 Создает `CFrameWnd` объекта, но не создает окно видимой области.  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов **создать** создание видимого окна.  
  
##  <a name="a-namecreatea--cframewndcreate"></a><a name="create"></a>CFrameWnd::Create  
 Вызов для создания и инициализации Windows окно, связанное с `CFrameWnd` объекта.  
  
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
 Указывает строку символом null, что имена классов Windows. Имя класса может быть любое имя, зарегистрированное в `AfxRegisterWndClass` глобальной функции или **RegisterClass** функции Windows. Если **NULL**, использует предопределенные по умолчанию `CFrameWnd` атрибуты.  
  
 `lpszWindowName`  
 Указывает символ нулем строка, представляющая имя окна. Использовать как текст строки заголовка.  
  
 `dwStyle`  
 Задает окно [стиль](../../mfc/reference/window-styles.md) атрибуты. Включить **FWS_ADDTOTITLE** стиля, если требуется, чтобы в заголовке автоматически отображать имя документа, представленного в окне.  
  
 `rect`  
 Задает размер и положение окна. `rectDefault` Значение позволяет Windows указать размер и положение нового окна.  
  
 `pParentWnd`  
 Указывает родительского окна фрейма окна. Этот параметр должен быть **NULL** для окон верхнего уровня кадра.  
  
 *lpszMenuName*  
 Определяет имя ресурса для использования с окном меню. Используйте **MAKEINTRESOURCE** Если целочисленный идентификатор вместо строки меню. Этот параметр может иметь **NULL**.  
  
 `dwExStyle`  
 Задает окно расширенных [стиль](../../mfc/reference/extended-window-styles.md) атрибуты.  
  
 `pContext`  
 Задает указатель [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. Этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создать `CFrameWnd` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CFrameWnd` , а затем вызвать **создать**, который создает фрейм окна Windows и присоединяет его к `CFrameWnd` объекта. **Создание** инициализирует окна имя класса и имя окна и регистрирует значения по умолчанию для его стиль, родительский и связанным меню.  
  
 Используйте `LoadFrame` вместо **создать** для загрузки из ресурсов, вместо указания аргументов фрейме окна.  
  
##  <a name="a-namecreateviewa--cframewndcreateview"></a><a name="createview"></a>CFrameWnd::CreateView  
 Вызов `CreateView` для создания представления в рамке.  
  
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
 Указатель на `CWnd` объекта в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член для создания «представления», не используйте `CView`-производным внутри рамки. После вызова метода `CreateView`, необходимо вручную установить представление активной и сделать его видимым, эти задачи не выполняются автоматически по `CreateView`.  
  
##  <a name="a-namedockcontrolbara--cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a>CFrameWnd::DockControlBar  
 В результате закреплено в фрейме окна панели управления.  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pBar`  
 Указывает на панели управления, чтобы закрепить.  
  
 `nDockBarID`  
 Определяет, какие стороны окна фрейма, рассмотрите возможность закрепления. Это может быть 0, или одно или несколько из следующих:  
  
- `AFX_IDW_DOCKBAR_TOP`Закрепить в верхней части окна фрейма.  
  
- **AFX_IDW_DOCKBAR_BOTTOM** закрепить в нижней части окна фрейма.  
  
- `AFX_IDW_DOCKBAR_LEFT`Закрепить в левой части окна фрейма.  
  
- `AFX_IDW_DOCKBAR_RIGHT`Закрепить в правой части окна фрейма.  
  
 Если значение равно 0, на панели управления можно закрепить с любой стороны включено закрепление в фрейме окна назначения.  
  
 `lpRect`  
 Определяет, в экранных координатах, где панели управления будет закреплено в неклиентской области окна фрейма назначения.  
  
### <a name="remarks"></a>Примечания  
 На панели управления будет прикреплен к одной из сторон окна фрейма, заданные в вызовах как [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) и [CFrameWnd::EnableDocking](#enabledocking). Определяется стороне выбран `nDockBarID`.  
  
##  <a name="a-nameenabledockinga--cframewndenabledocking"></a><a name="enabledocking"></a>CFrameWnd::EnableDocking  
 Эта функция вызывается для включения закрепляемых панелей в окне фрейма.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwDockStyle`  
 Указывает, какие стороны окна фрейма может служить закрепление сайтов для панелей элементов управления. Это может быть один или несколько из следующих:  
  
- `CBRS_ALIGN_TOP`Позволяет закрепления в верхней части клиентской области.  
  
- `CBRS_ALIGN_BOTTOM`Позволяет закрепления в нижней части области клиента.  
  
- `CBRS_ALIGN_LEFT`Позволяет Закрепление левого края клиентской области.  
  
- `CBRS_ALIGN_RIGHT`Позволяет закрепления в правую часть клиентской области.  
  
- `CBRS_ALIGN_ANY`Позволяет в любой части клиентской области закрепления.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию панели элементов управления будет прикреплен к стороне окна фрейма в следующем порядке: сверху, снизу, слева, справа.  
  
### <a name="example"></a>Пример  
  В примере показано [CToolBar::Create](../../mfc/reference/ctoolbar-class.md#create).  
  
##  <a name="a-nameendmodalstatea--cframewndendmodalstate"></a><a name="endmodalstate"></a>CFrameWnd::EndModalState  
 Данная функция-член вызывается для изменения состояния окна с модального на немодальное.  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>Примечания  
 `EndModalState`включает все окна отключено по [BeginModalState](#beginmodalstate).  
  
##  <a name="a-namefloatcontrolbara--cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a>CFrameWnd::FloatControlBar  
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
 Расположение, в экранных координатах, где будут размещаться левом верхнем углу панели управления.  
  
 `dwStyle`  
 Указывает, следует ли выравнивать панели управления по горизонтали или по вертикали в пределах его новый фрейм окна. Это может быть одним из следующих:  
  
- `CBRS_ALIGN_TOP`Изменяет ориентацию панели управления по вертикали.  
  
- `CBRS_ALIGN_BOTTOM`Изменяет ориентацию панели управления по вертикали.  
  
- `CBRS_ALIGN_LEFT`Изменяет ориентацию панели управления по горизонтали.  
  
- `CBRS_ALIGN_RIGHT`Изменяет ориентацию панели управления по горизонтали.  
  
 Если стили передаются указания вертикальной или горизонтальной ориентации, панели инструментов будет ориентирована по горизонтали.  
  
### <a name="remarks"></a>Примечания  
 Как правило это делается при запуске приложения при программа восстанавливает параметры из предыдущего выполнения.  
  
 Эта функция вызывается платформой, когда пользователь вызывает операцию перетаскивания, выпустив левой кнопки мыши при перетаскивании в расположении, не доступен для закрепления панели управления.  
  
##  <a name="a-namegetactivedocumenta--cframewndgetactivedocument"></a><a name="getactivedocument"></a>CFrameWnd::GetActiveDocument  
 Вызовите эту функцию-член для получения указателя на текущий **CDocument** присоединен к текущее активное представление.  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий [CDocument](../../mfc/reference/cdocument-class.md). Если текущий документ не возвращает **NULL**.  
  
##  <a name="a-namegetactiveframea--cframewndgetactiveframe"></a><a name="getactiveframe"></a>CFrameWnd::GetActiveFrame  
 Вызовите эту функцию-член для получения указателя к активному дочернего окна многодокументного интерфейса (MDI) окне фрейма MDI.  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активную дочернюю MDI. Если приложения SDI-приложения, или окно области MDI нет активного документа неявный **это** указателя будет возвращено.  
  
### <a name="remarks"></a>Примечания  
 Если нет активной дочерней MDI-приложения или приложения является однооконный интерфейс (SDI), неявный **это** возвращается указатель.  
  
##  <a name="a-namegetactiveviewa--cframewndgetactiveview"></a><a name="getactiveview"></a>CFrameWnd::GetActiveView  
 Вызовите эту функцию-член может получить указатель на активное представление (если таковые имеются), прикрепленных к окну кадров ( `CFrameWnd`).  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий [CView](../../mfc/reference/cview-class.md). Если текущее представление не возвращает **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает **NULL** при вызове для фрейма главного окна MDI ( `CMDIFrameWnd`). В приложении MDI фрейма главного окна MDI нет представления, связанные с ним. Вместо этого каждого отдельного дочернего окна ( `CMDIChildWnd`) имеет один или несколько связанных с ним представлений. Активное представление в приложении MDI можно получить, необходимо сначала найти активную дочернюю MDI и затем поиск активное представление для этого дочернего окна. Активную дочернюю MDI можно найти путем вызова функции `MDIGetActive` или **GetActiveFrame** как показано ниже:  
  
 [!code-cpp[NVC_MFCWindowing&#2;](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="a-namegetcontrolbara--cframewndgetcontrolbar"></a><a name="getcontrolbar"></a>CFrameWnd::GetControlBar  
 Вызов `GetControlBar` для получения доступа к панели управления, связанный с идентификатором.  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификационный номер панели элементов управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панели управления, связанный с идентификатором.  
  
### <a name="remarks"></a>Примечания  
 `nID` Параметр ссылается на уникальный идентификатор, передаваемый **создать** метод панели элементов управления. Дополнительные сведения о панели элементов управления, см. в разделе [панелей элементов управления](../../mfc/control-bars.md).  
  
 `GetControlBar`вернет панели управления, даже если он является перемещаемой и таким образом не является в настоящее время дочернего окна фрейма.  
  
##  <a name="a-namegetdockstatea--cframewndgetdockstate"></a><a name="getdockstate"></a>CFrameWnd::GetDockState  
 Вызовите эту функцию-член для хранения сведений о фрейме окна панели элементов управления в состоянии `CDockState` объекта.  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `state`  
 Содержит текущее состояние окна фрейма панелей элементов управления при возврате.  
  
### <a name="remarks"></a>Примечания  
 После этого можно написать содержимое `CDockState` в хранилище с помощью `CDockState::SaveState` или `Serialize`. Если позже вы хотите восстановить предыдущее состояние панели элементов управления, загрузить состояние с `CDockState::LoadState` или `Serialize`, затем вызовите `SetDockState` для применения к панели элементов управления окна фрейма в предыдущее состояние.  
  
##  <a name="a-namegetmenubarstatea--cframewndgetmenubarstate"></a><a name="getmenubarstate"></a>CFrameWnd::GetMenuBarState  
 Получает состояние отображения меню в текущем приложении MFC.  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение может иметь следующие значения:  
  
-   AFX_MBS_VISIBLE (0x01) — меню является видимым.  
  
-   AFX_MBS_HIDDEN (0x02) — меню скрыто.  
  
### <a name="remarks"></a>Примечания  
 Если возникает ошибка во время выполнения, этот метод утверждения в режиме отладки и вызывает исключение, производный от [CException](../../mfc/reference/cexception-class.md) класса.  
  
##  <a name="a-namegetmenubarvisibilitya--cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBarVisibility  
 Указывает, является ли состояние по умолчанию меню в текущем приложении MFC скрытым или видимым.  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает одно из следующих значений:  
  
-   AFX_MBV_KEEPVISIBLE (0x01) — меню отображается вообще времени и по умолчанию не имеет фокус.  
  
-   AFX_MBV_DISPLAYONFOCUS (0x02) — меню по умолчанию скрыт. Если меню скрыта, нажмите клавишу ALT, чтобы отобразить меню и делает его активным. Если меню отображается, нажмите клавишу ALT или ESC, чтобы скрыть его.  
  
-   AFX_MBV_ DISPLAYONFOCUS (0X02) | AFX_MBV_DISPLAYONF10 (0x04) (побитовое сочетание (или)) - меню по умолчанию скрыт. Если меню скрыта, нажмите клавишу F10, чтобы отобразить меню и делает его активным. Если меню отображается, нажмите клавишу F10, чтобы переключить фокус на или меню. Меню отображается до нажатия клавиши ALT или ESC, чтобы скрыть его.  
  
### <a name="remarks"></a>Примечания  
 Если возникает ошибка во время выполнения, этот метод утверждения в режиме отладки и вызывает исключение, производный от [CException](../../mfc/reference/cexception-class.md) класса.  
  
##  <a name="a-namegetmessagebara--cframewndgetmessagebar"></a><a name="getmessagebar"></a>CFrameWnd::GetMessageBar  
 Вызовите эту функцию-член для получения указателя на строку состояния.  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель строки состояния окна.  
  
##  <a name="a-namegetmessagestringa--cframewndgetmessagestring"></a><a name="getmessagestring"></a>CFrameWnd::GetMessageString  
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
 `CString`Объект, в котором следует разместить сообщение.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию просто загружает строки, заданной параметром `nID` из файла ресурсов. Эта функция вызывается платформой, когда строку сообщения в строке состояния необходимо обновить.  
  
##  <a name="a-namegettitlea--cframewndgettitle"></a><a name="gettitle"></a>CFrameWnd::GetTitle  
 Получает заголовок окна объекта.  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий текущий заголовок окна объекта.  
  
##  <a name="a-nameinitialupdateframea--cframewndinitialupdateframe"></a><a name="initialupdateframe"></a>CFrameWnd::InitialUpdateFrame  
 Вызов **IntitialUpdateFrame** после создания новый кадр с **создать**.  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Указывает на документ, с которым связана фрейме окна. Может быть **NULL**.  
  
 `bMakeVisible`  
 Если **TRUE**, указывает, что кадр должен стать видимым и active. Если **FALSE**, нет потомков становится видимым.  
  
### <a name="remarks"></a>Примечания  
 В результате чего все представления, фрейм окна, чтобы получить их `OnInitialUpdate` вызовов.  
  
 Кроме того Если существует не была ранее активное представление, основного представления окна фрейма делается активным. Основное представление — это представление с ИД дочернего объекта **AFX_IDW_PANE_FIRST**. Наконец, будет виден в фрейме окна Если `bMakeVisible` имеет ненулевое значение. Если `bMakeVisible` составляет 0, что текущим местоположением и видимое состояние окна фрейма останутся без изменений. Эта функция вызывается при использовании платформы реализации новых файлов и открытие файла необязательно.  
  
##  <a name="a-nameinmodalstatea--cframewndinmodalstate"></a><a name="inmodalstate"></a>CFrameWnd::InModalState  
 Вызовите эту функцию-член для проверки модальное или немодальное окно.  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если Да; в противном случае — 0.  
  
##  <a name="a-nameistrackinga--cframewndistracking"></a><a name="istracking"></a>CFrameWnd::IsTracking  
 Вызовите эту функцию-член для определения, если выполняется перемещение полосы разделения в окне.  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция разделитель выполняется; в противном случае — 0.  
  
##  <a name="a-nameloadacceltablea--cframewndloadacceltable"></a><a name="loadacceltable"></a>CFrameWnd::LoadAccelTable  
 Вызов для загрузки таблицы сочетание клавиш.  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszResourceName`  
 Определяет имя ресурса сочетаний клавиш. Используйте **MAKEINTRESOURCE** Если ресурс определяется целочисленный идентификатор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в таблице сочетаний клавиш был успешно загружен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Только одна таблица может загружаться одновременно.  
  
 Таблицы сочетаний клавиш, загруженные из ресурсы освобождаются автоматически при завершении работы приложения.  
  
 При вызове метода `LoadFrame` для создания окна фрейма, платформа загружает таблицу сочетаний клавиш, а также ресурсов меню и значок, а затем необязателен в последующем вызове функции-члена.  
  
##  <a name="a-nameloadbarstatea--cframewndloadbarstate"></a><a name="loadbarstate"></a>CFrameWnd::LoadBarState  
 Эта функция вызывается для восстановления параметров каждого панели элементов управления в фрейме окна.  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProfileName`  
 Имя раздела в файле настройки (INI) или ключ в реестре Windows, где хранится информация о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Восстановление включает видимость, горизонтальной или вертикальной ориентацией, состояние стыковки и положение панели элементов управления.  
  
 Параметры, которые требуется восстановить необходимо записать в реестр перед вызовом метода `LoadBarState`. Записывать данные в реестре, вызвав [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Записать данные INI-файл, вызвав [SaveBarState](#savebarstate).  
  
##  <a name="a-nameloadframea--cframewndloadframe"></a><a name="loadframe"></a>CFrameWnd::LoadFrame  
 Вызов для динамического создания фрейма окна из сведений о ресурсах.  
  
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
 Рамки [стиль](../../mfc/reference/window-styles.md). Включить **FWS_ADDTOTITLE** стиля, если требуется, чтобы в заголовке автоматически отображать имя документа, представленного в окне.  
  
 `pParentWnd`  
 Указатель родительского фрейма.  
  
 `pContext`  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. Этот параметр может иметь **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Создать `CFrameWnd` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CFrameWnd` , а затем вызвать `LoadFrame`, который загружает окна Windows и связанных ресурсов и присоединяет фрейме окна для `CFrameWnd` объекта. `nIDResource` Указывает меню, в таблице сочетаний клавиш, значок и строковый ресурс заголовок окна фрейма.  
  
 Используйте **создать** функции-члена вместо `LoadFrame` , если требуется указать все параметры создания окна фрейма.  
  
 Платформа вызывает функцию `LoadFrame` при создании окна фрейма, с помощью объекта шаблона документа.  
  
 Инфраструктура использует `pContext` для указания объектов подключения в окне фрейма, включая все содержащиеся объекты представлений. Можно задать `pContext` аргумент **NULL** при вызове `LoadFrame`.  
  
##  <a name="a-namembautomenuenablea--cframewndmbautomenuenable"></a><a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable  
 При включении этого элемента данных (по умолчанию), элементов меню, не имеют `ON_UPDATE_COMMAND_UI` или `ON_COMMAND` обработчики автоматически отключаются, когда пользователь запрашивает по меню.  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>Примечания  
 Пункты меню, которые имеют `ON_COMMAND` обработчик, но не `ON_UPDATE_COMMAND_UI` обработчика будут включены автоматически.  
  
 Если значение этого элемента данных, пункты меню автоматически включаются таким же образом, что включены кнопки панели инструментов.  
  
> [!NOTE]
> `m_bAutoMenuEnable`не оказывает влияния на пункты меню верхнего уровня.  
  
 Этот член данных упрощает реализацию дополнительные команды на основе текущего выделения и уменьшает потребность в написании `ON_UPDATE_COMMAND_UI` обработчики для включения и отключения пунктов меню.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#3;](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="a-namenegotiateborderspacea--cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a>CFrameWnd::NegotiateBorderSpace  
 Вызовите эту функцию-член для согласования граница места в окне фрейма во время активации inplace OLE.  
  
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
 Указатель на [RECT](../../mfc/reference/rect-structure1.md) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) , указывающий координаты границы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является **CFrameWnd** реализации согласования пробел границы OLE.  
  
##  <a name="a-nameonbarchecka--cframewndonbarcheck"></a><a name="onbarcheck"></a>CFrameWnd::OnBarCheck  
 Вызывается, когда действие выполняется по строке указанным элементом управления.  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления панели показано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если существует панели управления; в противном случае — 0.  
  
##  <a name="a-nameoncontexthelpa--cframewndoncontexthelp"></a><a name="oncontexthelp"></a>CFrameWnd::OnContextHelp  
 Обрабатывает клавиши SHIFT + F1 справка для элементов на месте.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы включить контекстной справки, необходимо добавить  
  
 [!code-cpp[NVC_MFCDocViewSDI №&16;](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 инструкции для вашего `CFrameWnd` класса схемы сообщений, а также добавляет запись в таблицу сочетаний клавиш, обычно клавиши SHIFT + F1, чтобы включить эту функцию-член.  
  
 Если приложение является OLE контейнер, `OnContextHelp` помещает все элементы на месте внутри рамки окна объекта в режим справки. Стрелка и знак вопроса и пользователь может затем наведите указатель мыши и нажмите левую кнопку мыши для выбора диалоговое окно, окно, меню или кнопки. Эта функция-член вызывает функцию Windows `WinHelp` в контексте справки объекта под курсором.  
  
##  <a name="a-nameoncreateclienta--cframewndoncreateclient"></a><a name="oncreateclient"></a>CFrameWnd::OnCreateClient  
 Вызывается средой во время выполнения `OnCreate`.  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Параметры  
 `lpcs`  
 Указатель на Windows [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) структуры *.*  
  
 `pContext`  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры *.*  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Невозможно вызвать эту функцию.  
  
 Реализация по умолчанию эта функция создает `CView` объекта из сведений, предоставленных в `pContext`, если это возможно.  
  
 Переопределить эту функцию для переопределения значений, переданных в `CCreateContext` объекта или изменение создаваемых элементов управления в области главного окна фрейма. `CCreateContext` Можно переопределить элементы описаны в [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) класса.  
  
> [!NOTE]
>  Не заменяйте значения, передаваемые в `CREATESTRUCT` структуру. Они являются только в информационных целях. Если требуется переопределить начальное окно прямоугольника, например, переопределение `CWnd` функции-члена [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).  
  
##  <a name="a-nameonhidemenubara--cframewndonhidemenubar"></a><a name="onhidemenubar"></a>CFrameWnd::OnHideMenuBar  
 Эта функция вызывается, когда система собирается скрыть строку меню в текущем приложении MFC.  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>Примечания  
 Этот обработчик событий позволяет вашему приложению для выполнения пользовательских действий, когда система собирается скрыть меню. Невозможно запретить меню как скрытые, но могут, например, вызывать другие методы для получения стиль меню или состояния.  
  
##  <a name="a-nameonsetpreviewmodea--cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CFrameWnd::OnSetPreviewMode  
 Вызов этой функции-члена переключает окно главного фрейма приложения в режим предварительного просмотра и из него.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Параметры  
 *bPreview*  
 Указывает, следует ли разместить приложение в режиме предварительного просмотра печати. Значение **TRUE** для размещения в режиме предварительного просмотра **FALSE** для выхода из режима предварительного просмотра.  
  
 `pState`  
 Указатель на **CPrintPreviewState** структуры.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию отключает все панели инструментов Стандартная и скрывает главного меню и главное окно клиента. Окна фрейма MDI это превращается в временного окна фрейма SDI.  
  
 Переопределите эту функцию-член для настройки скрытие и отображение панелей элементов управления и других частей рамки окна во время предварительного просмотра. Вызовите реализацию базового класса из внутри переопределенная версия.  
  
##  <a name="a-nameonshowmenubara--cframewndonshowmenubar"></a><a name="onshowmenubar"></a>CFrameWnd::OnShowMenuBar  
 Эта функция вызывается, когда система отображения меню в текущем приложении MFC.  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>Примечания  
 Этот обработчик событий позволяет вашему приложению для выполнения пользовательских действий, когда отобразится меню. Меню не может предотвратить отображение, но могут, например, вызывать другие методы для получения стиль меню или состояния.  
  
##  <a name="a-nameonupdatecontrolbarmenua--cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a>CFrameWnd::OnUpdateControlBarMenu  
 Вызывается инфраструктурой при обновлении связанным меню.  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объект, представляющий меню, которое создается команда обновления. Вызывает обработчик обновление [включить](../../mfc/reference/ccmdui-class.md#enable) функцию-член `CCmdUI` через `pCmdUI` для обновления пользовательского интерфейса.  
  
##  <a name="a-namerecalclayouta--cframewndrecalclayout"></a><a name="recalclayout"></a>CFrameWnd::RecalcLayout  
 Вызывается инфраструктурой при переключении панелей стандартных элементов управления и отключение или при изменении размера окна фрейма.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bNotify`  
 Определяет, получает ли активный элемент на месте для фрейма окна уведомления об изменении макета. Если **TRUE**, элемент оповещений; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция-член вызывает `CWnd` функции-члена `RepositionBars` для изменения положения всех панелей элементов управления в кадре, а также как главное окно клиента (обычно `CView` или **MDICLIENT**).  
  
 Переопределите эту функцию-член для управления, внешний вид и поведение элементов управления после изменения макета окна фрейма. Например назвать ее при выключать панелей элементов управления или добавьте другую панель элементов управления.  
  
##  <a name="a-namerectdefaulta--cframewndrectdefault"></a><a name="rectdefault"></a>CFrameWnd::rectDefault  
 Передать этот статический `CRect` как параметр при создании окна, чтобы разрешить операционной системе Windows выберите исходный размер и положение окна.  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="a-namesavebarstatea--cframewndsavebarstate"></a><a name="savebarstate"></a>CFrameWnd::SaveBarState  
 Эта функция используется для хранения информации о каждой панели элементов управления, принадлежащих фрейме окна.  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProfileName`  
 Имя раздела в файле настройки или ключ в реестре Windows, где хранится информация о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Эта информация может быть считано из файла инициализации с помощью [LoadBarState](#loadbarstate). Сведения, хранящиеся включают видимость горизонтальной или вертикальной ориентации закрепления состояние и положение элемента панели управления.  
  
##  <a name="a-namesetactivepreviewviewa--cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a>CFrameWnd::SetActivePreviewView  
 Обозначает указанное представление для активного представления для расширенного просмотра.  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>Параметры  
 `pViewNew`  
 Указатель на представление, чтобы активировать.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetactiveviewa--cframewndsetactiveview"></a><a name="setactiveview"></a>CFrameWnd::SetActiveView  
 Вызовите эту функцию-член для задания активное представление.  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *pViewNew*  
 Задает указатель [CView](../../mfc/reference/cview-class.md) объекта, или **NULL** для не активное представление.  
  
 `bNotify`  
 Указывает, является ли представление уведомлений об активации. Если **TRUE**, `OnActivateView` вызывается для нового представления; Если **FALSE**, это не так.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию автоматически, как пользователь изменяет фокус на представление в фрейме окна. Можно явно вызывать `SetActiveView` для изменения фокуса на указанное представление.  
  
##  <a name="a-namesetdockstatea--cframewndsetdockstate"></a><a name="setdockstate"></a>CFrameWnd::SetDockState  
 Вызов этой функции-члена для применения сведений о состоянии, хранящихся в `CDockState` объекта на панели элементов управления окна фрейма.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Параметры  
 `state`  
 Сохраненное состояние применяются к панели элементов управления окна фрейма.  
  
### <a name="remarks"></a>Примечания  
 Чтобы восстановить предыдущее состояние панелей элементов управления, можно загрузить сохраненное состояние с `CDockState::LoadState` или `Serialize`, затем использовать `SetDockState` для применения к панели элементов управления окна фрейма. Предыдущее состояние хранится в `CDockState` объекта с`GetDockState`  
  
##  <a name="a-namesetmenubarstatea--cframewndsetmenubarstate"></a><a name="setmenubarstate"></a>CFrameWnd::SetMenuBarState  
 Задает состояние отображения меню в текущем приложении MFC для скрытых или отображаемых.  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nState`|Указывает, следует ли отображать или скрывать меню. `nState` Параметр может принимать следующие значения:<br /><br /> -AFX_MBS_VISIBLE (0x01) — меню отображается, если он скрыт, но не влияет, если она отображается.<br />-AFX_MBS_HIDDEN (0x02) скрывает меню, если она отображается, но не влияет, если он скрыт.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод успешно изменяет состояние меню; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Если возникает ошибка во время выполнения, этот метод утверждения в режиме отладки и вызывает исключение, производный от [CException](../../mfc/reference/cexception-class.md) класса.  
  
##  <a name="a-namesetmenubarvisibilitya--cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a>CFrameWnd::SetMenuBarVisibility  
 Задает поведение по умолчанию меню в текущем приложении MFC, чтобы быть видимым или скрытым.  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nStyle`|Включение меню по умолчанию скрыт, или является видимым и имеет фокус. `nStyle` Параметр может принимать следующие значения:<br /><br /> -AFX_MBV_KEEPVISIBLE (0X01) —<br />     В меню отображается в любое время и по умолчанию не имеет фокус.<br />-AFX_MBV_DISPLAYONFOCUS (0X02) —<br />     Меню по умолчанию скрыт. Если меню скрыта, нажмите клавишу ALT, чтобы отобразить меню и делает его активным. Если меню отображается, нажмите клавишу ALT или ESC, чтобы скрыть меню.<br />-DISPLAYONFOCUS AFX_MBV_ (0X02) | AFX_MBV_DISPLAYONF10 (0X04)<br />     (побитовое сочетание (или)) - меню по умолчанию скрыт. Если меню скрыта, нажмите клавишу F10, чтобы отобразить меню и делает его активным. Если меню отображается, нажмите клавишу F10, чтобы переключить фокус на или меню. Меню отображается до нажатия клавиши ALT или ESC, чтобы скрыть его.|  
  
### <a name="remarks"></a>Примечания  
 Если значение `nStyle` параметр не является допустимым, данный метод подтверждает в режиме отладки и вызывает [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) в режиме выпуска. В случае других ошибок времени выполнения, этот метод утверждения в режиме отладки и вызывает исключение, производный от [CException](../../mfc/reference/cexception-class.md) класса.  
  
 Этот метод воздействует на состояние меню в приложениях, написанных для [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] и более поздних версий.  
  
##  <a name="a-namesetmessagetexta--cframewndsetmessagetext"></a><a name="setmessagetext"></a>CFrameWnd::SetMessageText  
 Эта функция используется для размещения строки на панели строки состояния с идентификатором 0.  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszText`  
 Указывает строку, которую помещен в строке состояния.  
  
 `nID`  
 Идентификатор строкового ресурса строки будет помещено в строке состояния.  
  
### <a name="remarks"></a>Примечания  
 Обычно это крайний левый и длинная, панели строки состояния.  
  
##  <a name="a-namesetprogressbarpositiona--cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a>CFrameWnd::SetProgressBarPosition  
 Задает текущую позицию для отображения на панели задач индикатора хода выполнения Windows 7.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Параметры  
 `nProgressPos`  
 Задает расположение для установки. Он должен быть в пределах диапазона, заданные `SetProgressBarRange`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetprogressbarrangea--cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a>CFrameWnd::SetProgressBarRange  
 Задает диапазон для отображения на панели задач индикатора хода выполнения Windows 7.  
  
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
  
##  <a name="a-namesetprogressbarstatea--cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a>CFrameWnd::SetProgressBarState  
 Задает тип и состояние индикатора хода выполнения, отображаемый на кнопке панели задач.  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `tbpFlags`  
 Флаги, управляющие кнопки выполняется текущее состояние. Укажите только один из следующих флагов, так как все состояния являются взаимоисключающими: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesettaskbaroverlayicona--cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a>CFrameWnd::SetTaskbarOverlayIcon  
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
 Указатель строку, которая содержит версию замещающий текст информации, представленной наложение для специальных возможностей.  
  
 `hIcon`  
 Дескриптор значка для использования в качестве наложения. Это должна быть небольшой значок, измерение 16 x 16 пикселей, разрешением 96 точек на дюйм (dpi). Если значок наложения уже применен к кнопке панели задач, что существующие наложения заменяется. Это значение может быть равно `NULL`. Как `NULL` значение, которое обрабатывается зависит от того, представляет ли кнопки панели задач одного окна или группы windows. За это отвечает вызывающего приложения, чтобы освободить `hIcon` когда он больше не нужен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; `FALSE` Если версия ОС меньше, чем Windows 7 или если заданию значка, возникает ошибка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesettitlea--cframewndsettitle"></a><a name="settitle"></a>CFrameWnd::SetTitle  
 Задает заголовок окна объекта.  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszTitle`  
 Указатель на строку символов, содержащая заголовок окна объекта.  
  
##  <a name="a-nameshowcontrolbara--cframewndshowcontrolbar"></a><a name="showcontrolbar"></a>CFrameWnd::ShowControlBar  
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
 Если **TRUE**, указывает, что будет отображаться на панели управления. Если **FALSE**, указывает, что панель элементов управления является скрытым.  
  
 *bDelay*  
 Если **TRUE**, задержка отображения панели управления. Если **FALSE**, Показать панель элементов управления немедленно.  
  
##  <a name="a-nameshowownedwindowsa--cframewndshowownedwindows"></a><a name="showownedwindows"></a>CFrameWnd::ShowOwnedWindows  
 Вызов этой функции-члена для отображения всех окон, которые являются потомками `CFrameWnd` объекта.  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 `bShow`  
 Указывает, будут ли собственные окна быть отображены или скрыты.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd-класс](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd-класс](../../mfc/reference/cmdichildwnd-class.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [Структура CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)

