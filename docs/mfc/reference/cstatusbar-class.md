---
title: CStatusBar-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
dev_langs:
- C++
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 199aa7adc6cb96a4bc92e196ff94d57abdedfede
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374303"
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
|[CStatusBar::Create](#create)|Создает строку состояния, присоединяется к `CStatusBar` и устанавливает Начальная высота шрифта и строка.|  
|[CStatusBar::CreateEx](#createex)|Создает `CStatusBar` дополнительные стили для внедренного объекта `CStatusBarCtrl` объекта.|  
|[CStatusBar::DrawItem](#drawitem)|Вызывается при изменении внешнего вида рисуемый владельцем строке состояния элемента управления изменяется.|  
|[CStatusBar::GetItemID](#getitemid)|Возвращает идентификатор индикатора для указанного индекса.|  
|[CStatusBar::GetItemRect](#getitemrect)|Возвращает отображение прямоугольник для указанного индекса.|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Возвращает идентификатор индикатора, стиля и ширины для данного индекса.|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|Возвращает стиль индикатора для указанного индекса.|  
|[CStatusBar::GetPaneText](#getpanetext)|Возвращает текст индикатора для указанного индекса.|  
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Предоставляет прямой доступ к базовой стандартного элемента управления.|  
|[CStatusBar::SetIndicators](#setindicators)|Задает идентификаторы индикатора.|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Задает идентификатор индикатора, стиль и ширину для указанного индекса.|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|Задает стиль индикатора для указанного индекса.|  
|[CStatusBar::SetPaneText](#setpanetext)|Задает текст индикатора для указанного индекса.|  
  
## <a name="remarks"></a>Примечания  
 Панелей вывода часто используются как строки сообщения и в качестве индикаторов состояния. Примеры включают справочное сообщение строки меню, которые кратко объясните команду меню и индикаторы, которые показывают состояние SCROLL LOCK, NUM LOCK и другие ключи.  
  
 [CStatusBar::GetStatusBarCtrl](#getstatusbarctrl), функция-член новые 4.0 MFC позволяет воспользоваться преимуществами общих элементов управления Windows поддержка строки дополнительные функциональные возможности и настройки состояния. `CStatusBar` функции-члены обеспечивают большую часть функций общих элементов управления Windows; Тем не менее, при вызове `GetStatusBarCtrl`, можно дать вашей строки состояния даже несколько характеристик строки состояния Windows 95/98. При вызове `GetStatusBarCtrl`, он возвращает ссылку на `CStatusBarCtrl` объекта. В разделе [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Дополнительные сведения о разработке с помощью стандартных элементов управления Windows. Дополнительные общие сведения о стандартных элементах управления см. в разделе [стандартные элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb775493) в Windows SDK.  
  
 Платформа хранит сведения индикатор в виде массива с крайнего левого индикатора в позиции 0. При создании строки состояния используется массив строк платформа связывает с индикаторами, соответствующих идентификаторам. Строковый идентификатор или индекс затем можно использовать для доступа к индикатора.  
  
 По умолчанию является «эластичной» первого индикатора: она занимает не используются в других областях индикатор длины строки состояния, таким образом, другие панели по правому краю.  
  
 Чтобы создать строку состояния, выполните следующие действия.  
  
1.  Создать `CStatusBar` объекта.  
  
2.  Вызовите [создать](#create) (или [CreateEx](#createex)) функция для создания строки состояния окна и присоединить его к `CStatusBar` объекта.  
  
3.  Вызовите [SetIndicators](#setindicators) связываемый с каждого индикатора идентификатора строки.  
  
 Обновление текста в строке состояния области тремя способами:  
  
1.  Вызовите [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) обновление текста в области только для 0.  
  
2.  Вызовите [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) в строке состояния `ON_UPDATE_COMMAND_UI` обработчика.  
  
3.  Вызовите [SetPaneText](#setpanetext) обновление текста для любой панели.  
  
 Вызовите [SetPaneStyle](#setpanestyle) измените стиль панели строки состояния.  
  
 Дополнительные сведения об использовании `CStatusBar`, см. в статье [реализация строки состояния в MFC](../../mfc/status-bar-implementation-in-mfc.md) и [Технические заметки 31: панелей элементов управления](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxext.h  
  
##  <a name="commandtoindex"></a>  CStatusBar::CommandToIndex  
 Возвращает индекс индикатор с заданным идентификатором.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIDFind`  
 Идентификатор строки индикатора, индекс которого требуется извлечь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс индикатора в случае успешного выполнения; значение -1, если выполнена успешно.  
  
### <a name="remarks"></a>Примечания  
 Индекс первого индикатора — 0.  
  
##  <a name="create"></a>  CStatusBar::Create  
 Создает (дочернего окна) в строке состояния и связывает его с `CStatusBar` объекта.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) окно которого Windows является родительским для строки состояния объекта.  
  
 `dwStyle`  
 Стиль строки состояния. Помимо стандартных Windows [стили](../../mfc/reference/styles-used-by-mfc.md#window-styles), поддерживаются следующие стили.  
  
- `CBRS_TOP` Строка управления находится в верхней части окна фрейма.  
  
- `CBRS_BOTTOM` Панель элементов управления — в нижней части окна области.  
  
- `CBRS_NOALIGN` Панель элементов управления не меняет свое положение при изменении размеров родительского.  
  
 `nID`  
 Идентификатор дочернего окна панели инструментов  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Также задает начальные шрифт и устанавливает состояние высоту строки в значения по умолчанию.  
  
##  <a name="createex"></a>  CStatusBar::CreateEx  
 Эта функция вызывается для создания (дочернего окна) в строке состояния и связать его с `CStatusBar` объекта.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на [CWnd](../../mfc/reference/cwnd-class.md) окно которого Windows является родительским для строки состояния объекта.  
  
 `dwCtrlStyle`  
 Дополнительные стили для создания внедренного [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) объекта. Значение по умолчанию задает строку состояния без захват для изменения размера или подсказки поддержки. Стили полосы состояния поддерживается являются:  
  
- **SBARS_SIZEGRIP** включает в себя строки состояния захват для изменения размера в правом конце строки состояния. Захват для изменения размера аналогична границы для изменения размера; это прямоугольная область, которая пользователя можно щелкнуть и перетащить для изменения размера родительского окна.  
  
- **SBT_TOOLTIPS** в строке состояния поддерживает подсказки.  
  
 Дополнительные сведения об этих стилей см. в разделе [параметры для CStatusBarCtrl](../../mfc/settings-for-the-cstatusbarctrl.md).  
  
 `dwStyle`  
 Стиль панели состояния. Значение по умолчанию задает в строке состояния отображается в нижней части окна фрейма. Примените любое сочетание строки стилей элемента управления в состояния [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Тем не менее этот параметр всегда должна включать стили WS_CHILD и WS_VISIBLE.  
  
 `nID`  
 Идентификатор дочернего окна в строке состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция также задает начальные шрифт и устанавливает состояние высоту строки в значения по умолчанию.  
  
 Используйте `CreateEx`, а не [создать](#create), когда определенные стили должны присутствовать во время создания внедренные строки состояния. Например, задать `dwCtrlStyle` для **SBT_TOOLTIPS** отображать подсказки в объекте строки состояния.  
  
##  <a name="cstatusbar"></a>  CStatusBar::CStatusBar  
 Создает `CStatusBar` , создает шрифта строки состояния по умолчанию, при необходимости и задается характеристики шрифта в значения по умолчанию.  
  
```  
CStatusBar();
```  
  
##  <a name="drawitem"></a>  CStatusBar::DrawItem  
 Эта функция-член вызывается платформой при изменении внешнего вида строка пользовательского состояния.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 **ItemAction** членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено. Переопределить эту функцию-член для реализации отрисовки рисуемый владельцем `CStatusBar` объекта. Приложения следует восстановить всех графических устройств (интерфейс) выбранных объектов контекст отображения указано в `lpDrawItemStruct` перед прекращением работы этой функции-члена.  
  
##  <a name="getitemid"></a>  CStatusBar::GetItemID  
 Возвращает идентификатор индикатора, определяемое `nIndex`.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс, идентификатор которой требуется получить индикатора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор определяемого индикатора `nIndex`.  
  
##  <a name="getitemrect"></a>  CStatusBar::GetItemRect  
 Копирует координат индикатора, определяемое `nIndex` в структуру, на который указывает `lpRect`.  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс индикатора должны быть получены которого координат прямоугольника.  
  
 `lpRect`  
 Указывает на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры или [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта, который будет получить координаты индикатора, определяемое `nIndex`.  
  
### <a name="remarks"></a>Примечания  
 Координаты задаются в пикселях относительно верхнего левого угла строки состояния.  
  
##  <a name="getpaneinfo"></a>  CStatusBar::GetPaneInfo  
 Наборы `nID`, `nStyle`, и `cxWidth` идентификатор, стиль и ширину области индикатора в расположении, заданном по `nIndex`.  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс панели, сведения о которой требуется получить.  
  
 `nID`  
 Ссылка на **UINT** присваивается идентификатор области.  
  
 `nStyle`  
 Ссылка на **UINT** , задан стиль панели.  
  
 `cxWidth`  
 Ссылка на целое число, равное ширину области.  
  
##  <a name="getpanestyle"></a>  CStatusBar::GetPaneStyle  
 Вызовите эту функцию-член для извлечения стиль панели строки состояния.  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс панели стиль которого требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стиль панели строки состояния, заданные `nIndex`.  
  
### <a name="remarks"></a>Примечания  
 Стиль панели определяет, как отображается область.  
  
 Список стилей, доступных для строки состояния см. в разделе [создать](#create).  
  
##  <a name="getpanetext"></a>  CStatusBar::GetPaneText  
 Вызовите эту функцию-член для извлечения текста, который отображается в области строки состояния.  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс панели, текст которой требуется получить.  
  
 `rString`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта, содержащего текст, который требуется получить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` объект, содержащий текст панели.  
  
### <a name="remarks"></a>Примечания  
 Вторая форма этого элемента функция заливки `CString` вместе с текстом строки.  
  
##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl  
 Эта функция-член обеспечивает прямой доступ к базовой стандартного элемента управления.  
  
```  
CStatusBarCtrl& GetStatusBarCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Содержит ссылку на [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Используйте `GetStatusBarCtrl` воспользоваться преимуществами функциональные возможности стандартного элемента управления строки состояния Windows и воспользоваться преимуществами поддержки [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) предоставляет для настройки строки состояния. Например с помощью стандартного элемента управления, вы можете указать стиль, который включает захват для изменения размера в строке состояния, или вы можете указать стиль, чтобы в строке состояния отображаются в верхней части клиентской области родительского окна.  
  
 Дополнительные общие сведения о стандартных элементах управления см. в разделе [стандартные элементы управления](http://msdn.microsoft.com/library/windows/desktop/bb775493) в Windows SDK.  
  
##  <a name="setindicators"></a>  CStatusBar::SetIndicators  
 Задает идентификатор каждого индикатора для значения, указанного в соответствующий элемент массива `lpIDArray`, загружает строки ресурса, указанного в каждый идентификатор и задает текст индикатора в строку.  
  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Параметры  
 `lpIDArray`  
 Указатель на массив идентификаторов.  
  
 `nIDCount`  
 Число элементов в массиве, на который указывает `lpIDArray`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo  
 Задает новый идентификатор, стиль и ширину панели индикаторов указанного.  
  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс панели индикаторов, стиль которого требуется задать.  
  
 `nID`  
 Новый идентификатор для панели индикаторов.  
  
 `nStyle`  
 Создание стиля для панели индикаторов.  
  
 `cxWidth`  
 Новое значение ширины панели индикаторов.  
  
### <a name="remarks"></a>Примечания  
 Поддерживаются следующие стили индикатора:  
  
- **SBPS_NOBORDERS** не объемной границы вокруг области.  
  
- **SBPS_POPOUT** обратное границы, чтобы текст «раскрывающееся.»  
  
- **SBPS_DISABLED** не рисования текста.  
  
- **SBPS_STRETCH** Stretch области для заполнения неиспользуемого пространства. Только одна область, в строке состояния может иметь этот стиль.  
  
- **SBPS_NORMAL** stretch, границы и исчезающего.  
  
##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle  
 Вызовите эту функцию-член требуется задать стиль панели строки состояния.  
  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс панели стиль которого требуется задать.  
  
 `nStyle`  
 Стиль панели стиль которого требуется задать.  
  
### <a name="remarks"></a>Примечания  
 Стиль панели определяет, как отображается область.  
  
 Список стилей, доступных для строки состояния см. в разделе [SetPaneInfo](#setpaneinfo).  
  
##  <a name="setpanetext"></a>  CStatusBar::SetPaneText  
 Вызовите эту функцию-член для задания области текста к строке, на который указывает `lpszNewText`.  
  
```  
BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс панели, текст которого требуется задать.  
  
 `lpszNewText`  
 Указатель на новый текст панели.  
  
 *bСтратегии обновлениями*  
 Если **TRUE**, области становится недействительным после изменения текста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `SetPaneText`, необходимо добавить обработчик обновления пользовательского интерфейса для отображения нового текста в строке состояния.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLBARS](../../visual-cpp-samples.md)   
 [Образец DLGCBR32 MFC](../../visual-cpp-samples.md)   
 [CControlBar-класс](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl-класс](../../mfc/reference/cstatusbarctrl-class.md)   
 [Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)
