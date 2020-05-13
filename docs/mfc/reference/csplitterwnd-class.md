---
title: Класс CSplitterWnd
ms.date: 11/04/2016
f1_keywords:
- CSplitterWnd
- AFXEXT/CSplitterWnd
- AFXEXT/CSplitterWnd::CSplitterWnd
- AFXEXT/CSplitterWnd::ActivateNext
- AFXEXT/CSplitterWnd::CanActivateNext
- AFXEXT/CSplitterWnd::Create
- AFXEXT/CSplitterWnd::CreateScrollBarCtrl
- AFXEXT/CSplitterWnd::CreateStatic
- AFXEXT/CSplitterWnd::CreateView
- AFXEXT/CSplitterWnd::DeleteColumn
- AFXEXT/CSplitterWnd::DeleteRow
- AFXEXT/CSplitterWnd::DeleteView
- AFXEXT/CSplitterWnd::DoKeyboardSplit
- AFXEXT/CSplitterWnd::DoScroll
- AFXEXT/CSplitterWnd::DoScrollBy
- AFXEXT/CSplitterWnd::GetActivePane
- AFXEXT/CSplitterWnd::GetColumnCount
- AFXEXT/CSplitterWnd::GetColumnInfo
- AFXEXT/CSplitterWnd::GetPane
- AFXEXT/CSplitterWnd::GetRowCount
- AFXEXT/CSplitterWnd::GetRowInfo
- AFXEXT/CSplitterWnd::GetScrollStyle
- AFXEXT/CSplitterWnd::IdFromRowCol
- AFXEXT/CSplitterWnd::IsChildPane
- AFXEXT/CSplitterWnd::IsTracking
- AFXEXT/CSplitterWnd::RecalcLayout
- AFXEXT/CSplitterWnd::SetActivePane
- AFXEXT/CSplitterWnd::SetColumnInfo
- AFXEXT/CSplitterWnd::SetRowInfo
- AFXEXT/CSplitterWnd::SetScrollStyle
- AFXEXT/CSplitterWnd::SplitColumn
- AFXEXT/CSplitterWnd::SplitRow
- AFXEXT/CSplitterWnd::OnDraw
- AFXEXT/CSplitterWnd::OnDrawSplitter
- AFXEXT/CSplitterWnd::OnInvertTracker
helpviewer_keywords:
- CSplitterWnd [MFC], CSplitterWnd
- CSplitterWnd [MFC], ActivateNext
- CSplitterWnd [MFC], CanActivateNext
- CSplitterWnd [MFC], Create
- CSplitterWnd [MFC], CreateScrollBarCtrl
- CSplitterWnd [MFC], CreateStatic
- CSplitterWnd [MFC], CreateView
- CSplitterWnd [MFC], DeleteColumn
- CSplitterWnd [MFC], DeleteRow
- CSplitterWnd [MFC], DeleteView
- CSplitterWnd [MFC], DoKeyboardSplit
- CSplitterWnd [MFC], DoScroll
- CSplitterWnd [MFC], DoScrollBy
- CSplitterWnd [MFC], GetActivePane
- CSplitterWnd [MFC], GetColumnCount
- CSplitterWnd [MFC], GetColumnInfo
- CSplitterWnd [MFC], GetPane
- CSplitterWnd [MFC], GetRowCount
- CSplitterWnd [MFC], GetRowInfo
- CSplitterWnd [MFC], GetScrollStyle
- CSplitterWnd [MFC], IdFromRowCol
- CSplitterWnd [MFC], IsChildPane
- CSplitterWnd [MFC], IsTracking
- CSplitterWnd [MFC], RecalcLayout
- CSplitterWnd [MFC], SetActivePane
- CSplitterWnd [MFC], SetColumnInfo
- CSplitterWnd [MFC], SetRowInfo
- CSplitterWnd [MFC], SetScrollStyle
- CSplitterWnd [MFC], SplitColumn
- CSplitterWnd [MFC], SplitRow
- CSplitterWnd [MFC], OnDraw
- CSplitterWnd [MFC], OnDrawSplitter
- CSplitterWnd [MFC], OnInvertTracker
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
ms.openlocfilehash: a872854af1695b8b2b347b21d73165d259b3a986
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753062"
---
# <a name="csplitterwnd-class"></a>Класс CSplitterWnd

Предоставляет функциональные возможности окна-разделителя, то есть окна, содержащего несколько областей.

## <a name="syntax"></a>Синтаксис

