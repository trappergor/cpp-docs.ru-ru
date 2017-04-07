---
title: "Класс CSplitterWnd | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- static splitter windows
- multiple views
- splitter windows
- views, multiple per frame
- dynamic splitter windows
- CSplitterWnd class
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
caps.latest.revision: 22
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
ms.openlocfilehash: d015aa604c5394ccbe8c7471b70c84763cc00a5b
ms.lasthandoff: 02/24/2017

---
# <a name="csplitterwnd-class"></a>Класс CSplitterWnd
Предоставляет функциональные возможности окна-разделителя, то есть окна, содержащего несколько областей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|Вызов для создания `CSplitterWnd` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](#activatenext)|Выполняет команду следующей или предыдущей области.|  
|[CSplitterWnd::CanActivateNext](#canactivatenext)|Проверяет, если команда следующей или предыдущей области в данный момент возможно.|  
|[CSplitterWnd::Create](#create)|Вызов окна-разделителя динамического создания и присоединить его к `CSplitterWnd` объекта.|  
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|Создает общий полосы прокрутки.|  
|[CSplitterWnd::CreateStatic](#createstatic)|Вызов создания статическое окно-разделитель и присоединить его к `CSplitterWnd` объекта.|  
|[CSplitterWnd::CreateView](#createview)|Вызов для создания области в окно-разделитель.|  
|[CSplitterWnd::DeleteColumn](#deletecolumn)|Удаление столбца из окна-разделителя.|  
|[CSplitterWnd::DeleteRow](#deleterow)|Удаляет строку из окна-разделителя.|  
|[CSplitterWnd::DeleteView](#deleteview)|Удаляет представление из окна разделителя.|  
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|Выполняет клавиатуры разделить команды, обычно «Разделение окна».|  
|[CSplitterWnd::DoScroll](#doscroll)|Выполняет синхронную прокрутку окна разделителя.|  
|[CSplitterWnd::DoScrollBy](#doscrollby)|Прокручивает окно разделитель заданное количество точек.|  
|[CSplitterWnd::GetActivePane](#getactivepane)|Определяет активную область из фокуса или активное представление в рамке.|  
|[CSplitterWnd::GetColumnCount](#getcolumncount)|Возвращает число столбцов текущей области.|  
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|Возвращает сведения об указанном столбце.|  
|[CSplitterWnd::GetPane](#getpane)|Возвращает область в указанной строке и столбце.|  
|[CSplitterWnd::GetRowCount](#getrowcount)|Возвращает число строк текущей области.|  
|[CSplitterWnd::GetRowInfo](#getrowinfo)|Возвращает сведения о заданной строки.|  
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|Возвращает стиль общей полосы прокрутки.|  
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|Возвращает дочерний идентификатор области в указанной строке и столбце окна.|  
|[CSplitterWnd::IsChildPane](#ischildpane)|Вызов для определения окна находится ли область дочернего окна-разделителя.|  
|[CSplitterWnd::IsTracking](#istracking)|Определяет, если разделитель перемещается в данный момент.|  
|[CSplitterWnd::RecalcLayout](#recalclayout)|Вызов на экран окна-разделителя после изменения размера строки или столбца.|  
|[CSplitterWnd::SetActivePane](#setactivepane)|Задает область, чтобы сделать активным в кадре.|  
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|Вызов для задания данных указанного столбца.|  
|[CSplitterWnd::SetRowInfo](#setrowinfo)|Вызов для установки информации указанной строки.|  
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|Указывает, что поддержка полосы прокрутки общих новый стиль полоса прокрутки окна-разделителя.|  
|[CSplitterWnd::SplitColumn](#splitcolumn)|Указывает, где рамка окна разделяет вертикально.|  
|[CSplitterWnd::SplitRow](#splitrow)|Указывает, где рамка окна разделяет горизонтально.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](#ondraw)|Вызывается платформой для рисования окно-разделитель.|  
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|Отображает рисунок окна разделителя.|  
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|Отображает рисунок окна разделителя же размер и форму, что окна фрейма.|  
  
## <a name="remarks"></a>Примечания  
 Области обычно является производным от объекта конкретного приложения [CView](../../mfc/reference/cview-class.md), но он может быть любой [CWnd](../../mfc/reference/cwnd-class.md) объекта с идентификатором соответствующее дочернее окно.  
  
 Объект `CSplitterWnd` объект обычно внедрен в родительский [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта. Создание `CSplitterWnd` объекта, выполнив следующие действия:  
  
1.  Внедрение `CSplitterWnd` переменной-члена в родительского фрейма.  
  
2.  Переопределение родительского фрейма [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) функции-члена.  
  
3.  Из переопределенного `OnCreateClient`, вызовите [создать](#create) или [CreateStatic](#createstatic) функции-члена `CSplitterWnd`.  
  
 Вызов **создать** функции-члена для создания динамическое окно разделитель. Динамическое окно разделитель обычно используется для создания и прокрутите ряд отдельных областей или представления одного документа. Платформа автоматически создает область начального разделителя; Затем платформа создает, изменяет и удаляет дополнительные области как элементы управления окна-разделителя работает пользователь.  
  
 При вызове **создать**, укажите минимальное высоте и столбец ширина строки, определяющие, когда области слишком малы для полного отображения. После вызова метода **создать**, можно настроить эти минимальные значения путем вызова [SetColumnInfo](#setcolumninfo) и [SetRowInfo](#setrowinfo) функции-члены.  
  
 Также используйте `SetColumnInfo` и `SetRowInfo` функции-члены для задать ширину столбца «идеальная» и «идеальная» высоту строки. Когда платформа отобразит окно-разделитель, то сначала он отображает родительского фрейма, а затем окна-разделителя. Затем платформа располагает панелей в столбцы и строки согласно их идеальным измерений, работа из верхнего левого в правый нижний угол клиентской области окна-разделителя.  
  
 Все области в окне динамический разделитель должен иметь тот же класс. Microsoft Word и Microsoft Excel, включают привычные приложения, поддерживающие динамические окна-разделители.  
  
 Используйте `CreateStatic` функции-члена для создания статическое окно-разделитель. Он может изменять размер панелей в статический разделитель окна, а не их количество или порядок.  
  
 Все статические разделителя в областях необходимо создать специально при создании статический разделитель. Убедитесь, что создание всех панелей до родительского фрейма `OnCreateClient` функция возвращает элемент, или framework будет отображаться окно неправильно.  
  
 `CreateStatic` Функция-член автоматически инициализирует статический разделитель строк минимальное высоте и столбец шириной 0. После вызова метода **создать**, настройте эти минимальные значения путем вызова [SetColumnInfo](#setcolumninfo) и [SetRowInfo](#setrowinfo) функции-члены. Также используйте `SetColumnInfo` и `SetRowInfo` после вызова метода `CreateStatic` для указания необходимости идеальной панели измерений.  
  
 Отдельные области статический разделитель часто принадлежат разным классам. Примеры из окна со статическим разделителем графический редактор и диспетчер файлов см.  
  
 Окна-разделителя поддерживает специальные ползунки (помимо полосы прокрутки, которые могут иметь области). Эти полосы прокрутки являются дочерними элементами элемента `CSplitterWnd` объекта и совместно с областями.  
  
 Эти специальные ползунки создать при создании окна-разделителя. Например `CSplitterWnd` , имеет одну строку, два столбца и **WS_VSCROLL** стиль будет отображать вертикальную полосу прокрутки, разделяется на две области. Когда пользователь перемещает полосы прокрутки, `WM_VSCROLL` сообщения отправляются в обеих областях. При панелей задать положение полосы прокрутки, полосы прокрутки общего устанавливается.  
  
 Дополнительные сведения об окнах разделителей см.:  
  
- [Техническое Примечание 29](../../mfc/tn029-splitter-windows.md)  
  
-   Статья базы знаний Q262024: Практическое руководство: использование CPropertySheet как дочерние CSplitterWnd  
  
 Дополнительные сведения о том, как создавать динамические окна-разделители, см.:  
  
-   Пример MFC [Scribble](../../visual-cpp-samples.md)  
  
-   Пример MFC [приложения](../../visual-cpp-samples.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="activatenext"></a>CSplitterWnd::ActivateNext  
 Вызывается платформой для выполнения команды следующей или предыдущей области.  
  
```  
virtual void ActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bPrev`  
 Указывает, какое окно для активации. **Значение TRUE,** для предыдущего; **FALSE** для следующего.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является команда высокого уровня, которая используется [CView](../../mfc/reference/cview-class.md) класс делегировать `CSplitterWnd` реализации.  
  
##  <a name="canactivatenext"></a>CSplitterWnd::CanActivateNext  
 Вызывается платформой для проверки, если команда следующей или предыдущей области в данный момент возможно.  
  
```  
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bPrev`  
 Указывает, какое окно для активации. **Значение TRUE,** для предыдущего; **FALSE** для следующего.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является команда высокого уровня, которая используется [CView](../../mfc/reference/cview-class.md) класс делегировать `CSplitterWnd` реализации.  
  
##  <a name="create"></a>CSplitterWnd::Create  
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
 Родительское окно фрейма окна разделителя.  
  
 *nMaxRows*  
 Максимальное число строк в окно-разделитель. Это значение не должно превышать 2.  
  
 *nMaxCols*  
 Максимальное количество столбцов в окно-разделитель. Это значение не должно превышать 2.  
  
 `sizeMin`  
 Задает минимальный размер, с которой может отображаться область.  
  
 `pContext`  
 Указатель на [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. В большинстве случаев это может быть `pContext` передан родительский фрейм окна.  
  
 `dwStyle`  
 Указывает стиль окна.  
  
 `nID`  
 Идентификатор окна дочернего окна. Идентификатор может быть **AFX_IDW_PANE_FIRST** Если окна-разделителя вложен в другой окно-разделитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно внедрить `CSplitterWnd` в родительском элементе [CFrameWnd](../../mfc/reference/cframewnd-class.md) или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта, выполнив следующие действия:  
  
1.  Внедрение `CSplitterWnd` переменной-члена в родительского фрейма.  
  
2.  Переопределение родительского фрейма [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) функции-члена.  
  
3.  Вызов **создать** функции-члена из переопределенного `OnCreateClient`.  
  
 При создании из окна-разделителя в пределах родительского фрейма передать родительского фрейма `pContext` параметр окна-разделителя. В противном случае — этот параметр может иметь **NULL**.  
  
 Задается начальной строки минимальное высоте и столбец ширину окна-разделителя динамического `sizeMin` параметр. Эти минимальные значения, которые определяют ли область слишком мал для отображения целиком, можно изменить при помощи [SetRowInfo](#setrowinfo) и [SetColumnInfo](#setcolumninfo) функции-члены.  
  
 Дополнительные сведения о окна с динамическим разделителем см «Разделитель Windows» в статье [несколько типов документов, представления и окна фрейма](../../mfc/multiple-document-types-views-and-frame-windows.md), [29 Технические заметки](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` о классе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#125;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]  
  
##  <a name="createscrollbarctrl"></a>CSplitterWnd::CreateScrollBarCtrl  
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
 Идентификатор окна дочернего окна. Идентификатор может быть **AFX_IDW_PANE_FIRST** Если окна-разделителя вложен в другой окно-разделитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `CreateScrollBarCtrl` для включения дополнительных элементов управления рядом с полосы прокрутки. Поведение по умолчанию является создание обычных элементов управления полосы прокрутки Windows.  
  
##  <a name="createstatic"></a>CSplitterWnd::CreateStatic  
 Чтобы создать статическое окно-разделитель, вызовите `CreateStatic` функции-члена.  
  
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
 Родительское окно фрейма окна разделителя.  
  
 `nRows`  
 Количество строк. Это значение не должно превышать 16.  
  
 *nCols*  
 Количество столбцов. Это значение не должно превышать 16.  
  
 `dwStyle`  
 Указывает стиль окна.  
  
 `nID`  
 Идентификатор окна дочернего окна. Идентификатор может быть **AFX_IDW_PANE_FIRST** Если окна-разделителя вложен в другой окно-разделитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Объект `CSplitterWnd` обычно является встроенным в родительскую папку `CFrameWnd` или [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) объекта, выполнив следующие действия:  
  
1.  Внедрение `CSplitterWnd` переменной-члена в родительского фрейма.  
  
2.  Переопределение родительского фрейма `OnCreateClient` функции-члена.  
  
3.  Вызов `CreateStatic` функции-члена из переопределенного [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient).  
  
 Статическое окно-разделитель содержит фиксированное число областей, часто от разных классов.  
  
 При создании статическое окно-разделитель, необходимо одновременно создать все области. [CreateView](#createview) для этого обычно используется функция-член, но можно создать другие классы nonview.  
  
 Начальной строки Минимальная высота и столбец по ширине статическое окно-разделитель — 0. Эти минимальные значения, которые определяют, когда область слишком мало для отображения целиком, можно изменить при помощи [SetRowInfo](#setrowinfo) и [SetColumnInfo](#setcolumninfo) функции-члены.  
  
 Чтобы добавить полосы прокрутки статическое окно-разделитель, добавьте **WS_HSCROLL** и **WS_VSCROLL** стили в `dwStyle`.  
  
 См. в статье «Разделитель Windows» [несколько типов документов, представления и окна фрейма](../../mfc/multiple-document-types-views-and-frame-windows.md), [29 Технические заметки](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` о классе для получения дополнительных сведений о окна со статическим разделителем.  
  
##  <a name="createview"></a>CSplitterWnd::CreateView  
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
 Указатель на создание контекста, используемый для создания представления (обычно `pContext` передан родительского фрейма переопределенный [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) создания окна-разделителя функции-члена).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Все области статическое окно-разделитель должны создаваться до отображения платформе разделителя.  
  
 Платформа также вызывает эту функцию-член для создания новых панелей, когда пользователь динамическое окно разделитель разделяет область, строки или столбца.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#4;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]  
  
##  <a name="csplitterwnd"></a>CSplitterWnd::CSplitterWnd  
 Вызов для создания `CSplitterWnd` объекта.  
  
```  
CSplitterWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Создать `CSplitterWnd` объекта в два этапа. Во-первых, вызовите конструктор, который создает `CSplitterWnd` , а затем вызвать [создать](#create) функция-член, который создает окно-разделитель и присоединяет его к `CSplitterWnd` объекта.  
  
##  <a name="deletecolumn"></a>CSplitterWnd::DeleteColumn  
 Удаление столбца из окна-разделителя.  
  
```  
virtual void DeleteColumn(int colDelete);
```  
  
### <a name="parameters"></a>Параметры  
 *colDelete*  
 Указывает столбец, удаляется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для реализации логики динамическое окно разделитель (то есть, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно настроить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="deleterow"></a>CSplitterWnd::DeleteRow  
 Удаляет строку из окна-разделителя.  
  
```  
virtual void DeleteRow(int rowDelete);
```  
  
### <a name="parameters"></a>Параметры  
 *rowDelete*  
 Указывает строка удаляется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для реализации логики динамическое окно разделитель (то есть, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно настроить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="deleteview"></a>CSplitterWnd::DeleteView  
 Удаляет представление из окна разделителя.  
  
```  
virtual void DeleteView(
    int row,  
    int col);
```  
  
### <a name="parameters"></a>Параметры  
 `row`  
 Задает строку разделителя окна с которого необходимо удалить представление.  
  
 `col`  
 Указывает столбец окно разделитель, на котором удалить представление.  
  
### <a name="remarks"></a>Примечания  
 Следующее представление становится доступной, если удаляется активное представление. Реализация по умолчанию предполагается, что представление будет автоматически удалять в [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy).  
  
 Эта функция-член вызывается платформой для реализации логики динамическое окно разделитель (то есть, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно настроить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="dokeyboardsplit"></a>CSplitterWnd::DoKeyboardSplit  
 Выполняет клавиатуры разделить команды, обычно «Разделение окна».  
  
```  
virtual BOOL DoKeyboardSplit();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член является команда высокого уровня, которая используется [CView](../../mfc/reference/cview-class.md) класс делегировать `CSplitterWnd` реализации.  
  
##  <a name="doscroll"></a>CSplitterWnd::DoScroll  
 Выполняет синхронную прокрутку окна разделителя.  
  
```  
virtual BOOL DoScroll(
    CView* pViewFrom,  
    UINT nScrollCode,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pViewFrom`  
 Указатель на представление, с которого отправляются сообщения прокрутки.  
  
 `nScrollCode`  
 Полоса прокрутки код, который указывает пользователь прокрутка запроса. Этот параметр состоит из двух частей: младший байт, который определяет тип возникновения прокрутки по горизонтали, а старший байт, который определяет тип возникновения прокрутки по вертикали:  
  
- **SB_BOTTOM** выполняет прокрутку вниз.  
  
- **SB_LINEDOWN** прокручивает одну строку вниз.  
  
- **SB_LINEUP** прокручивает одну строку вверх.  
  
- **SB_PAGEDOWN** прокручивании одной страницы.  
  
- **SB_PAGEUP** прокручивает одну страницу вверх.  
  
- **SB_TOP** прокручивается в начало.  
  
 `bDoScroll`  
 Определяет, происходит ли указанное действие прокрутки. Если `bDoScroll` является **TRUE** (то есть, если существует дочернее окно и если windows разбиения диапазон прокрутки), то указанное действие прокрутки может выполняться; Если `bDoScroll` — **FALSE** (то есть, если отсутствует дочерний период или диапазон прокрутки не имеют представления с разделением), затем прокрутки не возникает.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если происходит синхронную прокрутку; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для выполнения синхронную прокрутку окна разделителя, когда представление получает сообщение прокрутки. Переопределение синхронную прокрутку может требоваться действие пользователя.  
  
##  <a name="doscrollby"></a>CSplitterWnd::DoScrollBy  
 Прокручивает окно разделитель заданное количество точек.  
  
```  
virtual BOOL DoScrollBy(
    CView* pViewFrom,  
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pViewFrom`  
 Указатель на представление, с которого отправляются сообщения прокрутки.  
  
 `sizeScroll`  
 Число пикселей прокручиваться по горизонтали и вертикали.  
  
 bDoScroll  
 Определяет, происходит ли указанное действие прокрутки. Если `bDoScroll` является **TRUE** (то есть, если существует дочернее окно и если windows разбиения диапазон прокрутки), то указанное действие прокрутки может выполняться; Если `bDoScroll` — **FALSE** (то есть, если отсутствует дочерний период или диапазон прокрутки не имеют представления с разделением), затем прокрутки не возникает.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если происходит синхронную прокрутку; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой в ответ на сообщение прокрутки, для выполнения синхронизации прокрутку окна разделителя на величину, в пикселях, обозначенными `sizeScroll`. Положительные значения указывают прокрутку вниз и вправо; отрицательные значения указывают прокрутку вверх и влево.  
  
 Переопределение требуют вмешательства со стороны пользователя перед предоставлением прокрутки.  
  
##  <a name="getactivepane"></a>CSplitterWnd::GetActivePane  
 Определяет активную область из фокуса или активное представление в рамке.  
  
```  
virtual CWnd* GetActivePane(
    int* pRow = NULL,  
    int* pCol = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pRow`  
 Указатель на **int** для получения числа строк для активной области.  
  
 `pCol`  
 Указатель на **int** для извлечения номера столбца на активной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активной панели. **NULL** существования нет активной области.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для определения активной области в окно-разделитель. Переопределение требуют вмешательства со стороны пользователя перед получением активной области.  
  
##  <a name="getcolumncount"></a>CSplitterWnd::GetColumnCount  
 Возвращает число столбцов текущей области.  
  
```  
int GetColumnCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее число столбцов в разделителя. Для статического разделителя это будет также максимальное число столбцов.  
  
##  <a name="getcolumninfo"></a>CSplitterWnd::GetColumnInfo  
 Возвращает сведения об указанном столбце.  
  
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
 Ссылку на `int` будет присвоено текущую ширину столбца.  
  
 `cxMin`  
 Ссылку на `int` будет присвоено значение текущей минимальную ширину столбца.  
  
##  <a name="getpane"></a>CSplitterWnd::GetPane  
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
  
##  <a name="getrowcount"></a>CSplitterWnd::GetRowCount  
 Возвращает число строк текущей области.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее число строк в окно-разделитель. Для статическое окно-разделитель это будет также максимальное число строк.  
  
##  <a name="getrowinfo"></a>CSplitterWnd::GetRowInfo  
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
 Ссылка на `int` будет присвоено текущую высоту строки в пикселях.  
  
 `cyMin`  
 Ссылка на `int` будет присвоено значение текущей Минимальная высота строки в точках.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для получения сведений об указанной строки. `cyCur` Параметр заполняется из текущей высоты указанной строки и `cyMin` заполняется минимальную высоту строки.  
  
##  <a name="getscrollstyle"></a>CSplitterWnd::GetScrollStyle  
 Возвращает стиль общего полоса прокрутки окна-разделителя.  
  
```  
DWORD GetScrollStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один или несколько из следующих окон стиля флаги, в случае успешного выполнения:  
  
- **WS_HSCROLL** Если разделитель в настоящее время управляет общего горизонтальные полосы прокрутки.  
  
- **WS_VSCROLL** Если разделитель в настоящее время управляет общего вертикальных полос прокрутки.  
  
 Если значение равно нулю, окно-разделитель не находится под управлением любого общего ползунки.  
  
##  <a name="idfromrowcol"></a>CSplitterWnd::IdFromRowCol  
 Получает дочерний идентификатор области в указанной строке и столбце окна.  
  
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
 Идентификатор дочернего окна для области.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член используется для создания nonviews как областей и может быть вызвана до области существует.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#5;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]  
  
##  <a name="ischildpane"></a>CSplitterWnd::IsChildPane  
 Определяет, является ли `pWnd` область дочернего окна-разделителя в данный момент.  
  
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
 Указатель на `int` для хранения номер строки.  
  
 `pCol`  
 Указатель на `int` для хранения номер столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если значение ненулевое, `pWnd` в данный момент дочерние области этого окна-разделителя, и `pRow` и `pCol` будут заполнены положение панели в окно-разделитель. Если `pWnd` не области дочернего окна разделителей, возвращается значение 0.  
  
### <a name="remarks"></a>Примечания  
 В версиях Visual C++ 6.0 эта функция была определена как  
  
 `BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`  
  
 Эта версия больше не используется и не должен использоваться.  
  
##  <a name="istracking"></a>CSplitterWnd::IsTracking  
 Вызовите эту функцию-член для определения, если выполняется перемещение полосы разделения в окне.  
  
```  
BOOL IsTracking();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция разделитель выполняется; в противном случае — 0.  
  
##  <a name="ondrawsplitter"></a>CSplitterWnd::OnDrawSplitter  
 Отображает рисунок окна разделителя.  
  
```  
virtual void OnDrawSplitter(
    CDC* pDC,  
    ESplitType nType,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства для рисования. Если `pDC` — **NULL**, затем [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) вызывается framework и отсутствие разбиения рисуется окна.  
  
 `nType`  
 Значение **перечисления ESplitType**, который может принимать одно из следующих:  
  
- **splitBox** перетащить разделитель.  
  
- `splitBar`Панель, которая отображается между двумя разделенными windows.  
  
- **splitIntersection** пересечение windows разбиения. Этот элемент не будет вызываться при запуске в Windows 95/98.  
  
- **splitBorder** границы окна разбиения.  
  
 `rect`  
 Ссылку на [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, указывающий размер и форму windows разбиения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для рисования и указать точное характеристики окна-разделителя. Переопределение `OnDrawSplitter` для расширенной настройки изображения для различных компонентов графического окна-разделителя. Изображения по умолчанию аналогична разделителя в программе для Windows или Microsoft Windows 95/98 в смешиваются пересечениях полосы разделения.  
  
 Дополнительные сведения о окна с динамическим разделителем см «Разделитель Windows» в статье [несколько типов документов, представления и окна фрейма](../../mfc/multiple-document-types-views-and-frame-windows.md), [29 Технические заметки](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` о классе.  
  
##  <a name="oninverttracker"></a>CSplitterWnd::OnInvertTracker  
 Отображает рисунок окна разделителя же размер и форму, что окна фрейма.  
  
```  
virtual void OnInvertTracker(const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Ссылка на `CRect` объект, задающий отслеживающего прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается средой во время изменения размера разделителей. Переопределение `OnInvertTracker` для расширенной настройки изображение окна-разделителя. Изображения по умолчанию аналогична разделителя в программе для Windows или Microsoft Windows 95/98 в смешиваются пересечениях полосы разделения.  
  
 Дополнительные сведения о окна с динамическим разделителем см «Разделитель Windows» в статье [несколько типов документов, представления и окна фрейма](../../mfc/multiple-document-types-views-and-frame-windows.md), [29 Технические заметки](../../mfc/tn029-splitter-windows.md)и `CSplitterWnd` о классе.  
  
##  <a name="recalclayout"></a>CSplitterWnd::RecalcLayout  
 Вызов на экран окна-разделителя после изменения размера строки или столбца.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член правильно отобразите окно-разделитель, после выбора изменения размеров строк и столбцов с [SetRowInfo](#setrowinfo) и [SetColumnInfo](#setcolumninfo) функции-члены. Если изменить размеры строк и столбцов в процессе создания отображается окно-разделитель, не нужно вызывать эту функцию-член.  
  
 Платформа вызывает эту функцию-член, всякий раз, когда пользователь изменяет размер окна-разделителя или перемещает разбиения.  
  
### <a name="example"></a>Пример  
  В примере показано [CSplitterWnd::SetColumnInfo](#setcolumninfo).  
  
##  <a name="setactivepane"></a>CSplitterWnd::SetActivePane  
 Задает область, чтобы сделать активным в кадре.  
  
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
 Указатель на объект `CWnd`. Если **NULL**, области, определяемой `row` и `col` устанавливается active. Если не **NULL**, указывает области, в которой задается active.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для область набора как активные, при изменении пользователем фокуса на панель в фрейме окна. Можно явно вызывать `SetActivePane` для изменения фокуса на указанное представление.  
  
 Задать область, указав строки и столбца, **или** , предоставляя `pWnd`.  
  
##  <a name="setcolumninfo"></a>CSplitterWnd::SetColumnInfo  
 Вызов для задания данных указанного столбца.  
  
```  
void SetColumnInfo(
    int col,  
    int cxIdeal,  
    int cxMin);
```  
  
### <a name="parameters"></a>Параметры  
 `col`  
 Указывает столбец, окно разделитель.  
  
 *cxIdeal*  
 Задает оптимальную ширину столбца окна разделителя в пикселях.  
  
 `cxMin`  
 Указывает минимальную ширину столбца окна разделителя в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член можно задать новый минимальную ширину и Оптимальная ширина столбца. Минимальное значение столбца определяет, когда будет слишком мало для полного отображения столбца.  
  
 Когда платформа отобразит окно-разделитель, размещает панелей в столбцы и строки согласно их идеальным измерений, работа из верхнего левого в правый нижний угол клиентской области окна-разделителя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing №&6;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]  
  
##  <a name="setrowinfo"></a>CSplitterWnd::SetRowInfo  
 Вызов для установки информации указанной строки.  
  
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
 Вызовите эту функцию-член можно задать новый минимальную высоту и Идеальная высота строки. Минимальное значение строки определяет, когда будет слишком мало для полного отображения строки.  
  
 Когда платформа отобразит окно-разделитель, размещает панелей в столбцы и строки согласно их идеальным измерений, работа из верхнего левого в правый нижний угол клиентской области окна-разделителя.  
  
##  <a name="setscrollstyle"></a>CSplitterWnd::SetScrollStyle  
 Указывает, что поддержка полосы прокрутки общих новый стиль прокрутки окна-разделителя.  
  
```  
void SetScrollStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Новый стиль прокрутки окна-разделителя общего поддержка полосы прокрутки, которая может принимать одно из следующих значений:  
  
- **WS_HSCROLL** общих Создание и Отображение горизонтальной полосы прокрутки.  
  
- **WS_VSCROLL** общего Создание и Отображение вертикальной полосы прокрутки.  
  
### <a name="remarks"></a>Примечания  
 После создания полосу прокрутки его, не будут уничтожены даже в том случае, если `SetScrollStyle` вызывается без стиля; вместо этого эти полос прокрутки. Это позволяет сохранить свое состояние, даже если они скрыты полосы прокрутки. После вызова метода `SetScrollStyle` необходимо вызвать [RecalcLayout](#recalclayout) все изменения вступили в силу.  
  
##  <a name="splitcolumn"></a>CSplitterWnd::SplitColumn  
 Указывает, где рамка окна разделяет вертикально.  
  
```  
virtual BOOL SplitColumn(int cxBefore);
```  
  
### <a name="parameters"></a>Параметры  
 *cxBefore*  
 Позиция, в пикселях, перед которыми происходит разбиение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается при создании окна вертикального разделителя. `SplitColumn`Указывает расположение по умолчанию, где происходит разбиение.  
  
 `SplitColumn`вызывается платформой для реализации логики динамическое окно разделитель (то есть, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно настроить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="splitrow"></a>CSplitterWnd::SplitRow  
 Указывает, где рамка окна разделяет горизонтально.  
  
```  
virtual BOOL SplitRow(int cyBefore);
```  
  
### <a name="parameters"></a>Параметры  
 *cyBefore*  
 Позиция, в пикселях, перед которыми происходит разбиение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается при создании окна горизонтальный разделитель. `SplitRow`Указывает расположение по умолчанию, где происходит разбиение.  
  
 `SplitRow`вызывается платформой для реализации логики динамическое окно разделитель (то есть, если имеет окна-разделителя **SPLS_DYNAMIC_SPLIT** стиль). Его можно настроить, а также виртуальную функцию [CreateView](#createview), чтобы реализовать более сложные динамические разделителей.  
  
##  <a name="ondraw"></a>CSplitterWnd::OnDraw  
 Вызывается платформой для рисования окно-разделитель.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Пример MFC приложения](../../visual-cpp-samples.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)

