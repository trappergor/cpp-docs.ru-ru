---
title: Класс CFrameWnd
ms.date: 11/04/2016
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
ms.openlocfilehash: 0fd104e377300233ef1526f6c453346555dd27d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373791"
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
|[CFrameWnd::CFrameWnd](#cframewnd)|Формирует объект `CFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFrameWnd::Активировать](#activateframe)|Делает кадр видимым и доступным для пользователя.|
|[CFrameWnd::BeginModalState](#beginmodalstate)|Устанавливает окно рамы в модальный.|
|[CFrameWnd::Создание](#create)|Вызов для создания и инициализации `CFrameWnd` окна кадра Windows, связанного с объектом.|
|[CFrameWnd::CreateView](#createview)|Создает представление в кадре, который `CView`не является производным от .|
|[CFrameWnd::DockControlBar](#dockcontrolbar)|Доки панели управления.|
|[CFrameWnd::EnableDocking](#enabledocking)|Позволяет пристыковаться к панели управления.|
|[CFrameWnd::EndModalState](#endmodalstate)|Завершает состояние модального окна кадра. Включает все окна отключены. `BeginModalState`|
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Плавает панель управления.|
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Возвращает активный `CDocument` объект.|
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Возвращает активный `CFrameWnd` объект.|
|[CFrameWnd::GetActiveView](#getactiveview)|Возвращает активный `CView` объект.|
|[CFrameWnd::GetControlBar](#getcontrolbar)|Извлекает панель управления.|
|[CFrameWnd::GetDockState](#getdockstate)|Извлекает состояние доков окна рамы.|
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Извлекает состояние отображения меню в текущем приложении MFC.|
|[CFrameWnd::GetMenuBarВидимость](#getmenubarvisibility)|Указывает, скрыто ли или видно поведение меню по умолчанию в текущем приложении MFC.|
|[CFrameWnd::GetMessageBar](#getmessagebar)|Возвращает указатель в панель состояния, принадлежащую окну рамы.|
|[CFrameWnd::GetMessageString](#getmessagestring)|Извлекает сообщение, соответствующее идентификатору команды.|
|[CFrameWnd::GetTitle](#gettitle)|Получает название соответствующей панели управления.|
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Вызывает `OnInitialUpdate` функцию члена, относящуюся ко всем представлениям в окне кадра.|
|[CFrameWnd::InModalState](#inmodalstate)|Возвращает значение, указывающее, находится ли окно кадра в модальном состоянии.|
|[CFrameWnd::IsTracking](#istracking)|Определяет, перемещается ли бар сплиттера.|
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Вызов для загрузки таблицы акселератора.|
|[CFrameWnd::LoadBarState](#loadbarstate)|Вызов для восстановления параметров панели управления.|
|[CFrameWnd::LoadFrame](#loadframe)|Вызов динамически создать окно кадра из информации о ресурсах.|
|[CFrameWnd::ПереговорыBorderSpace](#negotiateborderspace)|Переговоры пограничного пространства в окне кадра.|
|[CFrameWnd::OnBarCheck](#onbarcheck)|Вызывается всякий раз, когда действие выполняется на указанной панели управления.|
|[CFrameWnd::OnContextHelp](#oncontexthelp)|Ручки SHIFT-F1 Справка для на месте элементов.|
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Устанавливает окно основной кадр амра в режим печати и выход из него.|
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|Вызывается в рамках при обновлении связанного меню.|
|[CFrameWnd::RecalcLayout](#recalclayout)|Перемещает панели управления `CFrameWnd` объекта.|
|[CFrameWnd::SaveBarState](#savebarstate)|Вызов для сохранения настроек панели управления.|
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Обозначает указанное представление как активное представление для Rich Preview.|
|[CFrameWnd::SetActiveView](#setactiveview)|Устанавливает активный `CView` объект.|
|[CFrameWnd::SetDockState](#setdockstate)|Вызов для стыковки окна рамы в главном окне.|
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Устанавливает состояние отображения меню в текущем приложении MFC для скрытых или отображаемых.|
|[CFrameWnd::SetMenuBarВидимость](#setmenubarvisibility)|Устанавливает поведение меню по умолчанию в текущем приложении MFC, чтобы быть скрытым или видимым.|
|[CFrameWnd::SetMessageText](#setmessagetext)|Устанавливает текст стандартной панели статуса.|
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Устанавливает текущее положение для панели прогресса Windows 7, отображаемый на панели задач.|
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Диапазон наборов для панели прогресса Windows 7 отображается на панели задач.|
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Устанавливает тип и состояние индикатора прогресса, отображаемого на кнопке панели задач.|
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Перегружен. Применяет наложение к кнопке панели задач для указания статуса приложения или уведомления пользователю.|
|[CFrameWnd::SetTitle](#settitle)|Устанавливает название соответствующей панели управления.|
|[CFrameWnd::ShowControlBar](#showcontrolbar)|Звоните, чтобы показать панель управления.|
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Отображается все окна, которые `CFrameWnd` являются потомками объекта.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CFrameWnd::OnCreateClient](#oncreateclient)|Создает клиентское окно для кадра.|
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Вызывается до меню в текущем приложении MFC скрыта.|
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Вызывается до того, как меню отображается в текущем приложении MFC.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Элементы управления автоматически включат и отключат функциональность для элементов меню.|
|[CFrameWnd::rectDefault](#rectdefault)|Передайте `CRect` эту статичную `CFrameWnd` в качестве параметра при создании объекта, чтобы позволить Windows выбрать первоначальный размер окна и положение.|

## <a name="remarks"></a>Remarks

Чтобы создать полезное окно кадра для `CFrameWnd`приложения, выберите класс из . Добавление переменных членов в полученный класс для хранения данных, специфичные для приложения. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Существует три способа построения окна рамы:

- Непосредственно построить его с помощью [Создать](#create).

- Непосредственно построить его с помощью [LoadFrame](#loadframe).

- Косвенно постройте его с помощью шаблона документа.

Перед вызовом `Create` `LoadFrame`или с помощью **нового** оператора c-e необходимо построить объект окна кадра на куче. Перед `Create`вызовом вы также можете зарегистрировать класс окон с глобальной функцией [AfxRegisterWndClass,](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) чтобы установить значок и стили классов для кадра.

Используйте `Create` функцию члена, чтобы передать параметры создания кадра в качестве непосредственных аргументов.

`LoadFrame`требует меньше аргументов, чем, `Create`и вместо этого извлекает большую часть значений по умолчанию из ресурсов, включая подпись кадра, значок, таблицу акселератора и меню. Чтобы быть `LoadFrame`доступными, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).

Когда `CFrameWnd` объект содержит представления и документы, они создаются косвенно рамочным, а не непосредственно программистом. Объект `CDocTemplate` организует создание кадра, создание содержащих представлений и соединение представлений с соответствующим документом. Параметры конструктора `CDocTemplate` определяют `CRuntimeClass` три класса (документ, кадр и представление). Объект `CRuntimeClass` используется инфраструктурой для динамического создания новых кадров при указании пользователем (например, с помощью команды File New или новой команды windows multiple document (MDI) Window New).

Класс окна кадра, `CFrameWnd` полученный из, должен быть объявлен с DECLARE_DYNCREATE для того, чтобы вышеуказанный механизм RUNTIME_CLASS работал правильно.

A `CFrameWnd` содержит реализации по умолчанию для выполнения следующих функций основного окна в типичном приложении для Windows:

- Окно `CFrameWnd` кадра отслеживает активное представление, которое не зависит от активного окна Windows или текущего ввода. При повторном активации кадра активное представление `CView::OnActivateView`уведомляется по вызову.

- Сообщения командования и множество распространенных сообщений об `OnSetFocus`уведомлении кадра, включая сообщения, обрабатываемые `OnHScroll`, `OnVScroll` и функции, `CWnd`делегируются окном `CFrameWnd` кадра в активное представление.

- Активное представление в настоящее время (или в настоящее время активное окно детской рамы MDI в случае кадра MDI) может определить заголовок окна кадра. Эта функция может быть отключена, выключив FWS_ADDTOTITLE стилю немного окна кадра.

- Окно `CFrameWnd` рамы управляет позиционированием баров управления, представлений и других детских окон в клиентской зоне окна кадра. Окно кадра также делает простоя обновления панели инструментов и других кнопок панели управления. Окно `CFrameWnd` кадра также имеет по умолчанию реализации команд для переключания панели и выключения панели инструментов и панели статуса.

- Окно `CFrameWnd` рамы управляет основным баром меню. При отображении всплывающее меню в окне кадра используется механизм UPDATE_COMMAND_UI для определения элементов меню, которые следует использовать, отключать или проверять. Когда пользователь выбирает элемент меню, окно кадра обновляет строку состояния строкой с строкой сообщения для этой команды.

- Окно `CFrameWnd` рамы имеет дополнительную таблицу ускорителей, которая автоматически переводит ускорители клавиатуры.

- Окно `CFrameWnd` кадра имеет дополнительный `LoadFrame` набор идентификаторов справки, который используется для чувствительной к контексту помощи. Окно кадра является основным оркестратором полумодальных состояний, таких как контекстно-чувствительная помощь (SHIFT-F1) и режимы предварительного просмотра печати.

- Окно `CFrameWnd` рамы откроет файл, вытащенный из диспетчера файлов и упавший на окно кадра. Если расширение файла зарегистрировано и связано с приложением, окно кадра отвечает на открытый запрос динамического обмена данными (DDE), который возникает, когда пользователь открывает файл данных в диспетчере файлов или когда вызывается функция `ShellExecute` Windows.

- Если окно кадра является основным окном `CWinThread::m_pMainWnd`приложения (т.е. при закрытии приложения, окно кадра побуждает пользователя сохранять любые измененные документы (для `OnClose` и `OnQueryEndSession`).

- Если окно кадра является основным окном приложения, окно кадра является контекстом для запуска WinHelp. Закрытие окна рамы выключит WINHELP. EXE, если он был запущен для помощи для этого приложения.

Не используйте оператора **удаления** C's для уничтожения окна рамы. Используйте вместо этого `CWnd::DestroyWindow`. Реализация `CFrameWnd` `PostNcDestroy` будет удалять объект C's при уничтожении окна. Когда пользователь закрывает окно кадра, `OnClose` обработчик по умолчанию вызовет. `DestroyWindow`

Для получения `CFrameWnd`дополнительной информации о, см. [Frame Windows](../../mfc/frame-windows.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cframewndactivateframe"></a><a name="activateframe"></a>CFrameWnd::Активировать

Вызов эту функцию участника, чтобы активировать и восстановить окно кадра, чтобы оно было видимым и доступным для пользователя.

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>Параметры

*nCmdShow*<br/>
Определяет параметр для передачи [на CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). По умолчанию кадр отображается и корректно восстанавливается.

### <a name="remarks"></a>Remarks

Эта функция участника обычно вызывается после события непользовательского интерфейса, такого как DDE, OLE или другое событие, которое может показать пользователю окно кадра или его содержимое.

Реализация по умолчанию активирует кадр и переносит его в верхнюю часть заказа и, при необходимости, выполняет те же шаги для окна основного кадра приложения.

Переизобить эту функцию участника, чтобы изменить способ активации кадра. Например, можно заставить окна для детей MDI быть максимально. Добавьте соответствующую функциональность, а затем позвоните в версию базового класса с явным *nCmdShow.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

## <a name="cframewndbeginmodalstate"></a><a name="beginmodalstate"></a>CFrameWnd::BeginModalState

Данная функция-член вызывается для преобразования окна фрейма в модальное.

```
virtual void BeginModalState();
```

## <a name="cframewndcframewnd"></a><a name="cframewnd"></a>CFrameWnd::CFrameWnd

Строит `CFrameWnd` объект, но не создает видимое окно кадра.

```
CFrameWnd();
```

### <a name="remarks"></a>Remarks

Вызов `Create` для создания видимого окна.

## <a name="cframewndcreate"></a><a name="create"></a>CFrameWnd::Создание

Вызов для создания и инициализации `CFrameWnd` окна кадра Windows, связанного с объектом.

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

*lpszClassName*<br/>
Указывает на строку символов с нулевым завершением, которая называет класс Windows. Имя класса может быть любым `AfxRegisterWndClass` именем, `RegisterClass` зарегистрированным с глобальной функцией или функцией Windows. Если NULL, использует предопределенные атрибуты по умолчанию. `CFrameWnd`

*lpszWindowName*<br/>
Указывает на строку символов с нулевым завершением, представляющую имя окна. Используется в качестве текста для заголовка бара.

*dwStyle*<br/>
Определяет атрибуты [стиля](../../mfc/reference/styles-used-by-mfc.md#window-styles) окна. Включите FWS_ADDTOTITLE стиль, если вы хотите, чтобы заголовок бар автоматически отображать имя документа, представленного в окне.

*rect*<br/>
Определяет размер и положение окна. Значение *rectDefault* позволяет Windows указать размер и положение нового окна.

*pParentWnd*<br/>
Определяет родительское окно этого окна кадра. Этот параметр должен быть NULL для окон рамки верхнего уровня.

*lpszМенюнам*<br/>
Определяет название ресурса меню, используемого с окном. Используйте MAKEINTRESOURCE, если в меню есть идентификатор, а не строка. Этот параметр может быть NULL.

*dwExStyle*<br/>
Определяет атрибуты расширенного [стиля](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) окна.

*pContext*<br/>
Определяет указатель на структуру [CCreateContext.](../../mfc/reference/ccreatecontext-structure.md) Этот параметр может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если инициализация является успешной; в противном случае 0.

### <a name="remarks"></a>Remarks

Постройте `CFrameWnd` объект в два этапа. Сначала вызвать конструктор, который строит `CFrameWnd` объект, а затем `Create`вызвать, который создает окно кадра `CFrameWnd` Windows и прикрепляет его к объекту. `Create`Инициализация имени класса окна и имени окна и регистрирует значения по умолчанию для его стиля, родительского и связанного меню.

Используйте `LoadFrame` `Create` вместо того, чтобы загружать окно кадра с ресурса вместо указания его аргументов.

## <a name="cframewndcreateview"></a><a name="createview"></a>CFrameWnd::CreateView

Вызов `CreateView` для создания представления в кадре.

```
CWnd* CreateView(
    CCreateContext* pContext,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Параметры

*pContext*<br/>
Определяет тип представления и документа.

*nID*<br/>
Идентификационный номер представления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CWnd` объект в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Используйте эту функцию участника для `CView`создания "представлений", которые не являются выведены в кадре. После `CreateView`вызова необходимо вручную настроить представление для активного и установить его для видимого; эти задачи не выполняются автоматически `CreateView`.

## <a name="cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a>CFrameWnd::DockControlBar

Вызывает пристыкование панели управления к окну рамы.

```
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
Указывает на переулок управления, которая будет пристыкована.

*nDockBarID*<br/>
Определяет, какие стороны окна рамы следует учитывать для стыковки. Это может быть 0, или один или более из следующих:

- AFX_IDW_DOCKBAR_TOP док на верхней стороне окна рамы.

- AFX_IDW_DOCKBAR_BOTTOM док в нижней части окна рамы.

- AFX_IDW_DOCKBAR_LEFT Док в левую сторону окна рамы.

- AFX_IDW_DOCKBAR_RIGHT док в правую сторону окна рамы.

Если 0, панель управления может быть пристыкована к любой стороне включен для стыковки в окне кадра назначения.

*lpRect*<br/>
Определяет, в координатах экрана, где панель управления будет состыкована в неклиентской области окна кадра назначения.

### <a name="remarks"></a>Remarks

Панель управления будет пристыкована к одной из сторон окна рамы, указанной в вызовах на [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) и [CFrameWnd::EnableDocking](#enabledocking). Выбранная сторона определяется *nDockBarID.*

## <a name="cframewndenabledocking"></a><a name="enabledocking"></a>CFrameWnd::EnableDocking

Вызов исключите эту функцию, чтобы включить док-панели управления в окне рамы.

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Параметры

*dwDockStyle*<br/>
Определяет, какие стороны окна рамы могут служить стыковочными площадками для контрольных баров. Это может быть один или несколько из следующих:

- CBRS_ALIGN_TOP позволяет стыковки в верхней части клиентской области.

- CBRS_ALIGN_BOTTOM позволяет стыковки в нижней части клиентской области.

- CBRS_ALIGN_LEFT позволяет стыковки на левой стороне клиентской области.

- CBRS_ALIGN_RIGHT Позволяет стыковки на правой стороне клиентской области.

- CBRS_ALIGN_ANY позволяет стыковки с любой стороны клиентской области.

### <a name="remarks"></a>Remarks

По умолчанию панели управления будут пристыкованы к боковой части окна кадра в следующем порядке: верхний, нижний, левый, правый.

### <a name="example"></a>Пример

  Смотрите пример [для CToolBar::Создание](../../mfc/reference/ctoolbar-class.md#create).

## <a name="cframewndendmodalstate"></a><a name="endmodalstate"></a>CFrameWnd::EndModalState

Данная функция-член вызывается для изменения состояния окна с модального на немодальное.

```
virtual void EndModalState();
```

### <a name="remarks"></a>Remarks

`EndModalState`позволяет все окна отключены [BeginModalState.](#beginmodalstate)

## <a name="cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a>CFrameWnd::FloatControlBar

Вызовите эту функцию, чтобы не пристыковаться к окну рамы.

```
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
Указывает на панель управления, которая будет плавать.

*Точки*<br/>
Расположение, в координатах экрана, где будет размещен верхний левый угол панели управления.

*dwStyle*<br/>
Определяет, следует ли выравнивать панель управления горизонтально или вертикально в пределах нового окна кадра. Это может быть любой из следующих:

- CBRS_ALIGN_TOP Ориентирует панель управления вертикально.

- CBRS_ALIGN_BOTTOM Ориентирует панель управления вертикально.

- CBRS_ALIGN_LEFT Ориентирует панель управления горизонтально.

- CBRS_ALIGN_RIGHT Ориентирует панель управления горизонтально.

Если стили передаются с указанием горизонтальной и вертикальной ориентации, панель инструментов будет ориентирована горизонтально.

### <a name="remarks"></a>Remarks

Как правило, это делается при запуске приложения, когда программа восстанавливает настройки из предыдущего выполнения.

Эта функция вызывается фреймворком, когда пользователь вызывает операцию падения, выпустив левую кнопку мыши, перетащив панель управления над местом, которое недоступно для стыковки.

## <a name="cframewndgetactivedocument"></a><a name="getactivedocument"></a>CFrameWnd::GetActiveDocument

Вызовите эту функцию участника, `CDocument` чтобы получить указатель на ток, прикрепленный к текущему активному представлению.

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий [CDocument](../../mfc/reference/cdocument-class.md). Если нет текущего документа, возвращает NULL.

## <a name="cframewndgetactiveframe"></a><a name="getactiveframe"></a>CFrameWnd::GetActiveFrame

Вызовите эту функцию участника, чтобы получить указатель на активное окно детского интерфейса (MDI) в окне кадра MDI.

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на активное окно ребенка MDI. Если приложение является приложением SDI, или окно милитера MDI не имеет активного документа, неявный **указатель** будет возвращен.

### <a name="remarks"></a>Remarks

Если нет активного ребенка MDI или приложение представляет собой единый интерфейс документа (SDI), неявный **указатель** возвращается.

## <a name="cframewndgetactiveview"></a><a name="getactiveview"></a>CFrameWnd::GetActiveView

Вызов эту функцию участника, чтобы получить указатель на активное представление `CFrameWnd`(если таковой имеется), прикрепленное к окну рамы ().

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий [CView](../../mfc/reference/cview-class.md). Если нет текущего представления, возвращает NULL.

### <a name="remarks"></a>Remarks

Эта функция возвращает NULL при вызове для `CMDIFrameWnd`окна основной рамы MDI (). В приложении MDI окно основной кадра MDI не имеет представления, связанного с ним. Вместо этого каждое `CMDIChildWnd`отдельное окно ребенка () имеет одно или несколько связанных представлений. Активное представление в приложении MDI можно получить, сначала найдя активное окно ребенка MDI, а затем найдя активное представление для этого окна ребенка. Активное окно ребенка MDI можно `MDIGetActive` найти, позвонив по функции или `GetActiveFrame` как показано в следующем:

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

## <a name="cframewndgetcontrolbar"></a><a name="getcontrolbar"></a>CFrameWnd::GetControlBar

Вызов, `GetControlBar` чтобы получить доступ к панели управления, связанной с идентификатором.

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификационный номер панели управления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на панель управления, связанную с идентификатором.

### <a name="remarks"></a>Remarks

Параметр *nID* относится к уникальному `Create` идентификатору, передаваемому методу панели управления. Для получения дополнительной информации о контрольных барах, обратитесь к теме, озаглавленной [Контроль баров](../../mfc/control-bars.md).

`GetControlBar`возвращает панель управления, даже если она плавает и, таким образом, в настоящее время не является детским окном кадра.

## <a name="cframewndgetdockstate"></a><a name="getdockstate"></a>CFrameWnd::GetDockState

Вызов ифункции этого элемента для хранения информации `CDockState` о состоянии в элементе управления окна в объекте.

```
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>Параметры

*Государства*<br/>
Содержит текущее состояние баров управления окном кадра по возвращении.

### <a name="remarks"></a>Remarks

Вы можете написать `CDockState` содержимое `CDockState::SaveState` для `Serialize`хранения с помощью или . Если позже требуется восстановить панели управления в прежнее `CDockState::LoadState` `Serialize`состояние, `SetDockState` загрузите состояние или позвоните, чтобы применить предыдущее состояние к барам управления окна кадра.

## <a name="cframewndgetmenubarstate"></a><a name="getmenubarstate"></a>CFrameWnd::GetMenuBarState

Извлекает состояние отображения меню в текущем приложении MFC.

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>Возвращаемое значение

Значение возврата может иметь следующие значения:

- AFX_MBS_VISIBLE (0x01) - Меню видно.

- AFX_MBS_HIDDEN (0x02) - Меню скрыто.

### <a name="remarks"></a>Remarks

При возникновении ошибки во времени выполнения этот метод утверждается в режиме Debug и вызывает исключение, полученное из класса [CException.](../../mfc/reference/cexception-class.md)

## <a name="cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBarВидимость

Указывает, скрыто ли или видно состояние меню по умолчанию в текущем приложении MFC.

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает одно из следующих значений:

- AFX_MBV_KEEPVISIBLE (0x01) - Меню отображается в любое время, и по умолчанию не имеет фокуса.

- AFX_MBV_DISPLAYONFOCUS (0x02) - Меню скрыто по умолчанию. Если меню скрыто, нажмите на ключ ALT, чтобы отобразить меню и придать ему фокус. Если меню отображается, нажмите на ключ ALT или ESC, чтобы скрыть его.

- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (битная комбинация (OR)) - Меню скрыто по умолчанию. Если меню скрыто, нажмите клавишу F10, чтобы отобразить меню и придать ему фокус. Если меню отображается, нажмите клавишу F10, чтобы переключить фокус на или вне меню. Меню отображается до тех пор, пока вы не нажмете на ключ ALT или ESC, чтобы скрыть его.

### <a name="remarks"></a>Remarks

При возникновении ошибки во времени выполнения этот метод утверждается в режиме Debug и вызывает исключение, полученное из класса [CException.](../../mfc/reference/cexception-class.md)

## <a name="cframewndgetmessagebar"></a><a name="getmessagebar"></a>CFrameWnd::GetMessageBar

Вызовите эту функцию участника, чтобы получить указатель на бар статуса.

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно окна статус-бара.

## <a name="cframewndgetmessagestring"></a><a name="getmessagestring"></a>CFrameWnd::GetMessageString

Переопределить эту функцию, чтобы обеспечить пользовательские строки для идонов команд.

```
virtual void GetMessageString(
    UINT nID,
    CString& rMessage) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор ресурса желаемого сообщения.

*rMessage*<br/>
`CString`объект, в который разместить сообщение.

### <a name="remarks"></a>Remarks

Реализация по умолчанию просто загружает строку, указанную *nID,* из файла ресурса. Эта функция вызывается инфраструктурой, когда строка сообщения в строке состояния нуждается в обновлении.

## <a name="cframewndgettitle"></a><a name="gettitle"></a>CFrameWnd::GetTitle

Извлекает название объекта окна.

```
CString GetTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий текущее название объекта окна.

## <a name="cframewndinitialupdateframe"></a><a name="initialupdateframe"></a>CFrameWnd::InitialUpdateFrame

Вызов `IntitialUpdateFrame` после создания нового `Create`кадра с .

```
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указывает на документ, к которому связано окно кадра. Может иметь значение NULL.

*bMakeVisible*<br/>
Если true, указывает, что кадр должен стать видимым и активным. Если FALSE, то никакие выходцы не сделаны видимыми.

### <a name="remarks"></a>Remarks

Это приводит к тому, что `OnInitialUpdate` все представления в окне кадра принимают их вызовы.

Кроме того, если ранее не было активного представления, основное представление окна кадра становится активным. Основным представлением является представление с идентификатором AFX_IDW_PANE_FIRST. Наконец, окно кадра становится видимым, если *bMakeVisible* является ненулевым. Если *bMakeVisible* раста0 0, текущее состояние и видимое состояние окна кадра останутся неизменными. Нет необходимости называть эту функцию при использовании реализации платформы File New и File Open.

## <a name="cframewndinmodalstate"></a><a name="inmodalstate"></a>CFrameWnd::InModalState

Вызов ифункции этого участника, чтобы проверить, является ли окно кадра модальным или безмодным.

```
BOOL InModalState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если да; в противном случае 0.

## <a name="cframewndistracking"></a><a name="istracking"></a>CFrameWnd::IsTracking

Вызовите эту функцию участника, чтобы определить, перемещается ли в настоящее время панель сплиттера в окне.

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция сплиттера продолжается; в противном случае 0.

## <a name="cframewndloadacceltable"></a><a name="loadacceltable"></a>CFrameWnd::LoadAccelTable

Вызов для загрузки указанной таблицы ускорителя.

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Определяет название ресурса ускорителя. Используйте MAKEINTRESOURCE, если ресурс идентифицирован с идентификатором.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если таблица ускорителя была успешно загружена; в противном случае 0.

### <a name="remarks"></a>Remarks

Загружается только одна таблица.

Таблицы ускорителей, загруженные из ресурсов, высвобождаются автоматически при завершении работы приложения.

Если вы `LoadFrame` призываете создать окно кадра, фреймворк загружает таблицу акселератора вместе с ресурсами меню и значка, и последующий вызов этой функции элемента будет ненужным.

## <a name="cframewndloadbarstate"></a><a name="loadbarstate"></a>CFrameWnd::LoadBarState

Вызовите эту функцию для восстановления параметров каждой панели управления, принадлежащей окну кадра.

```
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
Название раздела в файле инициализации (INI) или ключа в реестре Windows, где хранится государственная информация.

### <a name="remarks"></a>Remarks

Восстановленная информация включает в себя видимость, горизонтальную/вертикальную ориентацию, состояние стыковки и положение панели управления.

Настройки, которые необходимо восстановить, должны быть занесена в реестр перед вызовом. `LoadBarState` Напишите информацию в реестр, позвонив [в CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Напишите информацию в файл INI, позвонив [в SaveBarState](#savebarstate).

## <a name="cframewndloadframe"></a><a name="loadframe"></a>CFrameWnd::LoadFrame

Вызов динамически создать окно кадра из информации о ресурсах.

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*nIDResource*<br/>
Идентификатор общих ресурсов, связанных с окном кадра.

*dwDefaultStyle*<br/>
[Стиль](../../mfc/reference/styles-used-by-mfc.md#window-styles)кадра . Включите FWS_ADDTOTITLE стиль, если вы хотите, чтобы заголовок бар автоматически отображать имя документа, представленного в окне.

*pParentWnd*<br/>
Указатель на родителей кадра.

*pContext*<br/>
Указатель на структуру [CCreateContext.](../../mfc/reference/ccreatecontext-structure.md) Этот параметр может быть NULL.

### <a name="remarks"></a>Remarks

Постройте `CFrameWnd` объект в два этапа. Сначала вызвать конструктор, который строит `CFrameWnd` объект, а затем `LoadFrame`вызвать, который загружает окно кадра Windows `CFrameWnd` и связанные с ними ресурсы и прикрепляет окно кадра к объекту. Параметр *nIDResource* определяет меню, таблицу акселератора, значок и строковой ресурс заголовка для окна кадра.

Используйте `Create` функцию `LoadFrame` участника, а не когда требуется указать все параметры создания окна кадра.

Фрейм `LoadFrame` вызывается при создает окно кадра с помощью объекта шаблона документа.

Фрейм использует аргумент *pContext* для указания объектов, которые будут подключены к окну кадра, включая любые содержащиеся объекты представления. Вы можете установить аргумент *pContext* `LoadFrame`на NULL при вызове.

## <a name="cframewndm_bautomenuenable"></a><a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable

Когда этот элемент данных включен (который по умолчанию), элементы меню, которые не имеют ON_UPDATE_COMMAND_UI или ON_COMMAND обработчики будут автоматически отключены, когда пользователь снимает меню.

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>Remarks

Элементы меню, которые имеют обработчик ON_COMMAND но не обработчик ON_UPDATE_COMMAND_UI будет автоматически включен.

При установке этого элемента данных элементы меню автоматически приводятся в действие таким же образом, как и кнопки панели инструментов.

> [!NOTE]
> `m_bAutoMenuEnable`не влияет на пункты меню верхнего уровня.

Этот элемент данных упрощает реализацию дополнительных команд на основе текущего выбора и уменьшает необходимость записи ON_UPDATE_COMMAND_UI обработчиков для включения и отключения элементов меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

## <a name="cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a>CFrameWnd::ПереговорыBorderSpace

Вызовите эту функцию участника для согласования пограничного пространства в окне кадра во время активации OLE inplace.

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>Параметры

*nBorderCmd*<br/>
Содержит одно из следующих `enum BorderCmd`значений из:

- `borderGet` = 1

- `borderRequest` = 2

- `borderSet` = 3

*lpRectBorder*<br/>
Указатель на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) который определяет координаты границы.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена `CFrameWnd` является осуществление OLE переговоров пространства границы.

## <a name="cframewndonbarcheck"></a><a name="onbarcheck"></a>CFrameWnd::OnBarCheck

Вызывается всякий раз, когда действие выполняется на указанной панели управления.

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Отображается идентификатор панели управления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если контрольная планка существовала; в противном случае 0.

## <a name="cframewndoncontexthelp"></a><a name="oncontexthelp"></a>CFrameWnd::OnContextHelp

Ручки SHIFT-F1 Справка для на месте элементов.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Remarks

Для включения чувствительной к контексту помощи необходимо добавить

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

заявление на `CFrameWnd` карту сообщений класса, а также добавить запись таблицы акселератора, как правило, SHIFT-F1, чтобы включить эту функцию участника.

Если ваше приложение является `OnContextHelp` контейнером OLE, все элементы, содержащиеся в объекте окна кадра, переходят в режим справки. Курсор изменяется на стрелку и вопросительный знак, и пользователь может переместить указатель мыши и нажать левую кнопку мыши, чтобы выбрать диалоговую кнопку, окно, меню или кнопку команды. Эта функция члена вызывает `WinHelp` функцию Windows с контекстом справки объекта под курсором.

## <a name="cframewndoncreateclient"></a><a name="oncreateclient"></a>CFrameWnd::OnCreateClient

Вызывается рамки во время `OnCreate`исполнения .

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Параметры

*lpcs*<br/>
Указатель на структуру Windows [CREATESTRUCT.](/windows/win32/api/winuser/ns-winuser-createstructw)

*pContext*<br/>
Указатель на структуру [CCreateContext.](../../mfc/reference/ccreatecontext-structure.md)

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Никогда не называйте эту функцию.

Реализация этой функции по `CView` умолчанию создает объект из информации, представленной в *pContext,* если это возможно.

Переопределить эту функцию, чтобы переопределить значения, передаваемые в `CCreateContext` объекте, или изменить способ создания элементов управления в основной клиентской области окна кадра. Участники, `CCreateContext` которых вы можете переопределить, описаны в классе [CCreateContext.](../../mfc/reference/ccreatecontext-structure.md)

> [!NOTE]
> Не заменяйте значения, `CREATESTRUCT` передаваемые в структуре. Они только для информационного использования. Например, если вы хотите переопределить начальный прямоугольник окна, переопределить функцию `CWnd` участника [PreCreateWindow.](../../mfc/reference/cwnd-class.md#precreatewindow)

## <a name="cframewndonhidemenubar"></a><a name="onhidemenubar"></a>CFrameWnd::OnHideMenuBar

Эта функция вызывается, когда система собирается скрыть панель меню в текущем приложении MFC.

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>Remarks

Этот обработчик событий позволяет приложению выполнять пользовательские действия, когда система собирается скрыть меню. Нельзя предотвратить скрытие меню, но можно, например, вызвать другие методы для получения стиля или состояния меню.

## <a name="cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CFrameWnd::OnSetPreviewMode

Вызов этой функции-члена переключает окно главного фрейма приложения в режим предварительного просмотра и из него.

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>Параметры

*bPreview*<br/>
Определяет, следует ли размещать приложение в режиме предварительного просмотра. Установить, чтобы TRUE разместить в печати предварительного просмотра, FALSE отменить режим предварительного просмотра.

*pState*<br/>
Указатель на `CPrintPreviewState` структуру.

### <a name="remarks"></a>Remarks

Реализация по умолчанию отстраняет все стандартные панели инструментов и скрывает главное меню и основное клиентское окно. Это превращает окна рамки MDI во временные окна рамки SDI.

Переопределить эту функцию участника, чтобы настроить скрытие и отображение баров управления и других частей окна кадра во время предварительного просмотра печати. Вызовите реализацию базового класса из переочерденной версии.

## <a name="cframewndonshowmenubar"></a><a name="onshowmenubar"></a>CFrameWnd::OnShowMenuBar

Эта функция вызывается, когда система собирается отображать панель меню в текущем приложении MFC.

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>Remarks

Этот обработчик событий позволяет приложению выполнять пользовательские действия, когда меню вот-вот будет отображено. Нельзя предотвратить отображение меню, но можно, например, вызвать другие методы для получения стиля или состояния меню.

## <a name="cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a>CFrameWnd::OnUpdateControlBarMenu

Вызывается в рамках при обновлении связанного меню.

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на объект [CCmdUI,](../../mfc/reference/ccmdui-class.md) представляющий меню, генерирующее команду обновления. Обработчик обновления [Enable](../../mfc/reference/ccmdui-class.md#enable) вызывает функцию `CCmdUI` пользователя Enable через *pCmdUI* для обновления пользовательского интерфейса.

## <a name="cframewndrecalclayout"></a><a name="recalclayout"></a>CFrameWnd::RecalcLayout

Вызывается фреймворком при переключаемых стандартных батончиках управления или при повторном размере окна кадра.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Параметры

*bNotify*<br/>
Определяет, получает ли активный элемент на месте для окна кадра уведомление об изменении макета. Если true, элемент уведомляется; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Реализация этой функции элемента `CWnd` по `RepositionBars` умолчанию вызывает функцию участника для переориентации всех баров `CView` управления в кадре, а также в главном клиентском окне (обычно или MDICLIENT).

Переизвейдиэту функцию элемента для управления внешним видом и поведением баров управления после изменения макета окна кадра. Например, позвоните ему при включании или выключении баров управления или добавляете еще одну панель управления.

## <a name="cframewndrectdefault"></a><a name="rectdefault"></a>CFrameWnd::rectDefault

Передайте `CRect` эту статичную в качестве параметра при создании окна, чтобы позволить Windows выбрать первоначальный размер окна и положение.

```
static AFX_DATA const CRect rectDefault;
```

## <a name="cframewndsavebarstate"></a><a name="savebarstate"></a>CFrameWnd::SaveBarState

Вызов ими функции для хранения информации о каждой панели управления, принадлежащей окну кадра.

```
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
Название раздела в файле инициализации или ключа в реестре Windows, где хранится государственная информация.

### <a name="remarks"></a>Remarks

Эта информация может быть прочитана из файла инициализации с помощью [LoadBarState](#loadbarstate). Сохраненная информация включает в себя видимость, горизонтальную/вертикальную ориентацию, состояние стыковки и положение панели управления.

## <a name="cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a>CFrameWnd::SetActivePreviewView

Обозначает указанное представление как активное представление для Rich Preview.

```
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>Параметры

*pViewNew*<br/>
Указатель на представление, подносивще ею.

### <a name="remarks"></a>Remarks

## <a name="cframewndsetactiveview"></a><a name="setactiveview"></a>CFrameWnd::SetActiveView

Вызовите эту функцию участника, чтобы установить активное представление.

```
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Параметры

*pViewNew*<br/>
Укажите указатель на объект [CView](../../mfc/reference/cview-class.md) или NULL без активного просмотра.

*bNotify*<br/>
Определяет, следует ли уведомлять представление об активации. Если true, `OnActivateView` называется для нового мнения; если FALSE, это не так.

### <a name="remarks"></a>Remarks

Платформа будет вызывать эту функцию автоматически, поскольку пользователь изменяет фокус на представление в окне кадра. Можно явно призвать `SetActiveView` изменить фокус на указанное представление.

## <a name="cframewndsetdockstate"></a><a name="setdockstate"></a>CFrameWnd::SetDockState

Вызовите эту функцию участника, `CDockState` чтобы применить информацию состояния, хранящуюся в объекте, к барам управления окна кадра.

```
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>Параметры

*Государства*<br/>
Примените сохраненное состояние к барам управления окна кадра.

### <a name="remarks"></a>Remarks

Для восстановления предыдущего состояния баров управления можно загрузить `CDockState::LoadState` `Serialize`сохраненное `SetDockState` состояние или использовать его для нанесения его на панели управления окна кадра. Предыдущее состояние хранится `CDockState` в объекте с`GetDockState`

## <a name="cframewndsetmenubarstate"></a><a name="setmenubarstate"></a>CFrameWnd::SetMenuBarState

Устанавливает состояние отображения меню в текущем приложении MFC для скрытых или отображаемых.

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*nState*|(в) Определяет, отображать или скрывать меню. Параметр *nState* может иметь следующие значения:<br /><br />- AFX_MBS_VISIBLE (0x01) - Отображает меню, если оно скрыто, но не имеет эффекта, если оно видно.<br />- AFX_MBS_HIDDEN (0x02) - скрывает меню, если оно видно, но не имеет эффекта, если оно скрыто.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод успешно меняет состояние меню; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

При возникновении ошибки во времени выполнения этот метод утверждается в режиме Debug и вызывает исключение, полученное из класса [CException.](../../mfc/reference/cexception-class.md)

## <a name="cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a>CFrameWnd::SetMenuBarВидимость

Устанавливает поведение меню по умолчанию в текущем приложении MFC, чтобы быть скрытым или видимым.

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*nStyle*|(в) Определяет, скрыто ли меню по умолчанию, или оно видно и имеет фокус. Параметр *nStyle* может иметь следующие значения:<br /><br />- AFX_MBV_KEEPVISIBLE (0x01) -<br />     Меню отображается в любое время, и по умолчанию не имеет фокуса.<br />- AFX_MBV_DISPLAYONFOCUS (0x02) -<br />     Меню скрыто по умолчанию. Если меню скрыто, нажмите на ключ ALT, чтобы отобразить меню и придать ему фокус. Если меню отображается, нажмите на ключ ALT или ESC, чтобы скрыть меню.<br />- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (bitwise комбинация (OR)) - Меню скрыто по умолчанию. Если меню скрыто, нажмите клавишу F10, чтобы отобразить меню и придать ему фокус. Если меню отображается, нажмите клавишу F10, чтобы переключить фокус на или вне меню. Меню отображается до тех пор, пока вы не нажмете на ключ ALT или ESC, чтобы скрыть его.|

### <a name="remarks"></a>Remarks

Если значение параметра *nStyle* недействительно, этот метод утверждается в режиме Debug и повышает [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) в режиме выпуска. В случае других ошибок выполнения этот метод утверждается в режиме Debug и вызывает исключение, полученное из класса [CException.](../../mfc/reference/cexception-class.md)

Этот метод влияет на состояние меню в приложениях, написанных для Windows Vista и позже.

## <a name="cframewndsetmessagetext"></a><a name="setmessagetext"></a>CFrameWnd::SetMessageText

Вызовите эту функцию, чтобы поместить строку в панели status-bar, которая имеет идентификатор 0.

```
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указывает на строку, которая будет размещена на строке статуса.

*nID*<br/>
Идентификатор строки строки, которая будет размещена на строке состояния.

### <a name="remarks"></a>Remarks

Это, как правило, самое левое и самое длинное, панель статуса.

## <a name="cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a>CFrameWnd::SetProgressBarPosition

Устанавливает текущее положение панели выполнения Windows 7, отображаемый на панели задач.

```
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Параметры

*nProgressPos*<br/>
Определяет положение для настройки. Он должен находиться в `SetProgressBarRange`пределах диапазона, установленного .

### <a name="remarks"></a>Remarks

## <a name="cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a>CFrameWnd::SetProgressBarRange

Устанавливает диапазон для панели прогресса Windows 7, отображаемый на панели задач.

```
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Параметры

*nRangeMin*<br/>
Минимальное значение.

*nRangeMax*<br/>
Максимальная ценность.

### <a name="remarks"></a>Remarks

## <a name="cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a>CFrameWnd::SetProgressBarState

Устанавливает тип и состояние индикатора прогресса, отображаемого на кнопке панели задач.

```
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>Параметры

*tbpFlags*<br/>
Флаги, контролирующие текущее состояние кнопки «Прогресс». Укажите только один из следующих флагов, потому что все государства являются взаимоисключающими: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.

### <a name="remarks"></a>Remarks

## <a name="cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a>CFrameWnd::SetTaskbarOverlayIcon

Перегружен. Применяет наложение на кнопку панели задач, чтобы указать статус приложения или уведомить пользователя.

```
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,
    LPCTSTR lpcszDescr);

BOOL SetTaskbarOverlayIcon(
    HICON hIcon,
    LPCTSTR lpcszDescr);
```

### <a name="parameters"></a>Параметры

*nIDResource*<br/>
Упогоняет идентификатор значка ресурса для использования в качестве наложения. Подробнее о *hIcon* смотрите.

*lpcszDescr*<br/>
Указатель на строку, которая обеспечивает альт текстовую версию информации, передаваемые наложением, для целей доступности.

*hIcon*<br/>
Ручка значка для использования в качестве наложения. Это должен быть небольшой значок, размером 16x16 пикселей при 96 точках на дюйм (dpi). Если значок наложения уже применен к кнопке панели задач, существующая накладка заменяется. Это значение может быть NULL. Способ обработки значения NULL зависит от того, представляет ли кнопка панели задач одно окно или группу окон. Это ответственность вызова приложения для свободного *hIcon,* когда он больше не нужен.

### <a name="return-value"></a>Возвращаемое значение

TRUE в случае успеха; FALSE, если версия ОС меньше, чем Windows 7 или если происходит ошибка настройки значка.

### <a name="remarks"></a>Remarks

## <a name="cframewndsettitle"></a><a name="settitle"></a>CFrameWnd::SetTitle

Устанавливает название объекта окна.

```
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Параметры

*lpszНазвание*<br/>
Указатель на строку символов, содержащую название объекта окна.

## <a name="cframewndshowcontrolbar"></a><a name="showcontrolbar"></a>CFrameWnd::ShowControlBar

Вызов исчерпнивите эту функцию участника, чтобы показать или скрыть панель управления.

```
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
Указатель на панель управления, чтобы быть показаны или скрыты.

*bShow*<br/>
Если true, указывает, что панель управления должна быть показана. Если FALSE, указывает, что панель управления должна быть скрытой.

*bDelay*<br/>
Если true, задержка отображения панели управления. Если FALSE, немедленно откажите сьюнд-бар управления.

## <a name="cframewndshowownedwindows"></a><a name="showownedwindows"></a>CFrameWnd::ShowOwnedWindows

Вызов исчерпнивите эту функцию участника, чтобы показать все окна, которые являются потомками `CFrameWnd` объекта.

```
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Уточняется, должны ли быть показаны или скрыты принадлежащие окна.

## <a name="see-also"></a>См. также раздел

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)<br/>
[Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Структура CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)