```
class CSplitterWnd : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Вызов для `CSplitterWnd` построения объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSplitterWnd::ActivateNext](#activatenext)|Выполняет команду Next Pane или Previous Pane.|
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Проверка, возможно ли в настоящее время следующая команда Pane или Previous Pane.|
|[CSplitterWnd::Создание](#create)|Вызов для создания динамического окна сплиттера и прикрепить его к объекту. `CSplitterWnd`|
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Создает общий элемент управления панелью прокрутки.|
|[CSplitterWnd::CreateStatic](#createstatic)|Вызов для создания статического окна сплиттера и прикрепить его к объекту. `CSplitterWnd`|
|[CSplitterWnd::CreateView](#createview)|Вызов для создания панели в окне сплиттера.|
|[CSplitterWnd::DeleteColumn](#deletecolumn)|Удаляет столбец из окна сплиттера.|
|[CSplitterWnd::DeleteRow](#deleterow)|Удаляет строку из окна сплиттера.|
|[CSplitterWnd::DeleteView](#deleteview)|Удаляет представление из окна сплиттера.|
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Выполняет команду сплита клавиатуры, как правило, "Окно Сплит".|
|[CSplitterWnd::DoScroll](#doscroll)|Выполняет синхронизированную прокрутку разделенных окон.|
|[CSplitterWnd::DoScrollBy](#doscrollby)|Свитки разбивают окна на определенное количество пикселей.|
|[CSplitterWnd::GetActivePane](#getactivepane)|Определяет активное стекло от фокуса или активного представления в кадре.|
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Возвращает текущее количество столбцов панели.|
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Возвращает информацию в указанную колонку.|
|[CSplitterWnd::GetPane](#getpane)|Возвращает панель в указанном ряду и столбце.|
|[CSplitterWnd::GetRowCount](#getrowcount)|Возвращает текущее количество строк панели панели.|
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Возвращает информацию в указанную строку.|
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Возвращает общий стиль прокрутки-бар.|
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Возвращает идентификатор окна окна окна панели в указанном ряду и столбце.|
|[CSplitterWnd::IsChildPane](#ischildpane)|Позвоните, чтобы определить, является ли окно в настоящее время детским стеклом этого окна сплиттера.|
|[CSplitterWnd::IsTracking](#istracking)|Определяет, перемещается ли бар сплиттера.|
|[CSplitterWnd::RecalcLayout](#recalclayout)|Вызов для повторного отображения окна сплиттера после регулировки размера строки или столбца.|
|[CSplitterWnd::SetActivePane](#setactivepane)|Устанавливает панель, чтобы быть активным в кадре.|
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Звоните, чтобы установить указанную информацию о столбце.|
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Звоните, чтобы установить указанную информацию о строке.|
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Определяет новый стиль прокрутки-бара для общей поддержки сплиттера окна прокрутки-бара.|
|[CSplitterWnd::SplitColumn](#splitcolumn)|Указывает, где окно кадра расщепляется вертикально.|
|[CSplitterWnd::SplitRow](#splitrow)|Указывает, где окно кадра расколается горизонтально.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CSplitterWnd::OnDraw](#ondraw)|Вызывается по фреймворку, чтобы нарисовать окно сплиттера.|
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Рендеризирует изображение разделенного окна.|
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Отобразит изображение разделенного окна таким же размером и формой, как окно рамы.|

## <a name="remarks"></a>Remarks

Панель обычно является объектом, специфичным для приложения, полученным из [CView,](../../mfc/reference/cview-class.md)но это может быть любой объект [CWnd,](../../mfc/reference/cwnd-class.md) который имеет соответствующий идентификатор окна ребенка.

Объект `CSplitterWnd` обычно встраивается в родительский объект [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIChildWnd.](../../mfc/reference/cmdichildwnd-class.md) Создание `CSplitterWnd` объекта с помощью следующих шагов:

1. Встраиваем переменную `CSplitterWnd` члена в родительский кадр.

2. Переизвейдите функцию члена родительского кадра [CFrameWnd::OnCreateClient.](../../mfc/reference/cframewnd-class.md#oncreateclient)

3. `OnCreateClient`Из переверненных, вызов [создать](#create) или [CreateStatic](#createstatic) функции `CSplitterWnd`члена .

Вызов `Create` функции участника для создания динамического окна сплиттера. Динамическое окно сплиттера обычно используется для создания и прокрутки нескольких отдельных стекол или представлений одного и того же документа. Платформа автоматически создает исходное стекло для сплиттера; затем фреймворк создает, изменяет и распоряжается дополнительными стеклами при управлении окном сплиттера.

При вызове `Create`вы указываете минимальную высоту строки и ширину столбца, которые определяют, когда стекла слишком малы, чтобы быть полностью отображены. После вызова `Create`вы можете настроить эти минимумы, позвонив в функции участника [SetColumnInfo](#setcolumninfo) и [SetRowInfo.](#setrowinfo)

Также используйте `SetRowInfo` функции и функции `SetColumnInfo` члена, чтобы установить "идеальную" ширину для столбца и "идеальную" высоту для ряда. Когда фреймвор отображает окно сплиттера, он сначала отображает родительский кадр, а затем окно сплиттера. Затем фреймворк выкладывает стекла в столбцы и строки в соответствии с их идеальными размерами, работая от верхнего левого до нижнего правого угла клиентской зоны окна сплиттера.

Все стекла в динамическом окне сплиттера должны быть одного класса. Знакомые приложения, поддерживающие динамические окна сплиттера, включают Microsoft Word и Microsoft Excel.

Используйте `CreateStatic` функцию члена для создания статического окна сплиттера. Пользователь может изменять только размер стекол в статичном окне сплиттера, а не их количество или порядок.

При создании статического сплиттера необходимо создать все стекла статического сплиттера. Убедитесь, что вы создаете все панели `OnCreateClient` перед возвращением функции родительского кадра, или фреймворк не будет отображать окно правильно.

Функция `CreateStatic` члена автоматически инициирует статический сплиттер с минимальной высотой строки и шириной столбца 0. После вызова `Create`отрегулируйте эти минимумы, позвонив в функции участника [SetColumnInfo](#setcolumninfo) и [SetRowInfo.](#setrowinfo) Также `SetColumnInfo` используйте `SetRowInfo` и `CreateStatic` после вызова, чтобы указать желаемые идеальные размеры панели.

Отдельные стекла статического сплиттера часто относятся к разным классам. Примеры статических окон сплиттера смотрите графический редактор и менеджер файлов Windows.

Окно сплиттера поддерживает специальные бары прокрутки (кроме баров прокрутки, которые могут иметь стекла). Эти полоски прокрутки являются дочерними детьми `CSplitterWnd` объекта и являются общими с стеклами.

Вы создаете эти специальные бары прокрутки при создании окна сплиттера. Например, `CSplitterWnd` в одном ряду, двух столбцах и WS_VSCROLL стиле будет отображаться вертикальная панель прокрутки, которая разделяется двумя стеклами. Когда пользователь перемещает панель прокрутки, WM_VSCROLL сообщения отправляются на обе панели. Когда панели устанавливают положение панели прокрутки, устанавливается общая панель прокрутки.

Для получения дополнительной информации о окнах сплиттера [см.](../../mfc/tn029-splitter-windows.md)

Для получения дополнительной информации о том, как создать динамические окна сплиттера, см.:

- MFC образец [Scribble](../../overview/visual-cpp-samples.md)

- MFC образец [VIEWEX](../../overview/visual-cpp-samples.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSplitterWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="csplitterwndactivatenext"></a><a name="activatenext"></a>CSplitterWnd::ActivateNext

Вызывается по системе для выполнения следующего pane или Previous Pane команды.

```
virtual void ActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Параметры

