---
title: Класса CSplitterWnd | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 071eaeef6fbdbe4967d184936f5fb7bffb7786b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377853"
---
# <a name="csplitterwnd-class"></a>Класса CSplitterWnd
Предоставляет функциональные возможности окна-разделителя, то есть окна, содержащего несколько областей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Вызов для создания `CSplitterWnd` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](#activatenext)|Выполняет команды Next Pane и Previous Pane.|  
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Проверяет, является ли команды Next Pane и Previous Pane поддерживается в настоящее время.|  
|[CSplitterWnd::Create](#create)|Вызов для создания динамическое окно разделитель и присоединить его к `CSplitterWnd` объекта.|  
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Создает общий полосы прокрутки.|  
|[CSplitterWnd::CreateStatic](#createstatic)|Вызов создать окно со статическим разделителем и присоединить его к `CSplitterWnd` объекта.|  
|[CSplitterWnd::CreateView](#createview)|Вызов для создания области в окне разделителя.|  
|[CSplitterWnd::DeleteColumn](#deletecolumn)|Удаляет колонку из разделителя окна.|  
|[CSplitterWnd::DeleteRow](#deleterow)|Удаляет строку из окна разделителя.|  
|[CSplitterWnd::DeleteView](#deleteview)|Удаляет представление из окна разделителя.|  
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Выполняет команду, обычно «разделения окна». разделения клавиатуры|  
|[CSplitterWnd::DoScroll](#doscroll)|Выполняет синхронную прокрутку окна разделителя.|  
|[CSplitterWnd::DoScrollBy](#doscrollby)|Прокручивает окно разделитель заданное количество точек.|  
|[CSplitterWnd::GetActivePane](#getactivepane)|Определяет активную область из фокуса или активное представление во фрейме.|  
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Возвращает число столбцов текущей области.|  
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Возвращает сведения для указанного столбца.|  
|[CSplitterWnd::GetPane](#getpane)|Возвращает область в указанной строке и столбце.|  
|[CSplitterWnd::GetRowCount](#getrowcount)|Возвращает число строк текущей области.|  
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Возвращает сведения о заданной строки.|  
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Возвращает стиль общей полосы прокрутки.|  
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Возвращает дочерние окна идентификатор области в указанной строке и столбце.|  
|[CSplitterWnd::IsChildPane](#ischildpane)|Вызов, чтобы определить, является ли окно в данный момент дочерней области окна разделителя.|  
|[CSplitterWnd::IsTracking](#istracking)|Определяет, если разделитель перемещается в данный момент.|  
|[CSplitterWnd::RecalcLayout](#recalclayout)|Вызов отобразите окно-разделитель после изменение размера строк или столбцов.|  
|[CSplitterWnd::SetActivePane](#setactivepane)|Устанавливает область активной в одном в кадре.|  
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Вызов, чтобы задать сведения из указанного столбца.|  
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Вызов для установки сведений об указанной строки.|  
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Указывает, что полоса прокрутки поддержка общих новый стиль полосы прокрутки для окна разделителя.|  
|[CSplitterWnd::SplitColumn](#splitcolumn)|Указывает, где окно фрейма разделяется по вертикали.|  
|[CSplitterWnd::SplitRow](#splitrow)|Указывает, где окно фрейма разделяется по горизонтали.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](#ondraw)|Вызывается платформой для отрисовки окна-разделителя.|  
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Выполняет отрисовку рисунка окна разделителя.|  
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Подготовка образа для такого же размера и формы, что и окно фрейма окна разделителя.|  
  
## <a name="remarks"></a>Примечания  
 Области обычно является производным от объекта конкретного приложения [CView](../../mfc/reference/cview-class.md), но это может быть любой [CWnd](../../mfc/reference/cwnd-class.md) объекта с идентификатором подходящие дочерние окна.  
  
 Объект `CSplitterWnd` объект обычно является встроенным в родительскую папку [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта. Создание `CSplitterWnd` объекта, выполнив следующие действия:  
  
1.  Внедрение `CSplitterWnd` переменной-члена в родительского фрейма.  
  
2.  Переопределить родительского фрейма [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) функции-члена.  
  
3.  От переопределенного `OnCreateClient`, вызовите [создать](#create) или [CreateStatic](#createstatic) функции-члена `CSplitterWnd`.  
  
 Вызовите **создать** функции-члена для создания динамическое окно разделитель. Динамическое окно разделитель обычно используется для создания и прокрутите ряд отдельных областей или представления одного документа. Платформа автоматически создает начальной области для разделителей; Затем платформа создает, изменяет и удаляет дополнительные области, как пользователь работает окна разделителя элементов управления.  
  
 При вызове **создать**, задать ширину строки минимальное высоте и столбец, определить, когда панелей слишком малы, чтобы полностью отобразить. После вызова метода **создать**, можно настроить эти минимальные значения путем вызова [SetColumnInfo](#setcolumninfo) и [SetRowInfo](#setrowinfo) функции-члены.  
  
 Также используйте `SetColumnInfo` и `SetRowInfo` функции-члены для задания «Оптимальная» ширина столбца и «идеальный» высота строки. Если платформа отображает окна-разделителя, сначала отображается родительского фрейма, затем окна-разделителя. Затем платформа располагает области в столбцы и строки согласно их идеальной измерений, работа из верхнего левого в правый нижний угол клиентской области окна разделителя.  
  
 Все области в динамическое окно разделитель должен быть того же класса. Знакомые приложения, поддерживающие окна с динамическим разделителем включают Microsoft Word и Microsoft Excel.  
  
 Используйте `CreateStatic` функции-члена для создания статическое окно-разделитель. Пользователь может изменить размер областей в статический разделитель окна, а не их количества или порядка.  
  
 В частности, необходимо создать все статические разделителя на панели при создании статический разделитель. Убедитесь, что создание всех панелей перед родительского фрейма `OnCreateClient` функция возвращает элемент, или framework будет отображаться окно неправильно.  
  
 `CreateStatic` Функция-член автоматически инициализирует статический разделитель строк минимальное высоте и столбец шириной 0. После вызова метода **создать**, настройте эти минимальные значения путем вызова [SetColumnInfo](#setcolumninfo) и [SetRowInfo](#setrowinfo) функции-члены. Также используйте `SetColumnInfo` и `SetRowInfo` после вызова метода `CreateStatic` для указания требуемого идеальной панели измерений.  
  
 Отдельные области статический разделитель часто принадлежит разные классы. Примеры окна со статическим разделителем в разделе графический редактор и диспетчер файлов.  
  
 Окна-разделителя поддерживает специальные ползунки (помимо полосы прокрутки, которые могут иметь области). Эти полосы прокрутки являются потомками `CSplitterWnd` объекта и совместно с областями.  
  
 При создании окна-разделителя, создайте эти специальные ползунки. Например `CSplitterWnd` с одной строки, два столбца и **WS_VSCROLL** стиль будет отображать вертикальную полосу прокрутки, совместно используется двумя областями. Когда пользователь перемещает полосу прокрутки `WM_VSCROLL` сообщения отправляются в обеих областях. При панелей задать положение полосы прокрутки, полосы прокрутки общего устанавливается.  
  
 Дополнительные сведения об окнах разделителей см.:  
  
- [Техническое Примечание 29](../../mfc/tn029-splitter-windows.md)  
  
-   Статья базы знаний Q262024: Практическое руководство: использование CPropertySheet как дочерний CSplitterWnd  
  
 Дополнительные сведения о создании окна с динамическим разделителем см. в разделе:  
  
-   Пример MFC [Scribble](../../visual-cpp-samples.md)  
  
-   Пример MFC [VIEWEX](../../visual-cpp-samples.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxext.h  
  
##  <a name="activatenext"></a>  CSplitterWnd::ActivateNext  
 Вызывается платформой для выполнения команды Next Pane и Previous Pane.  
  
```  
virtual void ActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bPrev`  
 Указывает, какое окно для активации. **Значение TRUE,** для предыдущего; **FALSE** для следующего.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член — это высокоуровневая команда, которая используется [CView](../../mfc/reference/cview-class.md) класс делегировать `CSplitterWnd` реализации.  
  
##  <a name="canactivatenext"></a>  CSplitterWnd::CanActivateNext  
 Вызывается платформой для проверки, является ли команды Next Pane и Previous Pane поддерживается в настоящее время.  
  
```  
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bPrev`  
 Указывает, какое окно для активации. **Значение TRUE,** для предыдущего; **FALSE** для следующего.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член — это высокоуровневая команда, которая используется [CView](../../mfc/reference/cview-class.md) класс делегировать `CSplitterWnd` реализации.  
  
##  <a name="create"></a>  CSplitterWnd::Create  
 Чтобы создать динамическое окно разделитель, вызовите **создать** функции-члена.  
  
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
 `pParentWnd`  
 Родительское окно фрейма окна-разделителя.  
  
 *nMaxRows*  
 Максимальное число строк в окно-разделитель. Это значение не должно превышать 2.  
  
 *nMaxCols*  
 Максимальное число столбцов в окне разделителя. Это значение не должно превышать 2.  
  
 `sizeMin`  
 Задает минимальный размер, с которой может отображаться панель.  
  
 `pContext`  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. В большинстве случаев это может быть `pContext` передаваемый родительское окно фрейма.  
  
 `dwStyle`  
 Указывает стиль окна.  
  
 `nID`  
 Идентификатор дочернего окна окна. Идентификатор может быть **AFX_IDW_PANE_FIRST** Если окна-разделителя вложен в другой окно-разделитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно внедрить `CSplitterWnd` в родительскую папку [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта, выполнив следующие действия:  
  
1.  Внедрение `CSplitterWnd` переменной-члена в родительского фрейма.  
  
2.  Переопределить родительского фрейма [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) функции-члена.  
  
3.  Вызовите **создать** функции-члена из переопределенного `OnCreateClient`.  
  
 При создании окна-разделителя из внутри родительского фрейма, передавать родительского фрейма `pContext` параметр окна-разделителя. В противном случае этот параметр может иметь **NULL**.  
  
 Задается ширина высоте и столбец начальной строки минимальное динамическое окно разделитель `sizeMin` параметра. Эти минимумы, которые определяют ли панель слишком мал для отображения в полном объеме, можно изменить при помощи [SetRowInfo](#setrowinfo) и [SetColumnInfo](#setcolumninfo) функции-члены.  
  
 Дополнительные сведения о окна с динамическим разделителем см «Окна» в статье [несколько типов документов, представлений и фреймов](../../mfc/multiple-document-types-views-and-frame-windows.md), [Технические заметки 29](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` Общие сведения о классе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]  
  
##  <a name="createscrollbarctrl"></a>  CSplitterWnd::CreateScrollBarCtrl  
 Вызывается платформой для создания общей полосы прокрутки.  
  
```  
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Указывает стиль окна.  
  
 `nID`  
 Идентификатор дочернего окна окна. Идентификатор может быть **AFX_IDW_PANE_FIRST** Если окна-разделителя вложен в другой окно-разделитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределить `CreateScrollBarCtrl` для включения дополнительных элементов управления рядом с полосы прокрутки. Поведение по умолчанию является создание обычных элементов управления полосы прокрутки Windows.  
  
##  <a name="createstatic"></a>  CSplitterWnd::CreateStatic  
 Чтобы создать окно со статическим разделителем, вызовите `CreateStatic` функции-члена.  
  
```  
virtual BOOL CreateStatic(
    CWnd* pParentWnd,  
    int nRows,  
    int nCols,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Родительское окно фрейма окна-разделителя.  
  
 `nRows`  
 Количество строк. Это значение не должно превышать 16.  
  
 *nCols*  
 Количество столбцов. Это значение не должно превышать 16.  
  
 `dwStyle`  
 Указывает стиль окна.  
  
 `nID`  
 Идентификатор дочернего окна окна. Идентификатор может быть **AFX_IDW_PANE_FIRST** Если окна-разделителя вложен в другой окно-разделитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Объект `CSplitterWnd` обычно является встроенным в родительскую папку `CFrameWnd` или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта, выполнив следующие действия:  
  
1.  Внедрение `CSplitterWnd` переменной-члена в родительского фрейма.  
  
2.  Переопределить родительского фрейма `OnCreateClient` функции-члена.  
  
3.  Вызовите `CreateStatic` функции-члена из переопределенного [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).  
  
 Окно со статическим разделителем содержит фиксированное число панелей, часто из различных классов.  
  
 При создании окно со статическим разделителем, в то же время создайте все панели. [CreateView](#createview) функция-член обычно используется для этой цели, но можно создать другие классы nonview.  
  
 Начальной строки Минимальная ширина высоте и столбец для окно со статическим разделителем равна 0. Эти минимумы, которые определяют при областью слишком мал для отображения в полном объеме, можно изменить при помощи [SetRowInfo](#setrowinfo) и [SetColumnInfo](#setcolumninfo) функции-члены.  
  
 Чтобы добавить полосы прокрутки статическое окно-разделитель, добавьте **WS_HSCROLL** и **WS_VSCROLL** стили для `dwStyle`.  
  
 См. в статье «Окна» [несколько типов документов, представлений и фреймов](../../mfc/multiple-document-types-views-and-frame-windows.md), [Технические заметки 29](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` Общие сведения о классе для получения дополнительных сведений об окна со статическим разделителем.  
  
##  <a name="createview"></a>  CSplitterWnd::CreateView  
 Создает область для статическое окно-разделитель.  
  
```  
virtual BOOL CreateView(
    int row,  
    int col,  
    CRuntimeClass* pViewClass,  
    SIZE sizeInit,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Параметры  
 `row`  
 Задает строку разделителя окна для размещения нового представления.  
  
 `col`  
 Указывает столбец, окно разделитель для размещения нового представления.  
  
 `pViewClass`  
 Указывает [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) нового представления.  
  
 *sizeInit*  
 Задает первоначальный размер нового представления.  
  
 `pContext`  
 Указатель на контекст создания, используемый для создания представления (обычно `pContext` переданные родительского фрейма переопределенный [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) функция-член, в котором создается окна-разделителя).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Все области окно со статическим разделителем необходимо создать перед платформа отображает разделителя.  
  
 Также платформа вызывает эту функцию-член для создания новой области, когда пользователь динамическое окно разделитель разделяет области, строки или столбца.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]  
  
##  <a name="csplitterwnd"></a>  CSplitterWnd::CSplitterWnd  
 Вызов для создания `CSplitterWnd` объекта.  
  
```  
CSplitterWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Создать `CSplitterWnd` объекта в два этапа. Во-первых, вызывает конструктор, который создает `CSplitterWnd` объекта, а затем вызвать [создать](#create) функция-член, который создает окно-разделитель и присоединяет его к `CSplitterWnd` объекта.  
  
##  <a name="deletecolumn"></a>  CSplitterWnd::DeleteColumn  
 Удаляет колонку из разделителя окна.  
  
```  
virtual void DeleteColumn(int colDelete);
```  
  
### <a name="parameters"></a>Параметры  
 *colDelete*  
 Указывает столбец для удаления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для реализации логики динамическое окно разделитель (то есть, в том случае, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="deleterow"></a>  CSplitterWnd::DeleteRow  
 Удаляет строку из окна разделителя.  
  
```  
virtual void DeleteRow(int rowDelete);
```  
  
### <a name="parameters"></a>Параметры  
 *rowDelete*  
 Указывает строку для удаления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для реализации логики динамическое окно разделитель (то есть, в том случае, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="deleteview"></a>  CSplitterWnd::DeleteView  
 Удаляет представление из окна разделителя.  
  
```  
virtual void DeleteView(
    int row,  
    int col);
```  
  
### <a name="parameters"></a>Параметры  
 `row`  
 Задает строку разделителя окна с которого следует удалить представление.  
  
 `col`  
 Указывает столбец окна разделителя, с которого следует удалить представление.  
  
### <a name="remarks"></a>Примечания  
 Если удаляется активное представление следующее представление станет активным. Реализация по умолчанию предполагается, представление будет автоматически удалять в [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy).  
  
 Эта функция-член вызывается платформой для реализации логики динамическое окно разделитель (то есть, в том случае, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="dokeyboardsplit"></a>  CSplitterWnd::DoKeyboardSplit  
 Выполняет команду, обычно «разделения окна». разделения клавиатуры  
  
```  
virtual BOOL DoKeyboardSplit();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член — это высокоуровневая команда, которая используется [CView](../../mfc/reference/cview-class.md) класс делегировать `CSplitterWnd` реализации.  
  
##  <a name="doscroll"></a>  CSplitterWnd::DoScroll  
 Выполняет синхронную прокрутку окна разделителя.  
  
```  
virtual BOOL DoScroll(
    CView* pViewFrom,  
    UINT nScrollCode,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pViewFrom`  
 Указатель на представление, являющегося источником сообщения прокрутки.  
  
 `nScrollCode`  
 Полоса прокрутки код, указывающий пользователя прокрутки запроса. Этот параметр состоит из двух частей: младший байт, который определяет тип возникновения прокрутки по горизонтали, а старший байт, который определяет тип возникновения прокрутки по вертикали:  
  
- **SB_BOTTOM** выполняет прокрутку вниз.  
  
- **SB_LINEDOWN** прокручивает одну строку вниз.  
  
- **SB_LINEUP** прокручивает одну строку вверх.  
  
- **SB_PAGEDOWN** прокручивает одну страницу вниз.  
  
- **SB_PAGEUP** прокручивает одну страницу вверх.  
  
- **SB_TOP** прокручивается в начало.  
  
 `bDoScroll`  
 Определяет, происходит ли указанное действие прокрутки. Если `bDoScroll` — **TRUE** (то есть, в том случае, если существует дочернее окно и если windows разбиение диапазон прокрутки), то указанное действие прокрутки может выполняться; Если `bDoScroll` — **FALSE** (то есть, если существует ни одного дочернего окна, или диапазон прокрутки не имеют представления с разделением), а затем прокрутки не возникает.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если возникнет синхронную прокрутку. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для выполнения синхронную прокрутку окна разделителя, когда представление получает сообщение прокрутки. Переопределение синхронную прокрутку может требоваться действие пользователя.  
  
##  <a name="doscrollby"></a>  CSplitterWnd::DoScrollBy  
 Прокручивает окно разделитель заданное количество точек.  
  
```  
virtual BOOL DoScrollBy(
    CView* pViewFrom,  
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pViewFrom`  
 Указатель на представление, являющегося источником сообщения прокрутки.  
  
 `sizeScroll`  
 Число пикселей для прокручиваться по горизонтали и вертикали.  
  
 bDoScroll  
 Определяет, происходит ли указанное действие прокрутки. Если `bDoScroll` — **TRUE** (то есть, в том случае, если существует дочернее окно и если windows разбиение диапазон прокрутки), то указанное действие прокрутки может выполняться; Если `bDoScroll` — **FALSE** (то есть, если существует ни одного дочернего окна, или диапазон прокрутки не имеют представления с разделением), а затем прокрутки не возникает.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если возникнет синхронную прокрутку. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой в ответ на сообщение прокрутки, для выполнения синхронизации прокрутку окна разделителя на величину, в пикселях, обозначенном `sizeScroll`. Положительные значения указывают прокрутку вниз и вправо; отрицательные значения указывают, прокрутку вверх и влево.  
  
 Переопределите, чтобы требовать вмешательства со стороны пользователя, прежде чем разрешить прокрутки.  
  
##  <a name="getactivepane"></a>  CSplitterWnd::GetActivePane  
 Определяет активную область из фокуса или активное представление во фрейме.  
  
```  
virtual CWnd* GetActivePane(
    int* pRow = NULL,  
    int* pCol = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pRow`  
 Указатель на **int** для извлечения нескольких строк активной панели.  
  
 `pCol`  
 Указатель на **int** для извлечения номера столбца на активной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активной панели. **Значение NULL** Если существует нет активной панели.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой, чтобы определить активную область в окне разделителя. Переопределите, чтобы требовать вмешательства со стороны пользователя, прежде чем клиент получит активной панели.  
  
##  <a name="getcolumncount"></a>  CSplitterWnd::GetColumnCount  
 Возвращает число столбцов текущей области.  
  
```  
int GetColumnCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее число столбцов в разделителя. Для статического разделителя оно также будет использоваться максимальное число столбцов.  
  
##  <a name="getcolumninfo"></a>  CSplitterWnd::GetColumnInfo  
 Возвращает сведения для указанного столбца.  
  
```  
void GetColumnInfo(
    int col,  
    int& cxCur,  
    int& cxMin) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `col`  
 Указывает столбец.  
  
 *cxCur*  
 Ссылку на `int` требуется задать значение из текущей ширины столбца.  
  
 `cxMin`  
 Ссылку на `int` присваивается текущее минимальную ширину столбца.  
  
##  <a name="getpane"></a>  CSplitterWnd::GetPane  
 Возвращает область в указанной строке и столбце.  
  
```  
CWnd* GetPane(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `row`  
 Указывает строку.  
  
 `col`  
 Указывает столбец.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает область в указанной строке и столбце. Возвращаемый области обычно является [CView](../../mfc/reference/cview-class.md)-производного класса.  
  
##  <a name="getrowcount"></a>  CSplitterWnd::GetRowCount  
 Возвращает число строк текущей области.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее число строк в окно-разделитель. Статический разделитель окна оно также будет использоваться максимальное число строк.  
  
##  <a name="getrowinfo"></a>  CSplitterWnd::GetRowInfo  
 Возвращает сведения о заданной строки.  
  
```  
void GetRowInfo(
    int row,  
    int& cyCur,  
    int& cyMin) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `row`  
 Указывает строку.  
  
 `cyCur`  
 Ссылка на `int` присваивается текущую высоту строки в пикселях.  
  
 `cyMin`  
 Ссылка на `int` присваивается текущее минимальную высоту строки в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для получения сведений об указанной строки. `cyCur` Параметра заполняется из текущей высоты указанной строки и `cyMin` заполняется минимальную высоту строки.  
  
##  <a name="getscrollstyle"></a>  CSplitterWnd::GetScrollStyle  
 Возвращает стиль общего полоса прокрутки окна-разделителя.  
  
```  
DWORD GetScrollStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один или несколько из следующих окон стиля флаги, в случае успешного выполнения:  
  
- **WS_HSCROLL** Если разделитель в настоящее время управляет общего горизонтальные полосы прокрутки.  
  
- **WS_VSCROLL** Если разделитель в настоящее время управляет общего вертикальных полос прокрутки.  
  
 Если значение равно нулю, разделитель окна не находится под управлением любой полосы прокрутки общего.  
  
##  <a name="idfromrowcol"></a>  CSplitterWnd::IdFromRowCol  
 Получает дочерний идентификатор окна области в указанной строке и столбце.  
  
```  
int IdFromRowCol(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `row`  
 Задает строку разделителя окна.  
  
 `col`  
 Указывает столбец, окно разделитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор дочернего окна области.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член используется для создания nonviews как областей и может быть вызван до создания области.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]  
  
##  <a name="ischildpane"></a>  CSplitterWnd::IsChildPane  
 Определяет, является ли `pWnd` дочерней области окна разделителя в данный момент.  
  
```  
BOOL IsChildPane(
    CWnd* pWnd,  
    int* pRow,  
    int* pCol);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) проверяемый объект.  
  
 `pRow`  
 Указатель на `int` для сохранения числа строк.  
  
 `pCol`  
 Указатель на `int` для хранения номер столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если значение ненулевое, `pWnd` в данный момент дочерней области окна разделителя, и `pRow` и `pCol` будут заполнены положение области в окне разделителя. Если `pWnd` не является дочерней области окна разделителя, возвращается значение 0.  
  
### <a name="remarks"></a>Примечания  
 В версиях Visual C++ до версии 6.0 эта функция определена как  
  
 `BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`  
  
 Эта версия больше не используется и не должны использоваться.  
  
##  <a name="istracking"></a>  CSplitterWnd::IsTracking  
 Вызовите эту функцию-член для определения того, если в окне разделитель перемещается в данный момент.  
  
```  
BOOL IsTracking();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция разделителей выполняется в данный момент; в противном случае — 0.  
  
##  <a name="ondrawsplitter"></a>  CSplitterWnd::OnDrawSplitter  
 Выполняет отрисовку рисунка окна разделителя.  
  
```  
virtual void OnDrawSplitter(
    CDC* pDC,  
    ESplitType nType,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства для рисования. Если `pDC` — **NULL**, затем [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) называется, платформа и отсутствие разбиения рисуется окна.  
  
 `nType`  
 Значение **перечисления ESplitType**, который может принимать одно из следующих действий:  
  
- **splitBox** разделителя перетащите поле.  
  
- `splitBar` Панель, которая расположена между двумя разделенными windows.  
  
- **splitIntersection** пересечение окна разделителя. Этот элемент не будет вызываться при работе в Windows 95/98.  
  
- **splitBorder** границы окна разбиения.  
  
 `rect`  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, указывающий размер и форму окна разделителя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для отрисовки и укажите точный характеристики окна-разделителя. Переопределить `OnDrawSplitter` для расширенной настройки изображения для различных компонентов графического окна-разделителя. Изображения по умолчанию аналогично разделителя в программе для Windows или Microsoft Windows 95/98, в том, что смешиваются пересечениях разделителей.  
  
 Дополнительные сведения о окна с динамическим разделителем см «Окна» в статье [несколько типов документов, представлений и фреймов](../../mfc/multiple-document-types-views-and-frame-windows.md), [Технические заметки 29](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` Общие сведения о классе.  
  
##  <a name="oninverttracker"></a>  CSplitterWnd::OnInvertTracker  
 Подготовка образа для такого же размера и формы, что и окно фрейма окна разделителя.  
  
```  
virtual void OnInvertTracker(const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Ссылка на `CRect` объект, указывающий отслеживания прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой при изменении размера объекта разделителей. Переопределить `OnInvertTracker` для расширенной настройки изображение окна-разделителя. Изображения по умолчанию аналогично разделителя в программе для Windows или Microsoft Windows 95/98, в том, что смешиваются пересечениях разделителей.  
  
 Дополнительные сведения о окна с динамическим разделителем см «Окна» в статье [несколько типов документов, представлений и фреймов](../../mfc/multiple-document-types-views-and-frame-windows.md), [Технические заметки 29](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` Общие сведения о классе.  
  
##  <a name="recalclayout"></a>  CSplitterWnd::RecalcLayout  
 Вызов отобразите окно-разделитель после изменение размера строк или столбцов.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член правильно отобразите окно-разделитель, после выбора изменения размеров строк и столбцов с [SetRowInfo](#setrowinfo) и [SetColumnInfo](#setcolumninfo) функции-члены. Чтобы изменить размеры строк и столбцов в процессе создания, перед разделителя окно является видимым, необязательно вызывать функцию-член.  
  
 Эта функция-член вызывается платформой, каждый раз, когда пользователь изменяет размер окна разделителя или перемещает разбиения.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CSplitterWnd::SetColumnInfo](#setcolumninfo).  
  
##  <a name="setactivepane"></a>  CSplitterWnd::SetActivePane  
 Устанавливает область активной в одном в кадре.  
  
```  
virtual void SetActivePane(
    int row,  
    int col,  
    CWnd* pWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `row`  
 Если `pWnd` — **NULL**, указывает строку, в области, в которой будет активным.  
  
 `col`  
 Если `pWnd` — **NULL**, задает столбец в области, в которой будет активным.  
  
 `pWnd`  
 Указатель на объект `CWnd`. Если **NULL**, области, определяемой `row` и `col` задано active. В противном случае **NULL**, указывает панель, на которой установлен active.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для задания в области активной при перемещении пользователем фокуса на область в окне фрейма. Можно явно вызывать `SetActivePane` для изменения фокуса в указанном представлении.  
  
 Задать область, указав строки и столбца, **или** , предоставляя `pWnd`.  
  
##  <a name="setcolumninfo"></a>  CSplitterWnd::SetColumnInfo  
 Вызов, чтобы задать сведения из указанного столбца.  
  
```  
void SetColumnInfo(
    int col,  
    int cxIdeal,  
    int cxMin);
```  
  
### <a name="parameters"></a>Параметры  
 `col`  
 Указывает столбец окна разделителя.  
  
 *cxIdeal*  
 Задает оптимальную ширину столбца окна разделителя в пикселях.  
  
 `cxMin`  
 Задает минимальную ширину столбца окна разделителя в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для установки нового минимальную ширину и оптимальную ширину столбца. Минимальное значение столбца определяет, когда будет слишком малы, чтобы полностью отобразить столбец.  
  
 Если платформа отображает окно-разделитель, располагает области в столбцы и строки согласно их идеальной измерений, работа из верхнего левого в правый нижний угол клиентской области окна разделителя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]  
  
##  <a name="setrowinfo"></a>  CSplitterWnd::SetRowInfo  
 Вызов для установки сведений об указанной строки.  
  
```  
void SetRowInfo(
    int row,  
    int cyIdeal,  
    int cyMin);
```  
  
### <a name="parameters"></a>Параметры  
 `row`  
 Задает строку разделителя окна.  
  
 *cyIdeal*  
 Указывает Идеальная высота строки окна разделителя в пикселях.  
  
 `cyMin`  
 Указывает минимальную высоту строки окна разделителя в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для установки нового минимальную высоту и идеальные значения высоты строки. Минимальное значение строки определяет, когда будет слишком малы, чтобы полностью отобразить строку.  
  
 Если платформа отображает окно-разделитель, располагает области в столбцы и строки согласно их идеальной измерений, работа из верхнего левого в правый нижний угол клиентской области окна разделителя.  
  
##  <a name="setscrollstyle"></a>  CSplitterWnd::SetScrollStyle  
 Указывает, что полоса прокрутки поддержка общих новый стиль прокрутки для окна разделителя.  
  
```  
void SetScrollStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Новый стиль прокрутки для окна разделителя общей поддержки полосы прокрутки, может принимать одно из следующих значений:  
  
- **WS_HSCROLL** горизонтальной Create/Показать общие полосы прокрутки.  
  
- **WS_VSCROLL** по вертикали Create/Показать общие полосы прокрутки.  
  
### <a name="remarks"></a>Примечания  
 После создания полоса прокрутки его, не будут уничтожены даже в том случае, если `SetScrollStyle` вызывается без этого стиля; вместо этого эти полос прокрутки. Это позволяет полосы прокрутки сохранить их состояние, несмотря на то, что они будут скрыты. После вызова метода `SetScrollStyle` необходимо вызвать [RecalcLayout](#recalclayout) все изменения вступили в силу.  
  
##  <a name="splitcolumn"></a>  CSplitterWnd::SplitColumn  
 Указывает, где окно фрейма разделяется по вертикали.  
  
```  
virtual BOOL SplitColumn(int cxBefore);
```  
  
### <a name="parameters"></a>Параметры  
 *cxBefore*  
 Позиция, в пикселях, перед которыми происходит разбиение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается при создании окна вертикальный разделитель. `SplitColumn` Указывает расположение по умолчанию, где происходит разбиение.  
  
 `SplitColumn` вызывается платформой для реализации логики динамическое окно разделитель (то есть, в том случае, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="splitrow"></a>  CSplitterWnd::SplitRow  
 Указывает, где окно фрейма разделяется по горизонтали.  
  
```  
virtual BOOL SplitRow(int cyBefore);
```  
  
### <a name="parameters"></a>Параметры  
 *cyBefore*  
 Позиция, в пикселях, перед которыми происходит разбиение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается при создании окна горизонтальный разделитель. `SplitRow` Указывает расположение по умолчанию, где происходит разбиение.  
  
 `SplitRow` вызывается платформой для реализации логики динамическое окно разделитель (то есть, в том случае, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="ondraw"></a>  CSplitterWnd::OnDraw  
 Вызывается платформой для отрисовки окна-разделителя.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Пример MFC: VIEWEX](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)
