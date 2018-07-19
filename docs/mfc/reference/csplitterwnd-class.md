---
title: Класс CSplitterWnd | Документация Майкрософт
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
ms.openlocfilehash: f01452a2a8f8b4a50b9aa7723eb4ded24b3f3cc9
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027928"
---
# <a name="csplitterwnd-class"></a>Класс CSplitterWnd
Предоставляет функциональные возможности окна-разделителя, то есть окна, содержащего несколько областей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Вызов для создания `CSplitterWnd` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](#activatenext)|Выполняет команды Next Pane и Previous Pane.|  
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Проверяет, является ли команды Next Pane и Previous Pane сейчас невозможно.|  
|[CSplitterWnd::Create](#create)|Вызов для создания динамическое окно разделитель и присоединить его к `CSplitterWnd` объекта.|  
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Создает общий полосы прокрутки.|  
|[CSplitterWnd::CreateStatic](#createstatic)|Вызов для создания окна со статическим разделителем и присоединить его к `CSplitterWnd` объекта.|  
|[CSplitterWnd::CreateView](#createview)|Вызов для создания панели в окне разделителя.|  
|[CSplitterWnd::DeleteColumn](#deletecolumn)|Удаляет колонку из разделителя окна.|  
|[CSplitterWnd::DeleteRow](#deleterow)|Удаляет строку из окна разделителя.|  
|[CSplitterWnd::DeleteView](#deleteview)|Удаляет представление из окна разделителя.|  
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Выполняет команду, обычно «Разделение окна». разделения клавиатуры|  
|[CSplitterWnd::DoScroll](#doscroll)|Выполняет синхронную прокрутку окна разделителя.|  
|[CSplitterWnd::DoScrollBy](#doscrollby)|Прокручивает окно разделитель заданное количество пикселей.|  
|[CSplitterWnd::GetActivePane](#getactivepane)|Определяет активную область из фокуса или активное представление во фрейме.|  
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Возвращает текущее число столбцов для области.|  
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Возвращает сведения для указанного столбца.|  
|[CSplitterWnd::GetPane](#getpane)|Возвращает область в указанной строке и столбце.|  
|[CSplitterWnd::GetRowCount](#getrowcount)|Возвращает текущее количество строк панели.|  
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Возвращает сведения о заданной строки.|  
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Возвращает стиль общей полосы прокрутки.|  
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Возвращает дочерний идентификатор окна области в указанной строке и столбце.|  
|[CSplitterWnd::IsChildPane](#ischildpane)|Вызова, чтобы определить, является ли окно сейчас дочерней области этого окна разделителя.|  
|[CSplitterWnd::IsTracking](#istracking)|Определяет, если выполняется перемещение полосы разделения.|  
|[CSplitterWnd::RecalcLayout](#recalclayout)|Вызов для обновления окна разделителя после настройки размера строки или столбца.|  
|[CSplitterWnd::SetActivePane](#setactivepane)|Устанавливает область активной в одном во фрейме.|  
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Вызов для задания данных указанного столбца.|  
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Вызов для установки сведений об указанной строки.|  
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Указывает, что поддержка полосы прокрутки общих новый стиль полосы прокрутки для окна разделителя.|  
|[CSplitterWnd::SplitColumn](#splitcolumn)|Указывает, где окно фрейма разделяется по вертикали.|  
|[CSplitterWnd::SplitRow](#splitrow)|Указывает, где окно фрейма разделяется по горизонтали.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](#ondraw)|Вызывается платформой для отрисовки окна разделителя.|  
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Выполняет отрисовку рисунка окна разделителя.|  
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Выполняет отрисовку рисунка окна разделителя же размер и форму, что и окно фрейма.|  
  
## <a name="remarks"></a>Примечания  
Область обычно является объект конкретного приложения, производный от [CView](../../mfc/reference/cview-class.md), но это может быть любая [CWnd](../../mfc/reference/cwnd-class.md) объекта с идентификатором соответствующее дочернее окно.  
  
 Объект `CSplitterWnd` объект обычно является внедренным в родительский элемент [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта. Создание `CSplitterWnd` объекта, выполнив следующие действия:  
  
 1. Внедрение `CSplitterWnd` переменную-член в родительского фрейма.  
  
 2.  Переопределить родительского фрейма [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) функция-член.  
  
 3.  Из в переопределенный `OnCreateClient`, вызовите [создать](#create) или [CreateStatic](#createstatic) функцию-член `CSplitterWnd`.  
  
Вызовите `Create` функция-член для создания динамическое окно разделитель. Окно с динамическим разделителем обычно используется для создания и прокрутите ряд отдельных областей или представлений одного документа. Платформа автоматически создает начальной панели для разделителя; Затем платформа создает, изменяет размер и удаляет из дополнительных областей, как элементы управления окна разделителя работает пользователь.  
  
При вызове `Create`, задать ширину высоте и столбец минимальное строки, которые определяют, когда области слишком малы для полного отображения. После вызова метода `Create`, вы можете настроить эти минимальные значения путем вызова [SetColumnInfo](#setcolumninfo) и [SetRowInfo](#setrowinfo) функций-членов.  
  
Также используйте `SetColumnInfo` и `SetRowInfo` функции-члены для задания ширины «идеального» для столбца и «идеального» высоту строки. Когда платформа отображает окна разделителя, то сначала он отображает родительского фрейма, а затем окна разделителя. Затем платформа располагает области в столбцах и строках в соответствии с их идеальной измерений, работа из верхнего левого в правый нижний угол клиентской области окна разделителя.  
  
Все области в окно с динамическим разделителем должен быть того же класса. Знакомые приложения, поддерживающие окон с динамическими разделителями включают Microsoft Word и Microsoft Excel.  
  
Используйте `CreateStatic` функция-член для создания окна со статическим разделителем. Пользователь может изменить только размер областей в статический разделитель окна, а не их число или порядок.  
  
В частности, необходимо создать все со статическим разделителем в области при создании со статическим разделителем. Убедитесь, что при создании все области, прежде чем родительского фрейма `OnCreateClient` функция-член возвращает, или framework будет отображаться в окне неправильно.  
  
`CreateStatic` Функция-член автоматически инициализирует статический разделитель строк минимальное высоте и столбец шириной 0. После вызова метода `Create`, настроить эти минимальные значения путем вызова [SetColumnInfo](#setcolumninfo) и [SetRowInfo](#setrowinfo) функций-членов. Также используйте `SetColumnInfo` и `SetRowInfo` после вызова метода `CreateStatic` для указания требуемого идеальной панели измерений.  
  
Отдельные области со статическим разделителем часто принадлежат на различные классы. Примеры windows со статическим разделителем см. в разделе графический редактор и диспетчер файлов Windows.  
  
Окна разделителя поддерживает специальные ползунки (помимо полосы прокрутки, которые могут иметь области). Эти полосы прокрутки являются дочерними элементами `CSplitterWnd` объекта и являются общими с областями.  
  
При создании окна разделителя, создайте эти специальные ползунки. Например `CSplitterWnd` с одной строки, два столбца, и стиль WS_VSCROLL будет отображать вертикальную полосу прокрутки, совместно используется двумя областями. Когда пользователь перемещает полосу прокрутки, WM_VSCROLL сообщения отправляются в обеих областях. При области задать положение полосы прокрутки, полосы прокрутки общего устанавливается.  
  
Дополнительные сведения о окна разделителей см. в разделе:  
  
 - [Техническое Примечание 29](../../mfc/tn029-splitter-windows.md)  
  
 - Статье базы знаний Q262024: Практическое руководство: использование CPropertySheet как дочерние CSplitterWnd  
  
Дополнительные сведения о способах создания окон с динамическими разделителями см. в разделе:  
  
 - Пример MFC [Scribble](../../visual-cpp-samples.md)  
  
 - Пример MFC [VIEWEX](../../visual-cpp-samples.md).  
  
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
 *bPrev*  
 Указывает, какие окна, чтобы активировать. **Значение TRUE,** для предыдущего; **FALSE** к следующему шагу.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член — это высокоуровневая команда, которая используется [CView](../../mfc/reference/cview-class.md) класс делегировать `CSplitterWnd` реализации.  
  
##  <a name="canactivatenext"></a>  CSplitterWnd::CanActivateNext  
 Вызывается платформой для проверки, является ли команды Next Pane и Previous Pane сейчас невозможно.  
  
```  
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *bPrev*  
 Указывает, какие окна, чтобы активировать. **Значение TRUE,** для предыдущего; **FALSE** к следующему шагу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член — это высокоуровневая команда, которая используется [CView](../../mfc/reference/cview-class.md) класс делегировать `CSplitterWnd` реализации.  
  
##  <a name="create"></a>  CSplitterWnd::Create  
 Чтобы создать окно с динамическим разделителем, вызовите `Create` функция-член.  
  
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
 *pParentWnd*  
 Родительское окно фрейма окна разделителя.  
  
 *nMaxRows*  
 Максимальное количество строк в окне разделителя. Это значение не должно превышать 2.  
  
 *nMaxCols*  
 Максимальное количество столбцов в окне разделителя. Это значение не должно превышать 2.  
  
 *sizeMin*  
 Задает минимальный размер, с которой может отображаться область.  
  
 *pContext*  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. В большинстве случаев это может быть *pContext* передается родительское окно фрейма.  
  
 *dwStyle*  
 Указывает стиль окна.  
  
 *nID*  
 Идентификатор дочернего окна окна. Идентификатор может быть AFX_IDW_PANE_FIRST, если разделитель окна вложен в другом окне разделителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно внедрить `CSplitterWnd` родительского элемента [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта, выполнив следующие действия:  
  
1.  Внедрение `CSplitterWnd` переменную-член в родительского фрейма.  
  
2.  Переопределить родительского фрейма [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) функция-член.  
  
3.  Вызовите `Create` функции-члена из в переопределенный `OnCreateClient`.  
  
 При создании окна разделителя из родительского фрейма, передать родительского фрейма *pContext* параметр окна разделителя. В противном случае этот параметр может иметь значение NULL.  
  
 Задаются начальной строки минимальное высоте и столбец ширину динамическое окно разделитель *sizeMin* параметра. Эти минимумы, которые определяют, является ли область слишком мал для отображения целиком, можно изменить с помощью [SetRowInfo](#setrowinfo) и [SetColumnInfo](#setcolumninfo) функций-членов.  
  
 Дополнительные сведения о windows с динамическим разделителем, см. в разделе «Windows разделитель» в статье [несколько типов документов, представлений и фрейма Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [технические 29 Примечание](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` Общие сведения о классе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]  
  
##  <a name="createscrollbarctrl"></a>  CSplitterWnd::CreateScrollBarCtrl  
 Вызывается платформой для создания общего полосы прокрутки.  
  
```  
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *dwStyle*  
 Указывает стиль окна.  
  
 *nID*  
 Идентификатор дочернего окна окна. Идентификатор может быть AFX_IDW_PANE_FIRST, если разделитель окна вложен в другом окне разделителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределить `CreateScrollBarCtrl` для включения дополнительных элементов управления рядом с полосу прокрутки. Поведение по умолчанию — создать обычный элементов управления полосы прокрутки Windows.  
  
##  <a name="createstatic"></a>  CSplitterWnd::CreateStatic  
 Чтобы создать окно со статическим разделителем, вызовите `CreateStatic` функция-член.  
  
```  
virtual BOOL CreateStatic(
    CWnd* pParentWnd,  
    int nRows,  
    int nCols,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Параметры  
 *pParentWnd*  
 Родительское окно фрейма окна разделителя.  
  
 *nRows*  
 Количество строк. Это значение не должно превышать 16.  
  
 *nCols*  
 Количество столбцов. Это значение не должно превышать 16.  
  
 *dwStyle*  
 Указывает стиль окна.  
  
 *nID*  
 Идентификатор дочернего окна окна. Идентификатор может быть AFX_IDW_PANE_FIRST, если разделитель окна вложен в другом окне разделителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Объект `CSplitterWnd` обычно является встроенным в родительский элемент `CFrameWnd` или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта, выполнив следующие действия:  
  
1.  Внедрение `CSplitterWnd` переменную-член в родительского фрейма.  
  
2.  Переопределить родительского фрейма `OnCreateClient` функция-член.  
  
3.  Вызовите `CreateStatic` функции-члена из в переопределенный [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).  
  
 Окно со статическим разделителем содержит фиксированное количество областей, часто из различных классов.  
  
 При создании окна со статическим разделителем, в то же время создайте все области. [CreateView](#createview) функция-член обычно используется для этой цели, но можно создать другие классы nonview.  
  
 Начальной строки Минимальная ширина высоте и столбец для окна со статическим разделителем равна 0. Эти минимумы, которые определяют, когда область слишком мал для отображения целиком, можно изменить с помощью [SetRowInfo](#setrowinfo) и [SetColumnInfo](#setcolumninfo) функций-членов.  
  
 Чтобы добавить полосы прокрутки окна со статическим разделителем, добавить стили WS_HSCROLL и WS_VSCROLL *dwStyle*.  
  
 См. в разделе «Windows разделитель» в статье [несколько типов документов, представлений и фрейма Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [технические 29 Примечание](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` Общие сведения о классе дополнительную информацию о windows со статическим разделителем.  
  
##  <a name="createview"></a>  CSplitterWnd::CreateView  
 Создает область для окна со статическим разделителем.  
  
```  
virtual BOOL CreateView(
    int row,  
    int col,  
    CRuntimeClass* pViewClass,  
    SIZE sizeInit,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Параметры  
 *строки*  
 Задает строку разделителя окно для размещения нового представления.  
  
 *номер столбца*  
 Указывает столбец, окно разделитель для размещения нового представления.  
  
 *pViewClass*  
 Указывает [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) нового представления.  
  
 *sizeInit*  
 Задает первоначальный размер нового представления.  
  
 *pContext*  
 Указатель на контекст создания, используемый для создания представления (обычно *pContext* переданные родительского фрейма переопределенный [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) функция-член в которой является окна разделителя Идет создание).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Все области окна со статическим разделителем должны создаваться, прежде чем платформа отображает разделителя.  
  
 Кроме того, платформа вызывает эта функция-член для создания новой области в том случае, когда пользователь динамическое окно разделитель разделяет области, строки или столбца.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]  
  
##  <a name="csplitterwnd"></a>  CSplitterWnd::CSplitterWnd  
 Вызов для создания `CSplitterWnd` объекта.  
  
```  
CSplitterWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Создать `CSplitterWnd` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CSplitterWnd` объекта, а затем вызвать [создать](#create) функцией-членом, которая создает окно разделитель и присоединяет его к `CSplitterWnd` объекта.  
  
##  <a name="deletecolumn"></a>  CSplitterWnd::DeleteColumn  
 Удаляет колонку из разделителя окна.  
  
```  
virtual void DeleteColumn(int colDelete);
```  
  
### <a name="parameters"></a>Параметры  
 *colDelete*  
 Указывает столбец, для удаления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для реализации логики окно с динамическим разделителем (то есть, если разделитель окна имеет стиль SPLS_DYNAMIC_SPLIT). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="deleterow"></a>  CSplitterWnd::DeleteRow  
 Удаляет строку из окна разделителя.  
  
```  
virtual void DeleteRow(int rowDelete);
```  
  
### <a name="parameters"></a>Параметры  
 *rowDelete*  
 Задает строку для удаления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для реализации логики окно с динамическим разделителем (то есть, если разделитель окна имеет стиль SPLS_DYNAMIC_SPLIT). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="deleteview"></a>  CSplitterWnd::DeleteView  
 Удаляет представление из окна разделителя.  
  
```  
virtual void DeleteView(
    int row,  
    int col);
```  
  
### <a name="parameters"></a>Параметры  
 *строки*  
 Указывает строку окна разделителя, по которому следует удалить представление.  
  
 *номер столбца*  
 Указывает столбец окна разделителя, с которого следует удалить представление.  
  
### <a name="remarks"></a>Примечания  
 Если удаляется активное представление, следующее представление становится доступной. Реализация по умолчанию предполагается, что представление будет автоматически удалять в [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy).  
  
 Эта функция-член вызывается платформой для реализации логики окно с динамическим разделителем (то есть, если разделитель окна имеет стиль SPLS_DYNAMIC_SPLIT). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="dokeyboardsplit"></a>  CSplitterWnd::DoKeyboardSplit  
 Выполняет команду, обычно «Разделение окна». разделения клавиатуры  
  
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
 *pViewFrom*  
 Указатель на представление, от которого исходит сообщение прокрутки.  
  
 *nScrollCode*  
 Код полосы прокрутки, указывающий пользователя прокрутка запроса. Этот параметр состоит из двух частей: младший байт, который определяет тип возникновения прокрутки по горизонтали, и старший байт, который определяет тип возникновения прокрутки по вертикали:  
  
    - SB_BOTTOM выполняет прокрутку вниз.  
      
    - Выполняет прокрутку SB_LINEDOWN одну строку вниз.  
      
    - Выполняет прокрутку SB_LINEUP одну строку вверх.  
      
    - Выполняет прокрутку SB_PAGEDOWN одну страницу вниз.  
      
    - Выполняет прокрутку SB_PAGEUP одну страницу вверх.  
      
    - SB_TOP прокрутка к началу страницы.  
  
 *bDoScroll*  
 Определяет, происходит ли указанное действие прокрутки. Если *bDoScroll* имеет значение TRUE (то есть, в том случае, если существует дочернее окно, и если split windows диапазон прокрутки), а затем прокрутки указанное действие может выполняться; Если *bDoScroll* имеет значение FALSE (то есть, если нет дочернего окна существует, или отсутствует диапазон прокрутки представления с разделением), то прокрутка не происходит.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если происходит на синхронную прокрутку; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для выполнения синхронную прокрутку окна разделителя, когда представление получает сообщение прокрутки. Переопределение требуется действие пользователя, прежде чем будет разрешено синхронную прокрутку.  
  
##  <a name="doscrollby"></a>  CSplitterWnd::DoScrollBy  
 Прокручивает окно разделитель заданное количество пикселей.  
  
```  
virtual BOOL DoScrollBy(
    CView* pViewFrom,  
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *pViewFrom*  
 Указатель на представление, от которого исходит сообщение прокрутки.  
  
 *sizeScroll*  
 Число пикселей для прокручиваться по горизонтали и вертикали.  
  
 *bDoScroll*  
 Определяет, происходит ли указанное действие прокрутки. Если *bDoScroll* имеет значение TRUE (то есть, в том случае, если существует дочернее окно, и если split windows диапазон прокрутки), а затем прокрутки указанное действие может выполняться; Если *bDoScroll* имеет значение FALSE (то есть, если нет дочернего окна существует, или отсутствует диапазон прокрутки представления с разделением), то прокрутка не происходит.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если происходит на синхронную прокрутку; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой в ответ на сообщение прокрутки, для выполнения синхронизации прокрутку окна разделителя на величину, в пикселях, обозначается *sizeScroll*. Положительные значения указывают, прокрутку вниз и вправо; отрицательные значения указывают, прокрутку вверх и влево.  
  
 Переопределите, чтобы требовать вмешательства со стороны пользователя, прежде чем разрешить прокрутки.  
  
##  <a name="getactivepane"></a>  CSplitterWnd::GetActivePane  
 Определяет активную область из фокуса или активное представление во фрейме.  
  
```  
virtual CWnd* GetActivePane(
    int* pRow = NULL,  
    int* pCol = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pRow*  
 Указатель на **int** для получения числа строк активной области.  
  
 *pCol*  
 Указатель на **int** для получения числа столбцов активной области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активной панели. Значение NULL, если существует активных панелей нет.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для определения активной панели в окне разделителя. Переопределение требуется действие пользователя перед получением активной панели.  
  
##  <a name="getcolumncount"></a>  CSplitterWnd::GetColumnCount  
 Возвращает текущее число столбцов для области.  
  
```  
int GetColumnCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее число столбцов в разделителе. Для статического разделителя это будет также максимальное число столбцов.  
  
##  <a name="getcolumninfo"></a>  CSplitterWnd::GetColumnInfo  
 Возвращает сведения для указанного столбца.  
  
```  
void GetColumnInfo(
    int col,  
    int& cxCur,  
    int& cxMin) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *номер столбца*  
 Указывает столбец.  
  
 *cxCur*  
 Ссылку на **int** будет присвоено текущую ширину столбца.  
  
 *cxMin*  
 Ссылку на **int** будет присвоено минимальное текущую ширину столбца.  
  
##  <a name="getpane"></a>  CSplitterWnd::GetPane  
 Возвращает область в указанной строке и столбце.  
  
```  
CWnd* GetPane(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *строки*  
 Указывает строку.  
  
 *номер столбца*  
 Указывает столбец.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает область в указанной строке и столбце. Обычно является области возвращаемый [CView](../../mfc/reference/cview-class.md)-производного класса.  
  
##  <a name="getrowcount"></a>  CSplitterWnd::GetRowCount  
 Возвращает текущее количество строк панели.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее количество строк в окне разделителя. Для окна со статическим разделителем это будет также максимальное число строк.  
  
##  <a name="getrowinfo"></a>  CSplitterWnd::GetRowInfo  
 Возвращает сведения о заданной строки.  
  
```  
void GetRowInfo(
    int row,  
    int& cyCur,  
    int& cyMin) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *строки*  
 Указывает строку.  
  
 *cyCur*  
 Ссылка на **int** будет присвоено текущую высоту строки в пикселях.  
  
 *cyMin*  
 Ссылка на **int** будет присвоено текущего Минимальная высота строки в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции-члена для получения сведений об указанной строки. *CyCur* параметр заполняется текущей высоты указанной строки и *cyMin* заполняется минимальную высоту строки.  
  
##  <a name="getscrollstyle"></a>  CSplitterWnd::GetScrollStyle  
 Возвращает стиль общей полосы прокрутки окна разделителя.  
  
```  
DWORD GetScrollStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один или несколько из следующих окон в стиле флагов, при успешном выполнении:  
  
    - WS_HSCROLL разделителя в настоящее время управляет общим горизонтальных полос прокрутки.  
      
    - WS_VSCROLL, разделитель в настоящее время управляет общим вертикальных полос прокрутки.  
  
 Если значение равно нулю, разделитель окна не управляет полос прокрутки общего, в настоящее время.  
  
##  <a name="idfromrowcol"></a>  CSplitterWnd::IdFromRowCol  
 Получает дочерний идентификатор окна для области в указанной строке и указанном столбце.  
  
```  
int IdFromRowCol(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *строки*  
 Задает строку разделителя окна.  
  
 *номер столбца*  
 Указывает столбец, окно разделитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор дочернего окна для области.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член используется для создания nonviews как области и может быть вызвана, прежде чем области существует.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]  
  
##  <a name="ischildpane"></a>  CSplitterWnd::IsChildPane  
 Определяет, является ли *pWnd* в настоящее время является дочерней области этого окна разделителя.  
  
```  
BOOL IsChildPane(
    CWnd* pWnd,  
    int* pRow,  
    int* pCol);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) проверяемый объект.  
  
 *pRow*  
 Указатель на **int** в котором хранится номер строки.  
  
 *pCol*  
 Указатель на **int** для хранения номер столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если значение ненулевое, *pWnd* в настоящее время является дочерней области этого окна разделителя и *pRow* и *pCol* заполняются положение панели в окне разделителя. Если *pWnd* не является дочерней области окна разделителя, то возвращается значение 0.  
  
### <a name="remarks"></a>Примечания  
 В версиях Visual C++ 6.0 эта функция была определена как  
  
 `BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`  
  
 Эта версия больше не используется и не должны использоваться.  
  
##  <a name="istracking"></a>  CSplitterWnd::IsTracking  
 Вызовите для определения того, если разделитель в окне перемещается в данный момент эта функция-член.  
  
```  
BOOL IsTracking();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если разделитель выполняется операция; в противном случае 0.  
  
##  <a name="ondrawsplitter"></a>  CSplitterWnd::OnDrawSplitter  
 Выполняет отрисовку рисунка окна разделителя.  
  
```  
virtual void OnDrawSplitter(
    CDC* pDC,  
    ESplitType nType,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 *основного контроллера домена*  
 Указатель на контекст устройства, в котором выполняется отрисовка. Если *pDC* имеет значение NULL, затем [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) вызывается с платформой и не разбиение рисуется окна.  
  
 *nType*  
 Значение `enum ESplitType`, который может принимать одно из следующих:  
  
    - `splitBox` Перетащите поле разделителя.  
      
    - `splitBar` Панель, которая расположена между двумя разделенными windows.  
      
    - `splitIntersection` Пересечение окна разделителя. Этот элемент не будет вызываться при выполнении в Windows 95/98.  
      
    - `splitBorder` Границы окна разбиения.  
  
 *Rect*  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, задающий размер и форма окна разделителя.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для подготовки, а также указать точный характеристики окна-разделителя. Переопределить `OnDrawSplitter` для расширенной настройки изображение для различных компонентов графического окна-разделителя. Изображение по умолчанию аналогично разделителя в программе для Windows или Microsoft Windows 95/98, в том, что смешиваются пересечениях полосы разделения.  
  
 Дополнительные сведения о windows с динамическим разделителем, см. в разделе «Windows разделитель» в статье [несколько типов документов, представлений и фрейма Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [технические 29 Примечание](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` Общие сведения о классе.  
  
##  <a name="oninverttracker"></a>  CSplitterWnd::OnInvertTracker  
 Выполняет отрисовку рисунка окна разделителя же размер и форму, что и окно фрейма.  
  
```  
virtual void OnInvertTracker(const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 *Rect*  
 Ссылка на `CRect` объект, указывающий область отслеживания.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой при изменении размера из разделителей. Переопределить `OnInvertTracker` для расширенной настройки изображение окна с разделителями. Изображение по умолчанию аналогично разделителя в программе для Windows или Microsoft Windows 95/98, в том, что смешиваются пересечениях полосы разделения.  
  
 Дополнительные сведения о windows с динамическим разделителем, см. в разделе «Windows разделитель» в статье [несколько типов документов, представлений и фрейма Windows](../../mfc/multiple-document-types-views-and-frame-windows.md), [технические 29 Примечание](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` Общие сведения о классе.  
  
##  <a name="recalclayout"></a>  CSplitterWnd::RecalcLayout  
 Вызов для обновления окна разделителя после настройки размера строки или столбца.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член правильно повторного вывода окна разделителя, после выбора изменения размеров строк и столбцов с [SetRowInfo](#setrowinfo) и [SetColumnInfo](#setcolumninfo) функций-членов. Чтобы изменить размеры строк и столбцов как часть процесса создания перед разделителя окно видимо, не нужно вызывать эту функцию-член.  
  
 Эта функция-член вызывается платформой, каждый раз, когда пользователь изменяет размер окна разделителя или перемещает разбиения.  
  
### <a name="example"></a>Пример  
  См. в примере [CSplitterWnd::SetColumnInfo](#setcolumninfo).  
  
##  <a name="setactivepane"></a>  CSplitterWnd::SetActivePane  
 Устанавливает область активной в одном во фрейме.  
  
```  
virtual void SetActivePane(
    int row,  
    int col,  
    CWnd* pWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *строки*  
 Если *pWnd* имеет значение NULL, указывает строку, в области, где будет активна.  
  
 *номер столбца*  
 Если *pWnd* имеет значение NULL, указывает столбец, в области, где будет активна.  
  
 *pWnd*  
 Указатель на объект `CWnd`. Если значение равно NULL, определяемое области *строки* и *col* имеет значение active. Если значение не NULL, указывает область, которая имеет значение active.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для задания в области как активный, когда пользователь изменяет фокус в область в пределах фрейма окна. Можно явно вызывать `SetActivePane` для изменения фокуса для заданного представления.  
  
 Задать область, указав строки и столбца, **или** , предоставляя *pWnd*.  
  
##  <a name="setcolumninfo"></a>  CSplitterWnd::SetColumnInfo  
 Вызов для задания данных указанного столбца.  
  
```  
void SetColumnInfo(
    int col,  
    int cxIdeal,  
    int cxMin);
```  
  
### <a name="parameters"></a>Параметры  
 *номер столбца*  
 Указывает столбец окна разделителя.  
  
 *cxIdeal*  
 Указывает Оптимальная ширина столбца окна разделителя в пикселях.  
  
 *cxMin*  
 Указывает минимальную ширину столбца окна разделителя в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Эта функция члена для установки нового минимальную ширину и Оптимальная ширина столбца. Минимальное значение столбца определяет, когда будет слишком мал, чтобы полностью отобразить столбец.  
  
 Когда платформа отображает окна разделителя, располагает области в столбцах и строках в соответствии с их идеальной измерений, работа из верхнего левого в правый нижний угол клиентской области окна разделителя.  
  
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
 *строки*  
 Указывает строку разделителя окна.  
  
 *cyIdeal*  
 Указывает идеальные значения высоты строки окна разделителя в пикселях.  
  
 *cyMin*  
 Указывает минимальную высоту строки окна разделителя в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Эта функция члена для задания нового минимальные значения высоты и идеальные значения высоты строки. Минимальное значение строки определяет, когда будет слишком мал, чтобы полностью отобразить строку.  
  
 Когда платформа отображает окна разделителя, располагает области в столбцах и строках в соответствии с их идеальной измерений, работа из верхнего левого в правый нижний угол клиентской области окна разделителя.  
  
##  <a name="setscrollstyle"></a>  CSplitterWnd::SetScrollStyle  
 Указывает, что поддержка полосы прокрутки общих новый стиль прокрутки для окна разделителя.  
  
```  
void SetScrollStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 *dwStyle*  
 Новый стиль прокрутки для окна разделителя общих поддержка полосы прокрутки, которая может принимать одно из следующих значений:  
  
- WS_HSCROLL Create/горизонтальной общей полосы прокрутки.  
  
- WS_VSCROLL Create/вертикальной общей полосы прокрутки.  
  
### <a name="remarks"></a>Примечания  
 После создания полосу прокрутки он не будет уничтожен даже в том случае, если `SetScrollStyle` вызывается без этого стиля; вместо этого эти полос прокрутки. Это позволяет полосы прокрутки сохранить их состояние, несмотря на то, что они скрыты. После вызова метода `SetScrollStyle` необходимо вызвать [RecalcLayout](#recalclayout) для всех изменений в силу.  
  
##  <a name="splitcolumn"></a>  CSplitterWnd::SplitColumn  
 Указывает, где окно фрейма разделяется по вертикали.  
  
```  
virtual BOOL SplitColumn(int cxBefore);
```  
  
### <a name="parameters"></a>Параметры  
 *cxBefore*  
 Позиция, в пикселях, перед которыми будет разделено.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается при создании окна вертикальный разделитель. `SplitColumn` Указывает расположение по умолчанию, где происходит разбиение.  
  
 `SplitColumn` вызывается платформой для реализации логики окно с динамическим разделителем (то есть, если разделитель окна имеет стиль SPLS_DYNAMIC_SPLIT). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="splitrow"></a>  CSplitterWnd::SplitRow  
 Указывает, где окно фрейма разделяется по горизонтали.  
  
```  
virtual BOOL SplitRow(int cyBefore);
```  
  
### <a name="parameters"></a>Параметры  
 *cyBefore*  
 Позиция, в пикселях, перед которыми будет разделено.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается при создании окна горизонтальный разделитель. `SplitRow` Указывает расположение по умолчанию, где происходит разбиение.  
  
 `SplitRow` вызывается платформой для реализации логики окно с динамическим разделителем (то есть, если разделитель окна имеет стиль SPLS_DYNAMIC_SPLIT). Его можно изменить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="ondraw"></a>  CSplitterWnd::OnDraw  
 Вызывается платформой для отрисовки окна разделителя.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 *основного контроллера домена*  
 Указатель на контекст устройства.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Пример MFC: VIEWEX](../../visual-cpp-samples.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CView](../../mfc/reference/cview-class.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)