*bPrev*<br/>
Указывает, какое окно активировать. **TRUE** для предыдущих; **FALSE** для следующего.

### <a name="remarks"></a>Remarks

Эта функция —это команда высокого уровня, которая используется классом `CSplitterWnd` [CView](../../mfc/reference/cview-class.md) для делегирования реализации.

## <a name="csplitterwndcanactivatenext"></a><a name="canactivatenext"></a>CSplitterWnd::CanActivateNext

Вызывается по системе, чтобы проверить, если следующая панель или Предыдущий Pane команда в настоящее время возможно.

```
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>Параметры

*bPrev*<br/>
Указывает, какое окно активировать. **TRUE** для предыдущих; **FALSE** для следующего.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция —это команда высокого уровня, которая используется классом `CSplitterWnd` [CView](../../mfc/reference/cview-class.md) для делегирования реализации.

## <a name="csplitterwndcreate"></a><a name="create"></a>CSplitterWnd::Создание

Чтобы создать динамическое окно `Create` сплиттера, позвоните функции участника.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    int nMaxRows,
    int nMaxCols,
    SIZE sizeMin,
    CCreateContext* pContext,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_HSCROLL | WS_VSCROLL | SPLS_DYNAMIC_SPLIT,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Родительское окно кадра окна сплиттера.

*nMaxRows*<br/>
Максимальное количество строк в окне сплиттера. Это значение не должно превышать 2.

*nMaxCols*<br/>
Максимальное количество столбцов в окне сплиттера. Это значение не должно превышать 2.

*sizeMin*<br/>
Определяет минимальный размер, при котором может отображаться панель.

*pContext*<br/>
Указатель на структуру [CCreateContext.](../../mfc/reference/ccreatecontext-structure.md) В большинстве случаев это может быть *pContext,* передаваемый в окно родительской рамы.

*dwStyle*<br/>
Определяет стиль окна.

*nID*<br/>
Идентификатор окна ребенка окна. Идентификатор может быть AFX_IDW_PANE_FIRST, если окно сплиттера не вложено в другое окно сплиттера.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Вы можете вставить в родительский `CSplitterWnd` объект [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIChildWnd,](../../mfc/reference/cmdichildwnd-class.md) предприняв следующие шаги:

1. Встраиваем переменную `CSplitterWnd` члена в родительский кадр.

1. Переизвейдите функцию члена родительского кадра [CFrameWnd::OnCreateClient.](../../mfc/reference/cframewnd-class.md#oncreateclient)

1. Вызов `Create` функции участника из `OnCreateClient`перезаверженных .

При создании окна сплиттера из родительского кадра передайте параметр *pContext* родительской frame в окно сплиттера. В противном случае этот параметр может быть NULL.

Начальная минимальная высота строки и ширина столбца динамического окна сплиттера устанавливаются параметром *размера.* Эти минимумы, определяющие, слишком ли стекло для отображаемого в полном объеме, могут быть изменены с помощью функций участника [SetRowInfo](#setrowinfo) и [SetColumnInfo.](#setcolumninfo)

Подробнее о динамических окнах сплиттера см. [Multiple Document Types, Views, and Frame Windows](../../mfc/multiple-document-types-views-and-frame-windows.md) [Technical Note 29](../../mfc/tn029-splitter-windows.md) `CSplitterWnd`

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

## <a name="csplitterwndcreatescrollbarctrl"></a><a name="createscrollbarctrl"></a>CSplitterWnd::CreateScrollBarCtrl

Вызывается инфраструктурой для создания общего управления панелью прокрутки.

```
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль окна.

