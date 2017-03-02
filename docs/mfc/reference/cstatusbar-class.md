---
title: "CStatusBar-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBar
dev_langs:
- C++
helpviewer_keywords:
- indicators, status bar
- CStatusBar class
- status bars
- indicators
- status indicators
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e96070041ef5bcee0865991a14b6484082d8fc91
ms.lasthandoff: 02/24/2017

---
# <a name="cstatusbar-class"></a>CStatusBar-класс
Панель элементов управления со строкой областей текстового вывода или "индикаторов".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CStatusBar : public CControlBar  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStatusBar::CStatusBar](#cstatusbar)|Создает объект `CStatusBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStatusBar::CommandToIndex](#commandtoindex)|Возвращает индекс для идентификатора данного индикатора.|  
|[CStatusBar::Create](#create)|Создает строку состояния, присоединяется к `CStatusBar` объекта и задает исходную высоту шрифта и строки.|  
|[CStatusBar::CreateEx](#createex)|Создает `CStatusBar` объектов с помощью дополнительных стилей для embedded `CStatusBarCtrl` объекта.|  
|[CStatusBar::DrawItem](#drawitem)|Вызывается при изменении внешнего вида панели управления рисование владельцем состояние изменится.|  
|[CStatusBar::GetItemID](#getitemid)|Возвращает идентификатор индикатора для указанного индекса.|  
|[CStatusBar::GetItemRect](#getitemrect)|Возвращает отобразить прямоугольник для указанного индекса.|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Возвращает идентификатор индикатора, стиль и ширину для указанного индекса.|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|Возвращает стиль индикатора для указанного индекса.|  
|[CStatusBar::GetPaneText](#getpanetext)|Возвращает текст индикатора для указанного индекса.|  
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Предоставляет прямой доступ к базовой стандартного элемента управления.|  
|[CStatusBar::SetIndicators](#setindicators)|Задает идентификаторы индикатора.|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Задает идентификатор индикатора, стиль и ширину для указанного индекса.|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|Задает стиль индикатора для указанного индекса.|  
|[CStatusBar::SetPaneText](#setpanetext)|Задает текст индикатора для указанного индекса.|  
  
## <a name="remarks"></a>Примечания  
 Области Вывод часто используются как строки сообщения и как индикаторы состояния. Примеры включают справочное сообщение строки меню, которые кратко объясните команду меню и индикаторов, показывающих состояние SCROLL LOCK, NUM LOCK и других ключей.  
  
 [CStatusBar::GetStatusBarCtrl](#getstatusbarctrl), функции-члена новые 4.0 MFC позволяет воспользоваться преимуществами поддержки общих элементов управления Windows в строке настройки и дополнительную функциональность состояния. `CStatusBar`функции-члены предоставить большую часть функциональных возможностей Windows стандартных элементов управления; Тем не менее, при вызове метода `GetStatusBarCtrl`, можно предоставить вашей строки состояния даже несколько характеристик Windows 95/98 строки состояния. При вызове `GetStatusBarCtrl`, будет возвращена ссылка на `CStatusBarCtrl` объект. В разделе [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Дополнительные сведения о разработке с помощью общих элементов управления Windows. Дополнительные сведения об элементах управления в разделе [Общие элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb775493) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Платформа индикатор сведения хранятся в массиве с помощью индикатора крайней левой позиции 0. При создании строки состояния используется массив идентификаторов, платформа связывает с соответствующей индикаторы строк. Строковый идентификатор или индекс затем можно использовать для доступа к индикатора.  
  
 По умолчанию первый индикатор «эластичной»: занимает не используется в других областях индикатор длины строки состояния, чтобы другие панели по правому краю.  
  
 Чтобы создать строку состояния, выполните следующие действия.  
  
1.  Создать `CStatusBar` объекта.  
  
2.  Вызов [создать](#create) (или [CreateEx](#createex)) функция для создания строки состояния окна и присоединить его к `CStatusBar` объекта.  
  
3.  Вызов [SetIndicators](#setindicators) для присоединения к ним строковый идентификатор каждого индикатора.  
  
 Обновление текста в строке состояния области тремя способами:  
  
1.  Вызов [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) обновление текста в области 0 только.  
  
2.  Вызов [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) в строке состояния `ON_UPDATE_COMMAND_UI` обработчика.  
  
3.  Вызов [SetPaneText](#setpanetext) обновление текста для любой области.  
  
 Вызов [SetPaneStyle](#setpanestyle) обновление стиль панели строки состояния.  
  
 Дополнительные сведения об использовании `CStatusBar`, см. в статье [реализация строки состояния в MFC](../../mfc/status-bar-implementation-in-mfc.md) и [Технические заметки 31: панелей элементов управления](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="a-namecommandtoindexa--cstatusbarcommandtoindex"></a><a name="commandtoindex"></a>CStatusBar::CommandToIndex  
 Возвращает индекс индикатор с заданным идентификатором.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIDFind`  
 Идентификатор строки индикатора, индекс которого требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс индикатора в случае успешного выполнения; -1, если она завершилась неудачно.  
  
### <a name="remarks"></a>Примечания  
 Индекс первого индикатора равно 0.  
  
##  <a name="a-namecreatea--cstatusbarcreate"></a><a name="create"></a>CStatusBar::Create  
 Состояние панели (дочернее окно) создает и связывает его с `CStatusBar` объекта.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) окно которого Windows является родительским элементом в строке состояния объекта.  
  
 `dwStyle`  
 Стиль строки состояния. Помимо стандартных Windows [стили](../../mfc/reference/window-styles.md), поддерживаются следующие стили.  
  
- `CBRS_TOP`Панель находится в верхней части окна фрейма.  
  
- `CBRS_BOTTOM`Панель элементов управления — в нижней части окна области.  
  
- `CBRS_NOALIGN`При изменении размера родительской панели элементов управления не перемещен.  
  
 `nID`  
 Идентификатор дочернего окна панели инструментов  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Также задает начальное шрифт и устанавливает состояние высоту строки на значение по умолчанию.  
  
##  <a name="a-namecreateexa--cstatusbarcreateex"></a><a name="createex"></a>CStatusBar::CreateEx  
 Эта функция вызывается для создания состояния панели (дочернего окна) и связать его с `CStatusBar` объекта.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) окно которого Windows является родительским элементом в строке состояния объекта.  
  
 `dwCtrlStyle`  
 Дополнительные стили для создания внедренных [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) объекта. Значение по умолчанию указывает строку состояния без захвата для изменения размера или подсказки поддержки. Стили полосы состояния поддерживается являются:  
  
- **SBARS_SIZEGRIP** включает элемент управления строки состояния захват для изменения размера в правом конце строки состояния. Захват для изменения размера аналогичны изменяющей размер границы; это прямоугольная область, которая пользователя можно щелкнуть и перетащить для изменения размера родительского окна.  
  
- **SBT_TOOLTIPS** в строке состояния поддерживает подсказки.  
  
 Подробнее об этих стилей см. в разделе [параметры для CStatusBarCtrl](../../mfc/settings-for-the-cstatusbarctrl.md).  
  
 `dwStyle`  
 Стиль панели состояния. Значение по умолчанию указывает, что создано в строке состояния отображается в нижней части окна фрейма. Примените любое сочетание состояния панели управления стилей в [стили окна](../../mfc/reference/window-styles.md) и [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Тем не менее этот параметр необходимо всегда включать стили WS_CHILD и WS_VISIBLE.  
  
 `nID`  
 Идентификатор дочернего окна строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция также задает начальное шрифт и устанавливает состояние высоту строки на значение по умолчанию.  
  
 Используйте `CreateEx`, вместо [создать](#create), когда определенные стили должны присутствовать во время создания внедренные строки состояния. Например, задать `dwCtrlStyle` для **SBT_TOOLTIPS** для отображения всплывающих подсказок в объекте строки состояния.  
  
##  <a name="a-namecstatusbara--cstatusbarcstatusbar"></a><a name="cstatusbar"></a>CStatusBar::CStatusBar  
 Создает `CStatusBar` , создает шрифт по умолчанию строка состояния при необходимости и задается характеристики шрифта для значения по умолчанию.  
  
```  
CStatusBar();
```  
  
##  <a name="a-namedrawitema--cstatusbardrawitem"></a><a name="drawitem"></a>CStatusBar::DrawItem  
 Эта функция-член вызывается инфраструктурой при изменении внешнего вида строка пользовательского состояния.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено. Переопределить эту функцию-член для реализации отрисовки рисование владельцем `CStatusBar` объекта. Приложение должно восстановить всех графических устройств интерфейс (GDI) выбранных объектов в контексте отображения указано в `lpDrawItemStruct` до завершения работы этой функции-члена.  
  
##  <a name="a-namegetitemida--cstatusbargetitemid"></a><a name="getitemid"></a>CStatusBar::GetItemID  
 Возвращает идентификатор индикатора, определяемое `nIndex`.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс, идентификатор которой требуется извлечь индикатора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор определяемого индикатора `nIndex`.  
  
##  <a name="a-namegetitemrecta--cstatusbargetitemrect"></a><a name="getitemrect"></a>CStatusBar::GetItemRect  
 Копирует координат индикатора, определяемое `nIndex` в структуру, на который указывает `lpRect`.  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс прямоугольника, координаты которого должны быть получены индикатора.  
  
 `lpRect`  
 Указывает [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объект, принимающий координат индикатора, определяемое `nIndex`.  
  
### <a name="remarks"></a>Примечания  
 Координаты измеряются в пикселях относительно верхнего левого угла строки состояния.  
  
##  <a name="a-namegetpaneinfoa--cstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CStatusBar::GetPaneInfo  
 Наборы `nID`, `nStyle`, и `cxWidth` идентификатор, стиль и ширину области индикатора в расположении, заданном `nIndex`.  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс области, сведения о которой требуется получить.  
  
 `nID`  
 Ссылка на **UINT** присваивается идентификатор области.  
  
 `nStyle`  
 Ссылка на **UINT** , устанавливается на стиль панели.  
  
 `cxWidth`  
 Ссылка на целое число, равное ширину области.  
  
##  <a name="a-namegetpanestylea--cstatusbargetpanestyle"></a><a name="getpanestyle"></a>CStatusBar::GetPaneStyle  
 Вызовите эту функцию-член для получения стиль панели строки состояния.  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс области, стиль которого требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стиль панели строки состояния, определяемого `nIndex`.  
  
### <a name="remarks"></a>Примечания  
 Стиль области определяет, как области отображается.  
  
 Список стилей, доступных для строки состояния, в разделе [создать](#create).  
  
##  <a name="a-namegetpanetexta--cstatusbargetpanetext"></a><a name="getpanetext"></a>CStatusBar::GetPaneText  
 Вызовите эту функцию-член для извлечения текста, отображаемая на панели строки состояния.  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  ```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be retrieved.  
  
 `rString`  
 A reference to a [CString](../../atl-mfc-shared/reference/cstringt-class.md) object that contains the text to be retrieved.  
  
### Return Value  
 A `CString` object containing the pane's text.  
  
### Remarks  
 The second form of this member function fills a `CString` object with the string text.  
  
##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl  
 This member function allows direct access to the underlying common control.  
  
```  
CStatusBarCtrl & GetStatusBarCtrl() константу;  
```  
  
### Return Value  
 Contains a reference to a [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) object.  
  
### Remarks  
 Use `GetStatusBarCtrl` to take advantage of the functionality of the Windows status-bar common control, and to take advantage of the support [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) provides for status-bar customization. For example, by using the common control, you can specify a style that includes a sizing grip on the status bar, or you can specify a style to have the status bar appear at the top of the parent window's client area.  
  
 For more general information about common controls, See [Common Controls](http://msdn.microsoft.com/library/windows/desktop/bb775493) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setindicators"></a>  CStatusBar::SetIndicators  
 Sets each indicator's ID to the value specified by the corresponding element of the array `lpIDArray`, loads the string resource specified by each ID, and sets the indicator's text to the string.  
  
```  
BOOL SetIndicators (const UINT * lpIDArray,  
    int nIDCount);
```  
  
### Parameters  
 `lpIDArray`  
 Pointer to an array of IDs.  
  
 `nIDCount`  
 Number of elements in the array pointed to by `lpIDArray`.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo  
 Sets the specified indicator pane to a new ID, style, and width.  
  
```  
void SetPaneInfo (int nIndex,  
    UINT nID  
    UINT nStyle  
    int cxWidth);
```  
  
### Parameters  
 `nIndex`  
 Index of the indicator pane whose style is to be set.  
  
 `nID`  
 New ID for the indicator pane.  
  
 `nStyle`  
 New style for the indicator pane.  
  
 `cxWidth`  
 New width for the indicator pane.  
  
### Remarks  
 The following indicator styles are supported:  
  
- **SBPS_NOBORDERS** No 3-D border around the pane.  
  
- **SBPS_POPOUT** Reverse border so that text "pops out."  
  
- **SBPS_DISABLED** Do not draw text.  
  
- **SBPS_STRETCH** Stretch pane to fill unused space. Only one pane per status bar can have this style.  
  
- **SBPS_NORMAL** No stretch, borders, or pop-out.  
  
##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle  
 Call this member function to set the style of a status bar's pane.  
  
```  
void SetPaneStyle (int nIndex,  
    UINT nStyle);
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose style is to be set.  
  
 `nStyle`  
 Style of the pane whose style is to be set.  
  
### Remarks  
 A pane's style determines how the pane appears.  
  
 For a list of styles available for status bars, see [SetPaneInfo](#setpaneinfo).  
  
##  <a name="setpanetext"></a>  CStatusBar::SetPaneText  
 Call this member function to set the pane text to the string pointed to by `lpszNewText`.  
  
```  
SetPaneText BOOL (int nIndex,  
    LPCTSTR lpszNewText  
    BСтратегии обновлениями BOOL = TRUE);
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be set.  
  
 `lpszNewText`  
 Pointer to the new pane text.  
  
 *bUpdate*  
 If **TRUE**, the pane is invalidated after the text is set.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 After you call `SetPaneText`, you must add a UI update handler to display the new text in the status bar.  
  
### Example  
 [!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## See Also  
 [MFC Sample CTRLBARS](../../visual-cpp-samples.md)   
 [MFC Sample DLGCBR32](../../visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl Class](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)

