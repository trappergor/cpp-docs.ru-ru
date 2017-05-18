---
title: "Класс CMFCAutoHideBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideToolBar class
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
caps.latest.revision: 35
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: db15fc9fa3925230e372b6e13368f455dcfbb1a9
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcautohidebar-class"></a>Класс CMFCAutoHideBar
Класс `CMFCAutoHideBar` — это специальный класс панели инструментов, реализующий функцию автоматического скрытия.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCAutoHideBar : public CPane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||  
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Переопределяет `CPane::AllowShowOnPaneMenu`.)|  
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(Переопределяет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCAutoHideBar::Create](#create)|Создает панель элементов управления и присоединяет его к [CPane](../../mfc/reference/cpane-class.md) объекта. (Переопределяет [CPane::Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||  
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|Вызывается платформой непосредственно перед отображением меню особой панели. (Переопределяет [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||  
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(Переопределяет [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).)|  
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||  
|[CMFCAutoHideBar::StretchPane](#stretchpane)|Растягивает панель по вертикали или горизонтали. (Переопределяет [CBasePane::StretchPane](../../mfc/reference/cbasepane-class.md#stretchpane).)|  
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||  
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|Временную задержку между моментом, когда пользователь наводит указатель мыши на [CMFCAutoHideButton класса](../../mfc/reference/cmfcautohidebutton-class.md) до момента, когда платформа показано соответствующее окно.|  
  
## <a name="remarks"></a>Примечания  
 Когда пользователь переключает область закрепления в режим автоматического скрытия, платформа автоматически создает объект `CMFCAutoHideBar`. Он также создает необходимые [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) и [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) объектов. Каждый объект `CAutoHideDockSite` связан с определенным объектом `CMFCAutoHideButton`.  
  
 Класс `CMFCAutoHideBar` реализует отображение объекта `CAutoHideDockSite`, когда пользователь наводит указатель мыши на объект `CMFCAutoHideButton`. Когда панель инструментов получает сообщение WM_MOUSEMOVE, объект `CMFCAutoHideBar` запускает таймер. Когда отсчет завершается, панели инструментов отправляется уведомление о событии WM_TIMER. Панель инструментов обрабатывает это событие, проверяя, расположен ли указатель мыши на той же кнопке автоматического скрытия, на которой он находился при запуске таймера. В случае положительного результата отображается прикрепленный объект `CAutoHideDockSite`.  
  
 Длительность задержки таймера можно регулировать с помощью параметра `m_nShowAHWndDelay`. Значение по умолчанию составляет 400 мс.  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется создание объекта `CMFCAutoHideBar` и использование его метода `GetDockSiteRow`.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#26;](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxautohidebar.h  
  
##  <a name="addautohidewindow"></a>CMFCAutoHideBar::AddAutoHideWindow  
 Добавляет в окно `CDockablePane` функциональные возможности, которые позволяют ему выполнять автоматическое скрытие.  
  
```  
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pAutoHideWnd`  
 Окно, которое нужно скрыть.  
  
 [in] `dwAlignment`  
 Значение, указывающее выравнивание кнопки автоматического скрытия с окном приложения.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Параметр `dwAlignment` указывает, где в приложении находится кнопка автоматического скрытия. Параметру может быть присвоено одно из следующих значений:  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="allowshowonpanemenu"></a>CMFCAutoHideBar::AllowShowOnPaneMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="calcfixedlayout"></a>CMFCAutoHideBar::CalcFixedLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="cmfcautohidebar"></a>CMFCAutoHideBar::CMFCAutoHideBar  
 Создает объект CMFCAutoHideBar.  
  
```  
CMFCAutoHideBar();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="create"></a>CMFCAutoHideBar::Create  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszClassName`  
 [in] `dwStyle`  
 [in] `rect`  
 [in] `pParentWnd`  
 [in] `nID`  
 [in] `dwControlBarStyle`  
 [in] `pContext`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getfirstahwindow"></a>CMFCAutoHideBar::GetFirstAHWindow  
 Возвращает указатель на первое окно автоматического скрытия в приложении.  
  
```  
CDockablePane* GetFirstAHWindow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первое окно автоматического скрытия в приложении или значение NULL, если его не существует.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getvisiblecount"></a>CMFCAutoHideBar::GetVisibleCount  
 Получает количество видимых кнопок автоматического скрытия.  
  
```  
int GetVisibleCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество видимых кнопок автоматического скрытия.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_nshowahwnddelay"></a>CMFCAutoHideBar::m_nShowAHWndDelay  
 Временную задержку между моментом, когда пользователь наводит указатель мыши на [CMFCAutoHideButton класса](../../mfc/reference/cmfcautohidebutton-class.md) до момента, когда платформа показано соответствующее окно.  
  
```  
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;  
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь наводит указатель мыши на `CMFCAutoHideButton`, существует небольшая задержка перед платформа отображает соответствующее окно. Этот параметр определяет интервал, время задержки в миллисекундах.  
  
##  <a name="onshowcontrolbarmenu"></a>CMFCAutoHideBar::OnShowControlBarMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CPoint`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removeautohidewindow"></a>CMFCAutoHideBar::RemoveAutoHideWindow  
 Удаляет и уничтожает окно автоматического скрытия.  
  
```  
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```  
  
### <a name="parameters"></a>Параметры  
 CDockablePane *`pAutoHideWnd`  
 Удаляемое окно автоматического скрытия.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно; в противном случае — FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setactiveingroup"></a>CMFCAutoHideBar::SetActiveInGroup  
 Помечает строку автоматического скрытия как активную.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);  
```  
  
### <a name="parameters"></a>Параметры  
 [in] BOOL`bActive`  
 Значение TRUE, чтобы задать как активную; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 В разделе [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).  
  
##  <a name="setrecentvisiblestate"></a>CMFCAutoHideBar::SetRecentVisibleState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetRecentVisibleState(BOOL bState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bState`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="showautohidewindow"></a>CMFCAutoHideBar::ShowAutoHideWindow  
 Показывает окно автоматического скрытия.  
  
```  
BOOL ShowAutoHideWindow(
        CDockablePane* pAutoHideWnd,  
        BOOL bShow,  
        BOOL bDelay);  
```  
  
### <a name="parameters"></a>Параметры  
 [in] CDockablePane *`pAutoHideWnd`  
 [in] BOOL`bShow`  
 Значение TRUE для отображения окна.  
  
 [in] BOOL`bDelay`  
 Этот параметр не учитывается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно; в противном случае — FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="stretchpane"></a>CMFCAutoHideBar::StretchPane  
 Изменение размеров строки автоматического скрытия в свернутом состоянии в соответствии с размерами объекта `CMFCAutoHideButton` .  
  
```  
virtual CSize StretchPane(
    int nLength,   
    BOOL bVert);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nLength`  
 Значение не используется в базовой реализации. В производных реализациях это значение используется для указания длины панели, размер которой был изменен.  
  
 [in] `bVert`  
 Значение не используется в базовой реализации. В производных реализациях, используйте `TRUE` для обработки случаев, где автоматического скрытия панель свернута по вертикали, и `FALSE` для случая, где автоматического скрытия панель свернута по горизонтали.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер, полученный в результате изменения размера панели.  
  
### <a name="remarks"></a>Примечания  
 Производные классы могут переопределять этот метод для настройки поведения.  
  
##  <a name="unsetautohidemode"></a>CMFCAutoHideBar::UnSetAutoHideMode  
 Отключает режим автоматического скрытия для группы строк автоматического скрытия.  
  
```  
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)  
```  
  
### <a name="parameters"></a>Параметры  
 [in] pFirstBarInGroup  
 Указатель на первую строку автоматического скрытия в группе.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="updatevisiblestate"></a>CMFCAutoHideBar::UpdateVisibleState  
 Вызывается платформой при необходимости перерисовать строку автоматического скрытия.  
  
```  
void UpdateVisibleState();
```  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CPane](../../mfc/reference/cpane-class.md)   
 [Класс CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)   
 [Класс CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)