*nID*<br/>
Идентификатор окна ребенка окна. Идентификатор может быть AFX_IDW_PANE_FIRST, если окно сплиттера не вложено в другое окно сплиттера.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Переопределение, `CreateScrollBarCtrl` включаввв дополнительное элементы управления рядом с баром прокрутки. Поведение по умолчанию заключается в создании нормального управления панелью прокрутки Windows.

## <a name="csplitterwndcreatestatic"></a><a name="createstatic"></a>CSplitterWnd::CreateStatic

Чтобы создать статическое окно сплиттера, позвоните функции `CreateStatic` участника.

```
virtual BOOL CreateStatic(
    CWnd* pParentWnd,
    int nRows,
    int nCols,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Родительское окно кадра окна сплиттера.

*nRows*<br/>
Количество строк. Это значение не должно превышать 16.

*nКолс*<br/>
Количество столбцов. Это значение не должно превышать 16.

*dwStyle*<br/>
Определяет стиль окна.

*nID*<br/>
Идентификатор окна ребенка окна. Идентификатор может быть AFX_IDW_PANE_FIRST, если окно сплиттера не вложено в другое окно сплиттера.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

A `CSplitterWnd` обычно встраивается в родительский `CFrameWnd` объект или объект [CMDIChildWnd,](../../mfc/reference/cmdichildwnd-class.md) предпринимая следующие шаги:

1. Встраиваем переменную `CSplitterWnd` члена в родительский кадр.

1. Переопределить функцию члена `OnCreateClient` родительского кадра.

1. Позвоните `CreateStatic` функции участника из перекрытого [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).

Статическое окно сплиттера содержит фиксированное количество стекол, часто из разных классов.

При создании статического окна сплиттера необходимо одновременно создать все его стекла. Функция члена [CreateView](#createview) обычно используется для этой цели, но вы можете создавать и другие классы без просмотра.

Начальная минимальная высота строки и ширина столбца для статического окна сплиттера расшаты расшаты 0. Эти минимумы, определяющие, когда панель слишком мала, чтобы быть показана в полном объеме, могут быть изменены с помощью функций участника [SetRowInfo](#setrowinfo) и [SetColumnInfo.](#setcolumninfo)

Чтобы добавить бары прокрутки в статический сплиттер окна, добавить WS_HSCROLL и WS_VSCROLL стилей *dwStyle.*

См" Splitter Windows " в статье [Несколько типов документов, просмотров и кадров Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [Техническое примечание 29](../../mfc/tn029-splitter-windows.md), и обзор `CSplitterWnd` класса для получения дополнительной информации о статических окон сплиттера.

## <a name="csplitterwndcreateview"></a><a name="createview"></a>CSplitterWnd::CreateView

Создает стекла для статического окна сплиттера.

```
virtual BOOL CreateView(
    int row,
    int col,
    CRuntimeClass* pViewClass,
    SIZE sizeInit,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Параметры

*Строки*<br/>
Определяет строку окна сплиттера, в которой можно разместить новый вид.

*col*<br/>
Определяет столбец окна сплиттера, в котором можно разместить новый вид.

*pViewClass*<br/>
Определяет [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) нового представления.

*размерИИИИнит*<br/>
Определяет начальный размер нового представления.

*pContext*<br/>
Указатель на контекст создания, используемый для создания представления (обычно *pContext* передавался в переочерченную [cFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) функцию, в которой создается окно сплиттера).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Все стекла статического окна сплиттера должны быть созданы до того, как фреймворот отобразит сплиттер.

Платформа также вызывает функцию этого члена для создания новых стекол, когда пользователь динамического окна сплиттера разбивает панель, строку или столбец.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]

## <a name="csplitterwndcsplitterwnd"></a><a name="csplitterwnd"></a>CSplitterWnd::CSplitterWnd

Вызов для `CSplitterWnd` построения объекта.

```
CSplitterWnd();
```

### <a name="remarks"></a>Remarks

