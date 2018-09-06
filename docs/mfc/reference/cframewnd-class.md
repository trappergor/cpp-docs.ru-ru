---
title: Класс CFrameWnd | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CFrameWnd [MFC], CFrameWnd
- CFrameWnd [MFC], ActivateFrame
- CFrameWnd [MFC], BeginModalState
- CFrameWnd [MFC], Create
- CFrameWnd [MFC], CreateView
- CFrameWnd [MFC], DockControlBar
- CFrameWnd [MFC], EnableDocking
- CFrameWnd [MFC], EndModalState
- CFrameWnd [MFC], FloatControlBar
- CFrameWnd [MFC], GetActiveDocument
- CFrameWnd [MFC], GetActiveFrame
- CFrameWnd [MFC], GetActiveView
- CFrameWnd [MFC], GetControlBar
- CFrameWnd [MFC], GetDockState
- CFrameWnd [MFC], GetMenuBarState
- CFrameWnd [MFC], GetMenuBarVisibility
- CFrameWnd [MFC], GetMessageBar
- CFrameWnd [MFC], GetMessageString
- CFrameWnd [MFC], GetTitle
- CFrameWnd [MFC], InitialUpdateFrame
- CFrameWnd [MFC], InModalState
- CFrameWnd [MFC], IsTracking
- CFrameWnd [MFC], LoadAccelTable
- CFrameWnd [MFC], LoadBarState
- CFrameWnd [MFC], LoadFrame
- CFrameWnd [MFC], NegotiateBorderSpace
- CFrameWnd [MFC], OnBarCheck
- CFrameWnd [MFC], OnContextHelp
- CFrameWnd [MFC], OnSetPreviewMode
- CFrameWnd [MFC], OnUpdateControlBarMenu
- CFrameWnd [MFC], RecalcLayout
- CFrameWnd [MFC], SaveBarState
- CFrameWnd [MFC], SetActivePreviewView
- CFrameWnd [MFC], SetActiveView
- CFrameWnd [MFC], SetDockState
- CFrameWnd [MFC], SetMenuBarState
- CFrameWnd [MFC], SetMenuBarVisibility
- CFrameWnd [MFC], SetMessageText
- CFrameWnd [MFC], SetProgressBarPosition
- CFrameWnd [MFC], SetProgressBarRange
- CFrameWnd [MFC], SetProgressBarState
- CFrameWnd [MFC], SetTaskbarOverlayIcon
- CFrameWnd [MFC], SetTitle
- CFrameWnd [MFC], ShowControlBar
- CFrameWnd [MFC], ShowOwnedWindows
- CFrameWnd [MFC], OnCreateClient
- CFrameWnd [MFC], OnHideMenuBar
- CFrameWnd [MFC], OnShowMenuBar
- CFrameWnd [MFC], m_bAutoMenuEnable
- CFrameWnd [MFC], rectDefault
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 991b8c55c02272613ce329be9a053ff0110f1926
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764879"
---
# <a name="cframewnd-class"></a>Класс CFrameWnd
Реализует функции однодокументного интерфейса Windows (SDI) с наложенным или всплывающим фреймовым окном с элементами для управления окном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](#cframewnd)|Создает объект `CFrameWnd`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](#activateframe)|Становится кадр отображаются и доступны пользователю.|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|Задает фрейм окна к модальному окну.|  
|[CFrameWnd::Create](#create)|Вызов для создания и инициализации окно фрейма Windows, связанное с `CFrameWnd` объекта.|  
|[CFrameWnd::CreateView](#createview)|Создает представление внутри кадра, который не является производным от `CView`.|  
|[CFrameWnd::DockControlBar](#dockcontrolbar)|Закрепляет панель элементов управления.|  
|[CFrameWnd::EnableDocking](#enabledocking)|Позволяет быть закреплено на панели элементов управления.|  
|[CFrameWnd::EndModalState](#endmodalstate)|Завершает модальное состояние окна фрейма. Позволяет использовать все окна, отключил `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Отображается панель элементов управления.|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Возвращает активное `CDocument` объекта.|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Возвращает активное `CFrameWnd` объекта.|  
|[CFrameWnd::GetActiveView](#getactiveview)|Возвращает активное `CView` объекта.|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|Возвращает значение, на панели управления.|  
|[CFrameWnd::GetDockState](#getdockstate)|Извлекает состояние закрепления окна фрейма.|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Получает состояние отображения меню в текущем приложении MFC.|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Указывает, является ли по умолчанию меню в текущем приложении MFC видимым или скрытым.|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|Возвращает указатель на строке принадлежащих фрейм окна состояния.|  
|[CFrameWnd::GetMessageString](#getmessagestring)|Получает сообщение, соответствующее идентификатор команды.|  
|[CFrameWnd::GetTitle](#gettitle)|Извлекает заголовок панели связанных элементов управления.|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Вызывает `OnInitialUpdate` относящихся ко всем представлениям в окне фрейма для вызова функции-члена.|  
|[CFrameWnd::InModalState](#inmodalstate)|Возвращает значение, указывающее, является ли рамка окна в модальном состоянии.|  
|[CFrameWnd::IsTracking](#istracking)|Определяет, если выполняется перемещение полосы разделения.|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Вызов для загрузки в таблицу сочетаний клавиш.|  
|[CFrameWnd::LoadBarState](#loadbarstate)|Вызов, чтобы восстановить параметры панели управления.|  
|[CFrameWnd::LoadFrame](#loadframe)|Вызов для динамического создания окна фрейма из сведений о ресурсах.|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Согласовывает пограничное пространство в окне фрейма.|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|Вызывается всякий раз, когда действие выполняется на указанный элемент управления панели.|  
|[CFrameWnd::OnContextHelp](#oncontexthelp)|Обрабатывает клавиши SHIFT + F1 справки для элементов на месте.|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Задает главное окно приложения, заходом и выходом из режима предварительного просмотра печати.|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|Вызвано структурой при обновлении соответствующее меню.|  
|[CFrameWnd::RecalcLayout](#recalclayout)|Изменяет положение панелей элементов управления из `CFrameWnd` объекта.|  
|[CFrameWnd::SaveBarState](#savebarstate)|Вызов, чтобы сохранить параметры панели управления.|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Обозначает заданное представление, чтобы быть активное представление для расширенного просмотра.|  
|[CFrameWnd::SetActiveView](#setactiveview)|Задает активный `CView` объекта.|  
|[CFrameWnd::SetDockState](#setdockstate)|Вызов, чтобы закрепить окно в главном окне.|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Задает состояние отображения меню в текущем приложении MFC для скрытых или отображаемых.|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Задает поведение по умолчанию меню в текущем приложении MFC, чтобы быть видимым или скрытым.|  
|[CFrameWnd::SetMessageText](#setmessagetext)|Задает текст строки состояния standard.|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Задает текущую позицию для Windows 7 индикатор выполнения отображается на панели задач.|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Задает диапазон для Windows 7 индикатор выполнения отображается на панели задач.|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Задает тип и состояние индикатора хода выполнения, отображаемый на кнопке панели задач.|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Перегружен. Наложение применяется к кнопке панели задач, чтобы указать состояние приложения или уведомление для пользователя.|  
|[CFrameWnd::SetTitle](#settitle)|Задает заголовок панели связанный элемент управления.|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Вызов для отображения на панели управления.|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Показаны все окна, которые являются потомками `CFrameWnd` объекта.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|Создает окно клиента для кадра.|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Вызывается перед меню в текущем приложении MFC является скрытым.|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Вызывается перед отображением меню в текущем приложении MFC.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Элементы управления автоматическое включение и отключение функциональные возможности для пунктов меню.|  
|[CFrameWnd::rectDefault](#rectdefault)|Передайте этот статический `CRect` как параметр при создании `CFrameWnd` объекта, чтобы разрешить Windows выбрать исходный размер и положение окна.|  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать полезные рамку окна для приложения, являются производными от класса `CFrameWnd`. Добавьте переменные-члены производного класса для хранения данных, к конкретному приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.  
  
 Для создания окна фрейма тремя способами:  
  
-   Напрямую создать его с помощью [создать](#create).  
  
-   Напрямую создать его с помощью [LoadFrame](#loadframe).  
  
-   Косвенно создайте его с помощью шаблона документа.  
  
 Перед вызовом метода либо `Create` или `LoadFrame`, необходимо создать объект окна фрейма в куче, с помощью C++ **новый** оператор. Перед вызовом `Create`, вы также можете зарегистрировать класс окна с [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) глобальную функцию, чтобы задать значок и класс стили рамки.  
  
 Используйте `Create` функция-член для передачи в интерпретации аргументов параметры создания фрейма.  
  
 `LoadFrame` требуется меньшее количество аргументов, чем `Create`и вместо этого получает большинство его значений по умолчанию из ресурсов, включая заголовок, значок, таблицу сочетаний клавиш и меню фрейма. Должны быть доступны `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).  
  
 Когда `CFrameWnd` объект содержит представления и документы, они создаются косвенно платформой вместо непосредственно в программу самим разработчиком. `CDocTemplate` Объект организует Создание кадра, создавать содержащего представления, а также подключение из представлений в соответствующий документ. Параметры `CDocTemplate` указать конструктор `CRuntimeClass` из трех классов участвует (документа, фрейма и представления). Объект `CRuntimeClass` объект используется платформой для динамического создания новых кадров, при указании пользователем (например, с помощью команды создания файла или нескольких окно новой команды интерфейса (MDI) документа).  
  
 Класс окна фрейма, производный от `CFrameWnd` должна быть объявлена с DECLARE_DYNCREATE в порядке, для правильной работы механизма выше RUNTIME_CLASS.  
  
 Объект `CFrameWnd` содержит реализации по умолчанию для выполнения следующих функций главного окна в типичном приложении для Windows:  
  
-   Объект `CFrameWnd` окно следит за активного представления, которая независима от окна Windows, или текущий фокус ввода. При повторной активации кадр, активное представление получает уведомление, вызвав `CView::OnActivateView`.  
  
-   Команда сообщений и множество распространенных сообщений уведомлений кадра, в том числе обрабатываются `OnSetFocus`, `OnHScroll`, и `OnVScroll` функции `CWnd`, делегируются по `CFrameWnd` фрейм окна, в данный момент активное представление.  
  
-   В данный момент активное представление (или MDI дочернее окно текущего активного кадра в случае кадре MDI) можно определить заголовок окна фрейма. Эту функцию можно отключить, отключив бит стиля FWS_ADDTOTITLE фрейма окна.  
  
-   Объект `CFrameWnd` окно управляет положение панелей элементов управления, представления и другие дочерние окна внутри клиентской области окна фрейма. Рамка окна также выполняет обновление времени простоя из панели инструментов и другие кнопки панели элементов управления. Объект `CFrameWnd` окна области также имеет реализацию по умолчанию команды с использованием Включение и отключение панели инструментов и состояние.  
  
-   Объект `CFrameWnd` окно управляет строку главного меню. При отображении всплывающего меню, окна фрейма использует механизм UPDATE_COMMAND_UI чтобы определить, какие элементы меню должны быть включены, отключены или проверки. Когда пользователь выбирает пункт меню, окна фрейма обновляет строку сообщения для этой команды в строке состояния.  
  
-   Объект `CFrameWnd` окно имеет таблице необязательно сочетаний клавиш, автоматически преобразует сочетания клавиш.  
  
-   Объект `CFrameWnd` фрейм окна имеет идентификатор справки необязательный набор с `LoadFrame` , используемый для контекстной справки. Рамка окна является основной orchestrator полумодальные состояний, таких как контекстной справки (SHIFT + F1) и режима предварительного просмотра печати.  
  
-   Объект `CFrameWnd` окно откроется файл из диспетчера файл перетащен на фрейм окна. Если зарегистрировать расширение файла, который связывается с приложением, фрейм окна отвечает на динамических данных exchange (DDE) откройте запрос, возникающее, когда пользователь открывает файл данных в диспетчере файлов или при `ShellExecute` вызове функции Windows.  
  
-   Если окно фрейма главного окна приложения (то есть `CWinThread::m_pMainWnd`), когда пользователь закрывает приложение, фрейм окна предлагает пользователю сохранить все измененные документы (для `OnClose` и `OnQueryEndSession`).  
  
-   Если окно фрейма главного окна приложения, фрейм окна является контекст для выполнения WinHelp. Закрытие окна фрейма завершит работу WINHELP. EXE-файла, если оно было запущено для справки для этого приложения.  
  
 Не используйте C++ **удалить** оператор для уничтожения окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow`. `CFrameWnd` Реализация `PostNcDestroy` приведет к удалению объекта C++ при уничтожении окна. Когда пользователь закрывает окно по умолчанию `OnClose` вызовет обработчик `DestroyWindow`.  
  
 Дополнительные сведения о `CFrameWnd`, см. в разделе [фрейма Windows](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="activateframe"></a>  CFrameWnd::ActivateFrame  
 Эта функция члена для активации и восстанавливает фрейм окна, так как это отображаются и доступны пользователю.  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>Параметры  
 *nCmdShow*  
 Задает параметр для передачи [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). По умолчанию кадр показано и правильно восстановить.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член обычно вызывается после события без пользовательского интерфейса, такие как DDE, OLE и другие события, которое может отображать окна фрейма или его содержимое для пользователя.  
  
 Реализация по умолчанию активирует кадр и переводит ее в верхнюю часть Z-порядок и, при необходимости, выполняет те же действия для окна главного фрейма приложения.  
  
 Переопределите эту функцию-член для изменения, как активируется кадр. Например вы можете принудительно дочерних окон интерфейса MDI, чтобы развернуть. Добавить соответствующие функциональные возможности, а затем вызовите версии базового класса с явным *nCmdShow*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="beginmodalstate"></a>  CFrameWnd::BeginModalState  
 Данная функция-член вызывается для преобразования окна фрейма в модальное.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="cframewnd"></a>  CFrameWnd::CFrameWnd  
 Создает `CFrameWnd` объекта, но не создает видимым фрейма окна.  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите `Create` создание видимого окна.  
  
##  <a name="create"></a>  CFrameWnd::Create  
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
 *lpszClassName*  
 Указывает строку нуль-символом, с именем класса Windows. Имя класса может быть любое имя, зарегистрированное `AfxRegisterWndClass` глобальной функции или `RegisterClass` функции Windows. Если значение равно NULL, используется по умолчанию `CFrameWnd` атрибуты.  
  
 *lpszWindowName*  
 Указывает символ, завершающаяся нулем строка, представляющая имя окна. Используется в качестве текста для заголовка окна.  
  
 *dwStyle*  
 Задает окно [стиля](../../mfc/reference/styles-used-by-mfc.md#window-styles) атрибуты. Включите заголовок окна, чтобы автоматически отобразить имя документа, представленного в окне FWS_ADDTOTITLE стиль.  
  
 *Rect*  
 Задает размер и положение окна. *RectDefault* значение позволяет Windows указать размер и положение нового окна.  
  
 *pParentWnd*  
 Указывает родительского окна этого фрейма окна. Этот параметр должен иметь значение NULL для окна фрейма верхнего уровня.  
  
 *lpszMenuName*  
 Определяет имя ресурса меню для использования с окном. Используйте MAKEINTRESOURCE, если меню имеет целочисленный идентификатор вместо строки. Этот параметр может иметь значение NULL.  
  
 *dwExStyle*  
 Задает окно расширенных [стиля](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) атрибуты.  
  
 *pContext*  
 Задает указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. Этот параметр может иметь значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Создать `CFrameWnd` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CFrameWnd` объекта, а затем вызвать `Create`, который создает окно фрейма Windows и присоединяет его к `CFrameWnd` объекта. `Create` Инициализирует имя класса окна и имя окна и регистрирует значения по умолчанию для его стиль, родительский и связанным меню.  
  
 Используйте `LoadFrame` вместо `Create` загрузить фрейм окна из ресурсов, вместо указания аргументов.  
  
##  <a name="createview"></a>  CFrameWnd::CreateView  
 Вызовите `CreateView` для создания представления в рамке.  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Параметры  
 *pContext*  
 Указывает тип представления и документа.  
  
 *nID*  
 Идентификатор представления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CWnd` объекта, если успешно; в противном случае — NULL.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член для создания «представления», не используйте `CView`-производным внутри фрейма. После вызова метода `CreateView`, необходимо вручную установить представления в активный режим и задать, чтобы сделать его видимым; эти задачи не выполняются автоматически по `CreateView`.  
  
##  <a name="dockcontrolbar"></a>  CFrameWnd::DockControlBar  
 Заставляет панель элементов управления закрепить окно фрейма.  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pBar*  
 Указывает на панели управления можно закреплять.  
  
 *nDockBarID*  
 Определяет, какие стороны окна фрейма для закрепления. Это может быть 0, либо один или несколько из следующих:  
  
- AFX_IDW_DOCKBAR_TOP закрепить в верхней части фрейма окна.  
  
- Закрепить AFX_IDW_DOCKBAR_BOTTOM в нижней части окна фрейма.  
  
- Закрепить AFX_IDW_DOCKBAR_LEFT в левой части окна фрейма.  
  
- Закрепить AFX_IDW_DOCKBAR_RIGHT в правой части окна фрейма.  
  
 Если значение равно 0, на панели управления можно прикреплять к любой стороне включено закрепление целевой фрейм окна.  
  
 *lpRect*  
 Определяет, в экранных координатах в неклиентской области окна фрейма назначения, в которой будет закреплена на панели управления.  
  
### <a name="remarks"></a>Примечания  
 На панели управления будет прикреплен к одной из сторон окна фрейма, заданные в вызовах к обоим [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) и [CFrameWnd::EnableDocking](#enabledocking). В зависимости от выбранного стороне определяется *nDockBarID*.  
  
##  <a name="enabledocking"></a>  CFrameWnd::EnableDocking  
 Вызывайте эту функцию, чтобы включить закрепляемых панелей в окне фрейма.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDockStyle*  
 Указывает, какие стороны окна фрейма может служить закрепление сайтов для панелей элементов управления. Это может быть один или несколько из следующих:  
  
- CBRS_ALIGN_TOP позволяет закрепления в верхней части клиентской области.  
  
- CBRS_ALIGN_BOTTOM позволяет закрепления в нижней части клиентской области.  
  
- CBRS_ALIGN_LEFT позволяет Закрепление левого края клиентской области.  
  
- CBRS_ALIGN_RIGHT позволяет закрепления справа от клиентской области.  
  
- CBRS_ALIGN_ANY позволяет в любой части клиентской области закрепления.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию будет закреплен панелей элементов управления к стороне окна фрейма в следующем порядке: сверху, снизу, слева, справа.  
  
### <a name="example"></a>Пример  
  См. в примере [CToolBar::Create](../../mfc/reference/ctoolbar-class.md#create).  
  
##  <a name="endmodalstate"></a>  CFrameWnd::EndModalState  
 Данная функция-член вызывается для изменения состояния окна с модального на немодальное.  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>Примечания  
 `EndModalState` позволяет использовать все окна, отключил [BeginModalState](#beginmodalstate).  
  
##  <a name="floatcontrolbar"></a>  CFrameWnd::FloatControlBar  
 Вызывайте эту функцию, чтобы вызвать панель элементов управления не закреплено в фрейме окна.  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>Параметры  
 *pBar*  
 Указывает на панели элементов управления, можно оставить плавающим.  
  
 *точка*  
 Расположение, в экранных координатах, где будут размещаться в верхний левый угол панели элементов управления.  
  
 *dwStyle*  
 Указывает, следует ли выравнивать панели элементов управления по горизонтали или вертикали в пределах его новый фрейм окна. Он может принимать любое из следующих:  
  
- CBRS_ALIGN_TOP изменяет ориентацию панели элементов управления по вертикали.  
  
- CBRS_ALIGN_BOTTOM изменяет ориентацию панели элементов управления по вертикали.  
  
- CBRS_ALIGN_LEFT изменяет ориентацию панели элементов управления по горизонтали.  
  
- CBRS_ALIGN_RIGHT изменяет ориентацию панели элементов управления по горизонтали.  
  
 Если стили передаются указание вертикальной или горизонтальной ориентации, панели инструментов будет быть ориентирован горизонтально.  
  
### <a name="remarks"></a>Примечания  
 Как правило это делается при запуске приложения, когда программа является восстановление параметров из предыдущего выполнения.  
  
 Эта функция вызывается платформой, когда пользователь вызывает операцию перетаскивания, выпустив левую кнопку мыши при перетаскивании над расположение, которое не поддерживается для закрепления на панели управления.  
  
##  <a name="getactivedocument"></a>  CFrameWnd::GetActiveDocument  
 Эта функция-член для получения указателя на текущий вызов `CDocument` подключен к текущее активное представление.  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий [CDocument](../../mfc/reference/cdocument-class.md). Если нет текущего документа, возвращает значение NULL.  
  
##  <a name="getactiveframe"></a>  CFrameWnd::GetActiveFrame  
 Вызывайте эту функцию член, чтобы получить указатель на активный дочернего окна многодокументного интерфейса (MDI) окне фрейма MDI.  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активное дочернее окно MDI. Если приложение является приложением SDI или окно области MDI имеет документ не активен, неявный **это** будет возвращаться указатель.  
  
### <a name="remarks"></a>Примечания  
 Если нет активной дочерней MDI-формы или приложения — это один документ интерфейс (SDI), неявный **это** возвращается указатель.  
  
##  <a name="getactiveview"></a>  CFrameWnd::GetActiveView  
 Вызывайте эту функцию члена, чтобы получить указатель на активное представление (если таковые имеются), прикрепляемый к окну фрейма ( `CFrameWnd`).  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий [CView](../../mfc/reference/cview-class.md). Если нет текущего представления, возвращает значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает значение NULL при вызове для фрейма главного окна интерфейса MDI ( `CMDIFrameWnd`). В приложении MDI окна главного фрейма MDI не имеет представления, связанные с ней. Вместо этого каждый отдельных дочернего окна ( `CMDIChildWnd`) имеет одно или несколько связанных представлений. Активное представление в приложении MDI можно получить, сначала поиск активную дочернюю MDI и затем поиск активное представление для этого дочернего окна. Активное дочернее окно MDI можно найти, вызвав функцию `MDIGetActive` или `GetActiveFrame` как показано в следующем:  
  
 [!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="getcontrolbar"></a>  CFrameWnd::GetControlBar  
 Вызовите `GetControlBar` для получения доступа к панели элементов управления, который связан с идентификатором.  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор панели элементов управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на панели элементов управления, который связан с идентификатором.  
  
### <a name="remarks"></a>Примечания  
 *NID* параметр ссылается на уникальный идентификатор, переданный `Create` метод из панели элементов управления. Дополнительные сведения о панели элементов управления см. в разделе [панелей элементов управления](../../mfc/control-bars.md).  
  
 `GetControlBar` Возвращает панель элементов управления даже в том случае, если он открывается как плавающее окно и таким образом не является в настоящее время дочернее окно фрейма.  
  
##  <a name="getdockstate"></a>  CFrameWnd::GetDockState  
 Вызовите эту функцию-член для хранения сведений о состоянии об панелей элементов управления окна фрейма в `CDockState` объекта.  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *state*  
 Содержит текущее состояние окна фрейма панелей элементов управления при возврате.  
  
### <a name="remarks"></a>Примечания  
 После этого можно написать содержимое `CDockState` в хранилище с помощью `CDockState::SaveState` или `Serialize`. Если позже вы хотите восстановить предыдущее состояние панели элементов управления, загрузить состояние с `CDockState::LoadState` или `Serialize`, затем вызовите `SetDockState` для применения к панели элементов управления окна фрейма в предыдущее состояние.  
  
##  <a name="getmenubarstate"></a>  CFrameWnd::GetMenuBarState  
 Получает состояние отображения меню в текущем приложении MFC.  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение может иметь следующие значения:  
  
-   AFX_MBS_VISIBLE (0x01) — меню является видимым.  
  
-   AFX_MBS_HIDDEN (0x02) — меню скрыто.  
  
### <a name="remarks"></a>Примечания  
 Если возникает ошибка времени выполнения, этот метод утверждения в режиме отладки и вызывает исключение, производный от [CException](../../mfc/reference/cexception-class.md) класса.  
  
##  <a name="getmenubarvisibility"></a>  CFrameWnd::GetMenuBarVisibility  
 Указывает, является ли состояние по умолчанию меню в текущем приложении MFC, скрытыми или видимыми.  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает одно из следующих значений:  
  
-   AFX_MBV_KEEPVISIBLE (0x01) — меню отображается вообще и по умолчанию не имеет фокус.  
  
-   AFX_MBV_DISPLAYONFOCUS (0x02) — меню скрыта по умолчанию. Если меню скрыта, нажмите клавишу ALT, чтобы отобразить меню и сделать его активным. Если меню отображается, нажмите клавишу ALT или ESC, чтобы скрыть его.  
  
-   AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (битовую комбинацию (OR)) — меню скрыта по умолчанию. Если меню скрыта, нажмите клавишу F10 для отображения меню и сделать его активным. Если меню отображается, нажмите клавишу F10, чтобы переключить фокус, или отключить меню. До нажатия клавиши ALT или ESC, чтобы скрыть его отображении меню.  
  
### <a name="remarks"></a>Примечания  
 Если возникает ошибка времени выполнения, этот метод утверждения в режиме отладки и вызывает исключение, производный от [CException](../../mfc/reference/cexception-class.md) класса.  
  
##  <a name="getmessagebar"></a>  CFrameWnd::GetMessageBar  
 Вызывайте эту функцию члена, чтобы получить указатель на строку состояния.  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно строки состояния.  
  
##  <a name="getmessagestring"></a>  CFrameWnd::GetMessageString  
 Переопределите эту функцию для передачи пользовательских строк для идентификаторов команд.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор ресурса для нужного сообщения.  
  
 *rMessage*  
 `CString` Объект, в которую необходимо поместить сообщение.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию просто загружает строкой, указанной параметром *nID* из файла ресурсов. Эта функция вызывается платформой, когда строку сообщения в строке состояния необходимо обновить.  
  
##  <a name="gettitle"></a>  CFrameWnd::GetTitle  
 Извлекает заголовок окна объекта.  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий заголовок текущей объекта window.  
  
##  <a name="initialupdateframe"></a>  CFrameWnd::InitialUpdateFrame  
 Вызовите `IntitialUpdateFrame` после создания новый кадр с `Create`.  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>Параметры  
 *pDoc*  
 Указывает на документ, с которым связан объект окна. Может иметь значение NULL.  
  
 *bMakeVisible*  
 Значение TRUE указывает, что кадр должен стать видимым и активных. Если значение равно FALSE, нет потомков становится видимым.  
  
### <a name="remarks"></a>Примечания  
 В этом окне фрейма для получения в результате все представления их `OnInitialUpdate` вызовов.  
  
 Кроме того Если не ранее активное представление, первичное представление окна фрейма делается активным. Первичное представление — это представление с дочерним идентификатор из AFX_IDW_PANE_FIRST. Наконец, является видимым окно фрейма Если *bMakeVisible* имеет ненулевое значение. Если *bMakeVisible* равно 0, текущим фокусом и видимое состояние окна фрейма не изменится. Вызывайте эту функцию, при использовании реализации платформы новый файл и открытие файла необязателен.  
  
##  <a name="inmodalstate"></a>  CFrameWnd::InModalState  
 Вызовите эту функцию-член для проверки того, является ли рамка окна модальное или немодальное.  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если Да; в противном случае 0.  
  
##  <a name="istracking"></a>  CFrameWnd::IsTracking  
 Вызовите для определения того, если разделитель в окне перемещается в данный момент эта функция-член.  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если разделитель выполняется операция; в противном случае 0.  
  
##  <a name="loadacceltable"></a>  CFrameWnd::LoadAccelTable  
 Вызов для загрузки таблицы заданном сочетании клавиш.  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszResourceName*  
 Определяет имя ресурса сочетаний клавиш. Используйте MAKEINTRESOURCE, если ресурс идентифицируется с помощью целочисленному идентификатору.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в таблице сочетаний клавиш успешно загружены; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Только одна таблица может загружаться одновременно.  
  
 Таблицы сочетаний клавиш, загруженных из ресурсов автоматически освобождаются, когда приложение завершает работу.  
  
 Если вы вызываете `LoadFrame` для создания окна фрейма, framework загружает в таблицу сочетаний клавиш, а также ресурсов меню и значок, и последующем вызове эта функция-член затем необязателен.  
  
##  <a name="loadbarstate"></a>  CFrameWnd::LoadBarState  
 Вызывайте эту функцию, чтобы восстановить параметры каждую панель элементов управления, принадлежащие окну фрейма.  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszProfileName*  
 Имя раздела в файле настройки (INI) или ключ в реестре Windows, где хранятся сведения о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Восстановление включает видимость, ориентация по горизонтали и вертикали, состояние закрепления и положение панелей элементов управления.  
  
 Параметры, которые требуется восстановить необходимо записать в реестр перед вызовом метода `LoadBarState`. Записать информацию в реестре, вызвав [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Сведения об записи в INI-файл, вызвав [SaveBarState](#savebarstate).  
  
##  <a name="loadframe"></a>  CFrameWnd::LoadFrame  
 Вызов для динамического создания окна фрейма из сведений о ресурсах.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDResource*  
 Идентификатор общие ресурсы, связанные с окном фрейма.  
  
 *dwDefaultStyle*  
 Рамки [стиля](../../mfc/reference/styles-used-by-mfc.md#window-styles). Включите заголовок окна, чтобы автоматически отобразить имя документа, представленного в окне FWS_ADDTOTITLE стиль.  
  
 *pParentWnd*  
 Указатель на родительской.  
  
 *pContext*  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. Этот параметр может иметь значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Создать `CFrameWnd` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CFrameWnd` объекта, а затем вызвать `LoadFrame`, который загружает окно фрейма Windows и связанных ресурсов и присоединяет окна фрейма для `CFrameWnd` объекта. *NIDResource* параметр задает меню, в таблице сочетаний клавиш, значок и строковый ресурс заголовка для окна фрейма.  
  
 Используйте `Create` функция-член вместо `LoadFrame` при необходимости указать все параметры создания окна фрейма.  
  
 Платформа вызывает `LoadFrame` при создании фрейм окна, используя объект шаблона документа.  
  
 Инфраструктура использует *pContext* аргумент, чтобы указать объекты должен быть подключен к окном фрейма, включая все содержащиеся объекты представлений. Можно задать *pContext* аргумент значение NULL при вызове `LoadFrame`.  
  
##  <a name="m_bautomenuenable"></a>  CFrameWnd::m_bAutoMenuEnable  
 При включении этого элемента данных (по умолчанию), пункты меню, которые не имеют обработчиков ON_UPDATE_COMMAND_UI или ON_COMMAND будет автоматически отключена при пользователь извлекает меню.  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>Примечания  
 Пункты меню, которые имеют обработчик ON_COMMAND, но нет обработчика ON_UPDATE_COMMAND_UI будет включено автоматически.  
  
 Если этот элемент данных имеет значение, пункты меню автоматически включаются таким же образом, что включены кнопки панели инструментов.  
  
> [!NOTE]
> `m_bAutoMenuEnable` не оказывает влияния на пункты меню верхнего уровня.  
  
 Этот элемент данных упрощает реализацию дополнительные команды, на основании текущего выбора и уменьшает потребность в написании ON_UPDATE_COMMAND_UI обработчики для включения и отключения пунктов меню.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="negotiateborderspace"></a>  CFrameWnd::NegotiateBorderSpace  
 Вызовите эту функцию-член для согласования во время активации inplace OLE пространство границы в окне фрейма.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Параметры  
 *nBorderCmd*  
 Содержит одно из следующих значений из `enum BorderCmd`:  
  
- `borderGet` = 1  
  
- `borderRequest` = 2  
  
- `borderSet` = 3  
  
 *lpRectBorder*  
 Указатель на [RECT](../../mfc/reference/rect-structure1.md) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) , указывающий координаты границы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является `CFrameWnd` реализации согласования пространство границы OLE.  
  
##  <a name="onbarcheck"></a>  CFrameWnd::OnBarCheck  
 Вызывается всякий раз, когда действие выполняется на указанный элемент управления панели.  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор элемента управления панели отображаются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если существует панели элементов управления; в противном случае 0.  
  
##  <a name="oncontexthelp"></a>  CFrameWnd::OnContextHelp  
 Обрабатывает клавиши SHIFT + F1 справки для элементов на месте.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы включить контекстной справки, необходимо добавить  
  
 [!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 инструкции для вашей `CFrameWnd` класса схему сообщений, а также добавить записи в таблице сочетаний клавиш, обычно SHIFT + F1, чтобы включить эту функцию-член.  
  
 Если приложение OLE контейнер, `OnContextHelp` помещает все элементы на месте, содержащийся в объекте окна фрейма в режим справки. Курсор изменения стрелки и вопросительного знака и пользователь может затем наведите указатель мыши и нажмите левую кнопку мыши для выбора диалоговое окно, окно, меню или кнопки. Эта функция-член вызывает функцию Windows `WinHelp` с контекст справки объекта под курсором.  
  
##  <a name="oncreateclient"></a>  CFrameWnd::OnCreateClient  
 Вызвано структурой во время выполнения `OnCreate`.  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Параметры  
 *lpcs*  
 Указатель на Windows [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) структуры.  
  
 *pContext*  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Невозможно вызвать эту функцию.  
  
 Реализация по умолчанию эта функция создает `CView` объекта из сведений, предоставленных в *pContext*, если это возможно.  
  
 Переопределите эту функцию для переопределения значения, передаваемые в `CCreateContext` объекта или для изменения создания элементов управления в области главного окна фрейма. `CCreateContext` Описываются элементы, можно переопределить в [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) класса.  
  
> [!NOTE]
>  Не заменяйте значения, передаваемые в `CREATESTRUCT` структуры. Они являются только в информационных целях. Если вы хотите переопределить прямоугольника начального окна, например, переопределить `CWnd` функция-член [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).  
  
##  <a name="onhidemenubar"></a>  CFrameWnd::OnHideMenuBar  
 Эта функция вызывается, когда система собирается скрытие панели меню в текущем приложении MFC.  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>Примечания  
 Этот обработчик событий позволяет вашему приложению для выполнения пользовательских действий в том случае, когда система собирается скрыть меню. Меню не может предотвратить как скрытые, но можно например, вызвать другие методы для извлечения стиля меню или состояния.  
  
##  <a name="onsetpreviewmode"></a>  CFrameWnd::OnSetPreviewMode  
 Вызов этой функции-члена переключает окно главного фрейма приложения в режим предварительного просмотра и из него.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Параметры  
 *bPreview*  
 Указывает, следует ли разместить приложение в режиме предварительного просмотра печати. Значение TRUE для размещения в режиме предварительного просмотра, значение FALSE, чтобы выйти из режима предварительного просмотра.  
  
 *состояния производительности*  
 Указатель на `CPrintPreviewState` структуры.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию отключает все панели инструментов standard и скрывает главного меню и основного окна клиента. Это превращает окон области интерфейса MDI в временных окон фрейма SDI.  
  
 Переопределите эту функцию-член для настройки скрытие и отображение панелей элементов управления и других частей фрейма окна во время предварительного просмотра печати. Вызовите реализацию базового класса из переопределенных версии.  
  
##  <a name="onshowmenubar"></a>  CFrameWnd::OnShowMenuBar  
 Эта функция вызывается, когда система не будет отображать меню в текущем приложении MFC.  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>Примечания  
 Этот обработчик событий позволяет вашему приложению для выполнения пользовательских действий в том случае, когда отобразится меню. Меню не может предотвратить отображение, но можно например, вызвать другие методы для извлечения стиля меню или состояния.  
  
##  <a name="onupdatecontrolbarmenu"></a>  CFrameWnd::OnUpdateControlBarMenu  
 Вызвано структурой при обновлении соответствующее меню.  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 *pCmdUI*  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объект, представляющий меню, которое создается команда обновления. Вызовы обработчика обновления [включить](../../mfc/reference/ccmdui-class.md#enable) функцию-член `CCmdUI` объекта через *pCmdUI* для обновления пользовательского интерфейса.  
  
##  <a name="recalclayout"></a>  CFrameWnd::RecalcLayout  
 Вызывается платформой, когда стандартные панели элементов управления являются включаются или выключаются или при изменении размера окна фрейма.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bNotify*  
 Определяет, получает ли активный элемент на месте для окна фрейма уведомление об изменении макета. Значение TRUE, если элемент уведомляется; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция-член вызывает `CWnd` функция-член `RepositionBars` для изменения положения всех панелей элементов управления в фрейме, а также как основного окна клиента (обычно `CView` или MDICLIENT).  
  
 Переопределите эту функцию-член для управления внешний вид и поведение панели элементов управления, после изменения макета окна фрейма. Например назовите ее при выключать панелей элементов управления или добавьте другую панель элементов управления.  
  
##  <a name="rectdefault"></a>  CFrameWnd::rectDefault  
 Передайте этот статический `CRect` как параметр при создании окна, чтобы разрешить Windows выбрать исходный размер и положение окна.  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="savebarstate"></a>  CFrameWnd::SaveBarState  
 Эта функция используется для хранения информации о каждую панель элементов управления, принадлежащие окну фрейма.  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *lpszProfileName*  
 Имя раздела в файле настройки или ключ в реестре Windows, где хранятся сведения о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Эти сведения могут быть считаны из файла инициализации с помощью [LoadBarState](#loadbarstate). Сведения, хранящиеся включает видимость, горизонтальные/вертикальные ориентации закрепления, состояние и положение панели управления.  
  
##  <a name="setactivepreviewview"></a>  CFrameWnd::SetActivePreviewView  
 Обозначает заданное представление, чтобы быть активное представление для расширенного просмотра.  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>Параметры  
 *pViewNew*  
 Указатель на представление для активации.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setactiveview"></a>  CFrameWnd::SetActiveView  
 Вызывайте эту функцию члена, чтобы задать активное представление.  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *pViewNew*  
 Задает указатель на [CView](../../mfc/reference/cview-class.md) объект или значение NULL для не активное представление.  
  
 *bNotify*  
 Указывает, является ли представление для получения уведомлений об активации. Если значение равно TRUE, `OnActivateView` вызывается для нового представления; Если FALSE, это не так.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию автоматически, когда пользователь изменяет фокус в представлении в фрейме окна. Можно явно вызывать `SetActiveView` для изменения фокуса для заданного представления.  
  
##  <a name="setdockstate"></a>  CFrameWnd::SetDockState  
 Вызывайте эту функцию члена, чтобы применить сведения о состоянии, хранящихся в `CDockState` объект для панелей элементов управления окна фрейма.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Параметры  
 *state*  
 Сохраненное состояние применяются к панели элементов управления окна фрейма.  
  
### <a name="remarks"></a>Примечания  
 Чтобы восстановить предыдущее состояние панелей элементов управления, можно загрузить сохраненное состояние с `CDockState::LoadState` или `Serialize`, затем с помощью `SetDockState` для применения их к панели элементов управления окна фрейма. Предыдущее состояние хранится в `CDockState` объекта с `GetDockState`  
  
##  <a name="setmenubarstate"></a>  CFrameWnd::SetMenuBarState  
 Задает состояние отображения меню в текущем приложении MFC для скрытых или отображаемых.  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] *nState*|Указывает, следует ли отобразить или скрыть меню. *NState* параметр может иметь следующие значения:<br /><br /> -AFX_MBS_VISIBLE (0x01) — открывает меню, если он скрыт, но не действует, если он видим.<br />-AFX_MBS_HIDDEN (0x02) — скрывает элемент управления menu, если она видна, но не действует, если он скрыт.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод успешно изменяет состояние меню; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Если возникает ошибка времени выполнения, этот метод утверждения в режиме отладки и вызывает исключение, производный от [CException](../../mfc/reference/cexception-class.md) класса.  
  
##  <a name="setmenubarvisibility"></a>  CFrameWnd::SetMenuBarVisibility  
 Задает поведение по умолчанию меню в текущем приложении MFC, чтобы быть видимым или скрытым.  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] *nStyle*|Указывает меню по умолчанию скрыт, или является видимым и имеет фокус. *NStyle* параметр может иметь следующие значения:<br /><br /> -AFX_MBV_KEEPVISIBLE (0X01) —<br />     В меню отображается все время и по умолчанию не имеет фокус.<br />-AFX_MBV_DISPLAYONFOCUS (0X02 —)<br />     Меню скрыта по умолчанию. Если меню скрыта, нажмите клавишу ALT, чтобы отобразить меню и сделать его активным. Если меню отображается, нажмите клавишу ALT или ESC для скрытия меню.<br />-AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (битовую комбинацию (OR)) — меню скрыта по умолчанию. Если меню скрыта, нажмите клавишу F10 для отображения меню и сделать его активным. Если меню отображается, нажмите клавишу F10, чтобы переключить фокус, или отключить меню. До нажатия клавиши ALT или ESC, чтобы скрыть его отображении меню.|  
  
### <a name="remarks"></a>Примечания  
 Если значение *nStyle* параметр не является допустимым, этот метод проверочные утверждения в режиме отладки и вызывает [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) в режиме выпуска. В случае другие ошибки времени выполнения, этот метод, проверочные утверждения в режиме отладки и вызывает исключение, производный от [CException](../../mfc/reference/cexception-class.md) класса.  
  
 Этот метод воздействует на состояние меню в приложениях, написанных для Windows Vista и более поздних версий.  
  
##  <a name="setmessagetext"></a>  CFrameWnd::SetMessageText  
 Вызывайте эту функцию для размещения строки в области строки состояния, который имеет идентификатор 0.  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszText*  
 Указывает строку, которую можно поместить в строку состояния.  
  
 *nID*  
 Идентификатор строкового ресурса строки размещаются на строке состояния.  
  
### <a name="remarks"></a>Примечания  
 Обычно это области крайний левый и длинная, строки состояния.  
  
##  <a name="setprogressbarposition"></a>  CFrameWnd::SetProgressBarPosition  
 Задает текущую позицию для Windows 7 индикатора, отображаемый на панели задач.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Параметры  
 *nProgressPos*  
 Задает положение для задания. Он должен быть в пределах диапазона, заданные `SetProgressBarRange`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setprogressbarrange"></a>  CFrameWnd::SetProgressBarRange  
 Задание диапазона для индикатора выполнения Windows 7, отображаются на панели задач.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Параметры  
 *nRangeMin*  
 Минимальное значение.  
  
 *nRangeMax*  
 Максимальное значение.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setprogressbarstate"></a>  CFrameWnd::SetProgressBarState  
 Задает тип и состояние индикатора хода выполнения, отображаемый на кнопке панели задач.  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *tbpFlags*  
 Флаги, определяющие состояние кнопки хода выполнения. Укажите только одно из следующих флагов, так как все состояния являются взаимоисключающими: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settaskbaroverlayicon"></a>  CFrameWnd::SetTaskbarOverlayIcon  
 Перегружен. Наложение применяется к кнопке панели задач для указания состояния приложения или для уведомления пользователя.  
  
```  
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,  
    LPCTSTR lpcszDescr);

 
BOOL SetTaskbarOverlayIcon(
    HICON hIcon,  
    LPCTSTR lpcszDescr);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDResource*  
 Указывает идентификатор ресурса значка для использования в качестве наложения. Описание *hIcon* подробные сведения.  
  
 *lpcszDescr*  
 Указатель на строку, которая предоставляет замещающий текст версию информации, сообщаемой путем наложения, для специальных возможностей.  
  
 *hIcon*  
 Дескриптор значка для использования в качестве наложения. Это должна быть небольшой значок, измерение 16 x 16 пикселей, разрешением 96 точек на дюйм (dpi). Если накладывающийся значок уже применяется к кнопке панели задач, заменяется, существующие наложения. Это значение может быть NULL. Как обрабатывается значение NULL, зависит от того, представляет ли на кнопке одного окна или группы windows. Он отвечает за вызывающего приложения, чтобы освободить *hIcon* когда он больше не нужен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если выполнение прошло успешно; Значение FALSE, если версия ОС меньше, чем Windows 7 или при возникновении ошибки Задание значка.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settitle"></a>  CFrameWnd::SetTitle  
 Задает заголовок окна объекта.  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszTitle*  
 Указатель на строку символов, содержащая заголовок окна объекта.  
  
##  <a name="showcontrolbar"></a>  CFrameWnd::ShowControlBar  
 Вызовите эту функцию-член для отображения или скрытия панели элементов управления.  
  
```  
void ShowControlBar(
    CControlBar* pBar,  
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>Параметры  
 *pBar*  
 Указатель на панели управления, чтобы отображать и скрывать.  
  
 *bShow*  
 Если значение равно TRUE, указывает, что на панели управления для отображения. Если значение равно FALSE, указывает, что на панели управления будут скрыты.  
  
 *bDelay*  
 Если значение равно TRUE, отложить отображение панели управления. Если значение равно FALSE, отображение элемента управления панели немедленно.  
  
##  <a name="showownedwindows"></a>  CFrameWnd::ShowOwnedWindows  
 Вызовите эту функцию-член для отображения всех окон, которые являются потомками `CFrameWnd` объекта.  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 *bShow*  
 Указывает, принадлежащий windows, следует ли отображать и скрывать.  
  
## <a name="see-also"></a>См. также  
 [Класс CWnd](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)   
 [Класс CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)   
 [Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)   
 [Класс CView](../../mfc/reference/cview-class.md)   
 [Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)   
 [Структура CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)