Постройте `CSplitterWnd` объект в два этапа. Сначала вызовите конструктор, который `CSplitterWnd` создает объект, а затем вызовите функцию члена [Create,](#create) `CSplitterWnd` которая создает окно сплиттера и прикрепляет его к объекту.

## <a name="csplitterwnddeletecolumn"></a><a name="deletecolumn"></a>CSplitterWnd::DeleteColumn

Удаляет столбец из окна сплиттера.

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>Параметры

*colDelete*<br/>
Уотек столбца для удаления.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается инфраструктурой для реализации логики динамического окна сплиттера (т.е. если окно сплиттера имеет SPLS_DYNAMIC_SPLIT стиль). Он может быть настроен, наряду с виртуальной функцией [CreateView](#createview), для реализации более продвинутых динамических сплиттеров.

## <a name="csplitterwnddeleterow"></a><a name="deleterow"></a>CSplitterWnd::DeleteRow

Удаляет строку из окна сплиттера.

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>Параметры

*rowDelete*<br/>
Уотек строки для удаления.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается инфраструктурой для реализации логики динамического окна сплиттера (т.е. если окно сплиттера имеет SPLS_DYNAMIC_SPLIT стиль). Он может быть настроен, наряду с виртуальной функцией [CreateView](#createview), для реализации более продвинутых динамических сплиттеров.

## <a name="csplitterwnddeleteview"></a><a name="deleteview"></a>CSplitterWnd::DeleteView

Удаляет представление из окна сплиттера.

```
virtual void DeleteView(
    int row,
    int col);
```

### <a name="parameters"></a>Параметры

*Строки*<br/>
Определяет строку окна сплиттера, при которой можно удалить представление.

*col*<br/>
Опознавательный столбец окна сплиттера, на котором можно удалить представление.

### <a name="remarks"></a>Remarks

Если активное представление удаляется, следующее представление станет активным. Реализация по умолчанию предполагает автоматическое удаление представления в [PostNcDestroy.](../../mfc/reference/cwnd-class.md#postncdestroy)

Эта функция члена вызывается инфраструктурой для реализации логики динамического окна сплиттера (т.е. если окно сплиттера имеет SPLS_DYNAMIC_SPLIT стиль). Он может быть настроен, наряду с виртуальной функцией [CreateView](#createview), для реализации более продвинутых динамических сплиттеров.

## <a name="csplitterwnddokeyboardsplit"></a><a name="dokeyboardsplit"></a>CSplitterWnd::DoKeyboardSplit

Выполняет команду сплита клавиатуры, как правило, "Окно Сплит".

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция —это команда высокого уровня, которая используется классом `CSplitterWnd` [CView](../../mfc/reference/cview-class.md) для делегирования реализации.

## <a name="csplitterwnddoscroll"></a><a name="doscroll"></a>CSplitterWnd::DoScroll

Выполняет синхронизированную прокрутку разделенных окон.

```
virtual BOOL DoScroll(
    CView* pViewFrom,
    UINT nScrollCode,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Параметры

*pViewFrom*<br/>
Указатель на представление, из которого происходит прокрутка сообщения.

*nScrollCode*<br/>
Код прокрутки-бар, указывающий запрос на прокрутку пользователя. Этот параметр состоит из двух частей: низкоупорядоченного байта, определяющего тип прокрутки, происходящих горизонтально, и байта высокого порядка, который определяет тип прокрутки, происходящий вертикально:

- SB_BOTTOM свитки внизу.

- SB_LINEDOWN прокручивает одну строку вниз.

- SB_LINEUP прокручивает одну линию.

- SB_PAGEDOWN прокручивает одну страницу вниз.

- SB_PAGEUP прокручивает одну страницу вверх.

- SB_TOP свитки сверху.

*bDoScroll*<br/>
Определяет, происходит ли указанное действие прокрутки. Если *bDoScroll* является правдой (т.е. если окно ребенка существует, и если разделенные окна имеют диапазон прокрутки), то указанное действие прокрутки может иметь место; если *bDoScroll* false (т.е. если не существует окна ребенка, или разделенные представления не имеют диапазона прокрутки), то прокрутка не происходит.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если происходит синхронизированная прокрутка; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается инфраструктурой для выполнения синхронизированной прокрутки разделенных окон, когда представление получает сообщение прокрутки. Переопределение, требующее действия пользователя, прежде чем будет разрешена синхронизация прокрутки.

## <a name="csplitterwnddoscrollby"></a><a name="doscrollby"></a>CSplitterWnd::DoScrollBy

Свитки разбивают окна на определенное количество пикселей.

```
virtual BOOL DoScrollBy(
    CView* pViewFrom,
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>Параметры

*pViewFrom*<br/>
Указатель на представление, из которого происходит прокрутка сообщения.

*размерScroll*<br/>
Количество пикселей, которые будут прокручиваться горизонтально и вертикально.

*bDoScroll*<br/>
Определяет, происходит ли указанное действие прокрутки. Если *bDoScroll* является правдой (т.е. если окно ребенка существует, и если разделенные окна имеют диапазон прокрутки), то указанное действие прокрутки может иметь место; если *bDoScroll* false (т.е. если не существует окна ребенка, или разделенные представления не имеют диапазона прокрутки), то прокрутка не происходит.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если происходит синхронизированная прокрутка; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается фреймворком в ответ на сообщение прокрутки для выполнения синхронизированной прокрутки разделенных окон по количеству, в пикселях, указанных *размеромScroll*. Положительные значения указывают на прокрутку вниз и вправо; отрицательные значения указывают на прокрутку вверх и влево.

Переопределить, чтобы потребовать действия пользователя, прежде чем разрешить прокрутку.

## <a name="csplitterwndgetactivepane"></a><a name="getactivepane"></a>CSplitterWnd::GetActivePane

Определяет активное стекло от фокуса или активного представления в кадре.

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>Параметры

*pRow*<br/>
Указатель на **int** для получения номера строки активного стекла.

*pCol*<br/>
Указатель на **int** для извлечения номера столбца активного стекла.

### <a name="return-value"></a>Возвращаемое значение

Указатель на активную панель. NULL, если активного стекла не существует.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается фректовой для определения активного стекла в окне сплиттера. Переопределение требует действия пользователя, прежде чем получить активное стекло.

## <a name="csplitterwndgetcolumncount"></a><a name="getcolumncount"></a>CSplitterWnd::GetColumnCount

Возвращает текущее количество столбцов панели.

```
int GetColumnCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущее количество столбцов в сплиттере. Для статического сплиттера это также будет максимальное количество столбцов.

## <a name="csplitterwndgetcolumninfo"></a><a name="getcolumninfo"></a>CSplitterWnd::GetColumnInfo

Возвращает информацию в указанную колонку.

```cpp
void GetColumnInfo(
    int col,
    int& cxCur,
    int& cxMin) const;
```

### <a name="parameters"></a>Параметры

*col*<br/>
Указывает столбец.

*cxCur*<br/>
Ссылка на **int,** которая будет установлена на текущую ширину столбца.

*cxMin*<br/>
Ссылка на **int,** которая будет установлена на текущую минимальную ширину столбца.

## <a name="csplitterwndgetpane"></a><a name="getpane"></a>CSplitterWnd::GetPane

Возвращает панель в указанном ряду и столбце.

```
CWnd* GetPane(
    int row,
    int col) const;
```

### <a name="parameters"></a>Параметры

*Строки*<br/>
Определяет строку.

*col*<br/>
Указывает столбец.

### <a name="return-value"></a>Возвращаемое значение

Возвращает панель в указанном ряду и столбце. Возвращалось стекло, как [CView](../../mfc/reference/cview-class.md)правило, CView-производные класса.

## <a name="csplitterwndgetrowcount"></a><a name="getrowcount"></a>CSplitterWnd::GetRowCount

Возвращает текущее количество строк панели панели.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущее количество строк в окне сплиттера. Для статического окна сплиттера это также будет максимальное количество строк.

## <a name="csplitterwndgetrowinfo"></a><a name="getrowinfo"></a>CSplitterWnd::GetRowInfo

Возвращает информацию в указанную строку.

```cpp
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>Параметры

*Строки*<br/>
Определяет строку.

*cyCur*<br/>
Ссылка на **Int,** которая будет установлена на текущую высоту строки в пикселях.

*цимин*<br/>
Ссылка на **Int,** которая будет установлена на текущую минимальную высоту строки в пикселях.

### <a name="remarks"></a>Remarks

Позвоните этой функции участника для получения информации об указанной строке. Параметр *cyCur* заполняется текущей высотой указанного ряда, а *цимин* заполняется минимальной высотой строки.

## <a name="csplitterwndgetscrollstyle"></a><a name="getscrollstyle"></a>CSplitterWnd::GetScrollStyle

Возвращает общий стиль прокрутки для окна сплиттера.

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Один или несколько из следующих флагов стиля окна, в случае успеха:

- WS_HSCROLL Если сплиттер в настоящее время управляет общими горизонтальными барами прокрутки.

- WS_VSCROLL Если сплиттер в настоящее время управляет общими вертикальными барами прокрутки.

Если ноль, окно сплиттера в настоящее время не управляет общими барами прокрутки.

## <a name="csplitterwndidfromrowcol"></a><a name="idfromrowcol"></a>CSplitterWnd::IdFromRowCol

Получение идентификатора окна ребенка для панели в указанном ряду и столбце.

```
int IdFromRowCol(
    int row,
    int col) const;
```

### <a name="parameters"></a>Параметры

*Строки*<br/>
Определяет строку окна сплиттера.

*col*<br/>
Определяет столбец окна сплиттера.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор окна ребенка для панели.

### <a name="remarks"></a>Remarks

Эта функция члена используется для создания непросмотров в виде стекол и может быть вызвана до того, как панель существует.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]

## <a name="csplitterwndischildpane"></a><a name="ischildpane"></a>CSplitterWnd::IsChildPane

Определяет, является ли *pWnd* в настоящее время детским стеклом этого окна сплиттера.

```
BOOL IsChildPane(
    CWnd* pWnd,
    int* pRow,
    int* pCol);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) который должен быть протестирован.

*pRow*<br/>
Указатель на **int,** в котором для хранения номера строки.

*pCol*<br/>
Указатель на **int,** в котором можно хранить номер столбца.

### <a name="return-value"></a>Возвращаемое значение

Если ненулевой, *pWnd* в настоящее время является детским стеклом этого окна сплиттера, и *pRow* и *pCol* заполнены положением панели в окне сплиттера. Если *pWnd* не является детским стеклом этого окна сплиттера, 0 возвращается.

### <a name="remarks"></a>Remarks

В версиях Visual C' до 6.0 эта функция была определена как

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

Эта версия устарела и не должна использоваться.

## <a name="csplitterwndistracking"></a><a name="istracking"></a>CSplitterWnd::IsTracking

Вызовите эту функцию участника, чтобы определить, перемещается ли в настоящее время панель сплиттера в окне.

```
BOOL IsTracking();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если операция сплиттера продолжается; в противном случае 0.

## <a name="csplitterwndondrawsplitter"></a><a name="ondrawsplitter"></a>CSplitterWnd::OnDrawSplitter

Рендеризирует изображение разделенного окна.

```
virtual void OnDrawSplitter(
    CDC* pDC,
    ESplitType nType,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства, в котором можно рисовать. Если *pDC* является NULL, то [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) вызывается фреймворкой и не нарисовано разделенное окно.

*nType*<br/>
Значение , `enum ESplitType`которое может быть одним из следующих:

- `splitBox`Коробка для перетаскивания сплиттера.

- `splitBar`Бар, который появляется между двумя разделенными окнами.

- `splitIntersection`Пересечение разбитых окон. Этот элемент не будет вызываться при запуске на Windows 95/98.

- `splitBorder`Границы разделенного окна.

*rect*<br/>
Ссылка на объект [CRect](../../atl-mfc-shared/reference/crect-class.md) с указанием размера и формы разделенных окон.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается инфраструктурой для рисования и указания точных характеристик окна сплиттера. Переопределение `OnDrawSplitter` для расширенной настройки изображений для различных графических компонентов окна сплиттера. Изображения по умолчанию аналогичны сплиттеру в Microsoft Works for Windows или Microsoft Windows 95/98, так как пересечения сплиттерных полос смешиваются вместе.

Подробнее о динамических окнах сплиттера см. [Multiple Document Types, Views, and Frame Windows](../../mfc/multiple-document-types-views-and-frame-windows.md) [Technical Note 29](../../mfc/tn029-splitter-windows.md) `CSplitterWnd`

## <a name="csplitterwndoninverttracker"></a><a name="oninverttracker"></a>CSplitterWnd::OnInvertTracker

Отобразит изображение разделенного окна таким же размером и формой, как окно рамы.

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Ссылка `CRect` на объект, определяющий прямоугольник отслеживания.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается инфраструктурой во время переосмысления сплиттеров. Переопределение `OnInvertTracker` для расширенной настройки изображений окна сплиттера. Изображения по умолчанию аналогичны сплиттеру в Microsoft Works for Windows или Microsoft Windows 95/98, так как пересечения сплиттерных полос смешиваются вместе.

Подробнее о динамических окнах сплиттера см. [Multiple Document Types, Views, and Frame Windows](../../mfc/multiple-document-types-views-and-frame-windows.md) [Technical Note 29](../../mfc/tn029-splitter-windows.md) `CSplitterWnd`

## <a name="csplitterwndrecalclayout"></a><a name="recalclayout"></a>CSplitterWnd::RecalcLayout

Вызов для повторного отображения окна сплиттера после регулировки размера строки или столбца.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Remarks

Вызов ими функции участника для правильного отображения окна сплиттера после корректировки размеров строки и столбцов с функциями участника [SetRowInfo](#setrowinfo) и [SetColumnInfo.](#setcolumninfo) Если вы изменяете размерстроки и столбец в процессе создания до того, как будет видно окно сплиттера, нет необходимости вызывать эту функцию участника.

Фрейм вызывает эту функцию участника всякий раз, когда пользователь изменяет размер окна сплиттера или перемещает сплит.

### <a name="example"></a>Пример

  Смотрите пример [CSplitterWnd::SetColumnInfo](#setcolumninfo).

## <a name="csplitterwndsetactivepane"></a><a name="setactivepane"></a>CSplitterWnd::SetActivePane

Устанавливает панель, чтобы быть активным в кадре.

```
virtual void SetActivePane(
    int row,
    int col,
    CWnd* pWnd = NULL);
```

### <a name="parameters"></a>Параметры

*Строки*<br/>
Если *pWnd* является NULL, указывает строку в панели, которая будет активна.

*col*<br/>
Если *pWnd* является NULL, упомяните столбец в панели, которая будет активна.

*pWnd*<br/>
Указатель на объект `CWnd`. Если NULL, панель, указанная *строкой* и *col,* установлена активная. Если не NULL, указывает панель, которая установлена активная.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается инфраструктурой для установки панели как активная, когда пользователь изменяет фокус на панель в окне кадра. Можно явно призвать `SetActivePane` изменить фокус на указанное представление.

Укажите панель, предоставив строку и столбец, **или** предоставив *pWnd.*

## <a name="csplitterwndsetcolumninfo"></a><a name="setcolumninfo"></a>CSplitterWnd::SetColumnInfo

Звоните, чтобы установить указанную информацию о столбце.

```cpp
void SetColumnInfo(
    int col,
    int cxIdeal,
    int cxMin);
```

### <a name="parameters"></a>Параметры

*col*<br/>
Определяет столбец окна сплиттера.

*cxИдеальный*<br/>
Определяет идеальную ширину для столбца окна сплиттера в пикселях.

*cxMin*<br/>
Определяет минимальную ширину столбца окна сплиттера в пикселях.

### <a name="remarks"></a>Remarks

Вызовите эту функцию члена, чтобы установить новую минимальную ширину и идеальную ширину для столбца. Минимальное значение столбца определяет, когда столбец будет слишком мал, чтобы быть полностью отображенным.

Когда фреймвор отображает окно сплиттера, он выкладывает стекла в столбцы и строки в соответствии с их идеальными размерами, работая от верхнего левого к нижнему правому углу клиентской области окна сплиттера.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]

## <a name="csplitterwndsetrowinfo"></a><a name="setrowinfo"></a>CSplitterWnd::SetRowInfo

Звоните, чтобы установить указанную информацию о строке.

```cpp
void SetRowInfo(
    int row,
    int cyIdeal,
    int cyMin);
```

### <a name="parameters"></a>Параметры

*Строки*<br/>
Определяет строку окна сплиттера.

*cyIdeal*<br/>
Определяет идеальную высоту для строки окна сплиттера в пикселях.

*цимин*<br/>
Определяет минимальную высоту для строки окна сплиттера в пикселях.

### <a name="remarks"></a>Remarks

Вызовите эту функцию участника, чтобы установить новую минимальную высоту и идеальную высоту для ряда. Минимальное значение строки определяет, когда строка будет слишком мала, чтобы быть полностью отображаемым.

Когда фреймвор отображает окно сплиттера, он выкладывает стекла в столбцы и строки в соответствии с их идеальными размерами, работая от верхнего левого к нижнему правому углу клиентской области окна сплиттера.

## <a name="csplitterwndsetscrollstyle"></a><a name="setscrollstyle"></a>CSplitterWnd::SetScrollStyle

Определяет новый стиль прокрутки для общей поддержки окна сплиттера.

```cpp
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Новый стиль прокрутки для общей поддержки сплиттерного окна прокрутки, который может быть одним из следующих значений:

- WS_HSCROLL Создать/показать горизонтальные общие бары прокрутки.

- WS_VSCROLL Создать/показать вертикальные общие бары прокрутки.

### <a name="remarks"></a>Remarks

После создания панели прокрутки она `SetScrollStyle` не будет уничтожена, даже если она называется без этого стиля; вместо этого эти прокрутки баров скрыты. Это позволяет бары прокрутки сохранить свое состояние, даже если они скрыты. После `SetScrollStyle` вызова необходимо позвонить [в RecalcLayout,](#recalclayout) чтобы все изменения вступили в силу.

## <a name="csplitterwndsplitcolumn"></a><a name="splitcolumn"></a>CSplitterWnd::SplitColumn

Указывает, где окно кадра расщепляется вертикально.

```
virtual BOOL SplitColumn(int cxBefore);
```

### <a name="parameters"></a>Параметры

*cxПеред*<br/>
Положение, в пикселях, перед которым происходит раскол.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается при создании вертикального окна сплиттера. `SplitColumn`указывает место по умолчанию, где происходит разделение.

`SplitColumn`называется инфраструктурой для реализации логики динамического окна сплиттера (т.е. если окно сплиттера имеет SPLS_DYNAMIC_SPLIT стиль). Он может быть настроен, наряду с виртуальной функцией [CreateView](#createview), для реализации более продвинутых динамических сплиттеров.

## <a name="csplitterwndsplitrow"></a><a name="splitrow"></a>CSplitterWnd::SplitRow

Указывает, где окно кадра расколается горизонтально.

```
virtual BOOL SplitRow(int cyBefore);
```

### <a name="parameters"></a>Параметры

*cyПеред*<br/>
Положение, в пикселях, перед которым происходит раскол.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена вызывается при создании горизонтального окна сплиттера. `SplitRow`указывает место по умолчанию, где происходит разделение.

`SplitRow`называется инфраструктурой для реализации логики динамического окна сплиттера (т.е. если окно сплиттера имеет SPLS_DYNAMIC_SPLIT стиль). Он может быть настроен, наряду с виртуальной функцией [CreateView](#createview), для реализации более продвинутых динамических сплиттеров.

## <a name="csplitterwndondraw"></a><a name="ondraw"></a>CSplitterWnd::OnDraw

Вызывается по фреймворку, чтобы нарисовать окно сплиттера.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства.

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[MFC Образец VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)
