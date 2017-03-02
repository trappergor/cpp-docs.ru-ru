---
title: "Класс CMFCReBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCReBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCReBar class
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
caps.latest.revision: 27
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
ms.openlocfilehash: 5ec432cb8cf70d31c04c718fd7e802ee9c099763
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcrebar-class"></a>Класс CMFCReBar
Объект `CMFCReBar` объект является панель элементов управления, которая предоставляет макет, сохраняемость и сведения о состоянии для элементов управления главной панели.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCReBar : public CPane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCReBar::AddBar](#addbar)|Добавляет диапазон главной панели.|  
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Переопределяет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCReBar::CanFloat](#canfloat)|(Переопределяет [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CMFCReBar::Create](#create)|Создает элемент управления главной панели и присоединяет его к `CMFCReBar` объекта.|  
|[CMFCReBar::EnableDocking](#enabledocking)|(Переопределяет [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|  
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||  
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Предоставляет прямой доступ к базовому объекту [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) стандартного элемента управления.|  
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Переопределяет [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Переопределяет [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|  
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Переопределяет [CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/e139f06a-9793-4ee2-bc3d-517389368c77).)|  
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Переопределяет [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|  
  
## <a name="remarks"></a>Примечания  
 Объект `CMFCReBar` объект может содержать множество дочерних окон. Это включает поля ввода, панели инструментов и списки. Главной панели можно изменить программным способом, или пользователь может вручную изменить размер главной панели, перетащив границу окна. Можно также задать цвет фона объекта главной панели в растровое изображение по своему усмотрению.  
  
 На главной панели объект ведет себя аналогично объект панели инструментов. Контейнер элементов управления может содержать один или несколько полосы, и каждый диапазон может содержать полосу захвата, точечный рисунок, текстовую метку и дочернего окна.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCReBar` класса. В примере показано создание элемента управления "Главная панель" и добавление диапазона. Функции аппаратного контроллера управления в качестве внутренних инструментов. Этот фрагмент кода является частью [пример главной панели теста](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RebarTest&#1;](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest&#2;](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRebar.h  
  
##  <a name="a-nameaddbara--cmfcrebaraddbar"></a><a name="addbar"></a>CMFCReBar::AddBar  
 Добавляет диапазон главной панели.  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pBar`  
 Указатель дочернего окна, который должен быть вставлен в главной панели. Указанный объект должен иметь **WS_CHILD** стиль окна.  
  
 [in] `pszText`  
 Задает текст, отображаемый на главной панели. Текст не является частью дочернего окна. Вместо этого он отображается на главной панели, сам.  
  
 [in] [out]`pbmp`  
 Указывает битовую карту для отображения на заднем плане главной панели.  
  
 [in] `dwStyle`  
 Содержит стиль для применения к полосе. Полный список стилей внешнего см. в описании для `fStyle` в [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структуры документации по пакету Windows SDK.  
  
 [in] `clrFore`  
 Представляет цвет переднего плана главной панели.  
  
 [in] `clrBack`  
 Представляет цвет фона главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если диапазон успешно добавлено к главной панели; в противном случае — `FALSE`.  
  
##  <a name="a-namecreatea--cmfcrebarcreate"></a><a name="create"></a>CMFCReBar::Create  
 Создает элемент управления главной панели и присоединяет его к [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) объекта.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pParentWnd`  
 Указатель на родительское окно этого элемента управления главной панели.  
  
 [in] `dwCtrlStyle`  
 Задает стиль для элемента управления главной панели. Значение по умолчанию стиль — **RBS_BANDBORDERS**, который отображает ограничить строки для разделения соседних делений на главной панели управления. Список допустимых стили см [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) документации по пакету Windows SDK.  
  
 [in] `dwStyle`  
 Стиль окна элемента управления главной панели. Список допустимых стили см [стили окна](../../mfc/reference/window-styles.md).  
  
 [in] `nID`  
 Идентификатор главной панели дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если контейнер был создан успешно. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetrebarctrla--cmfcrebargetrebarctrl"></a><a name="getrebarctrl"></a>CMFCReBar::GetReBarCtrl  
 Предоставляет прямой доступ к `CReBarCtrl` базового стандартного элемента управления для `CMFCReBar` объектов.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на базовый `CReBarCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы воспользоваться преимуществами главной панели Windows, общие функции управления при настройке вашей главной панели.  
  
##  <a name="a-namecalcfixedlayouta--cmfcrebarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCReBar::CalcFixedLayout  
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
  
##  <a name="a-namecanfloata--cmfcrebarcanfloat"></a><a name="canfloat"></a>CMFCReBar::CanFloat  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenabledockinga--cmfcrebarenabledocking"></a><a name="enabledocking"></a>CMFCReBar::EnableDocking  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwDockStyle`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetrebarbandinfosizea--cmfcrebargetrebarbandinfosize"></a><a name="getrebarbandinfosize"></a>CMFCReBar::GetReBarBandInfoSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT GetReBarBandInfoSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonshowcontrolbarmenua--cmfcrebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a>CMFCReBar::OnShowControlBarMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CPoint`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameontoolhittesta--cmfcrebarontoolhittest"></a><a name="ontoolhittest"></a>CMFCReBar::OnToolHitTest  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 [in] `pTI`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonupdatecmduia--cmfcrebaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCReBar::OnUpdateCmdUI  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTarget`  
 [in] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetpanealignmenta--cmfcrebarsetpanealignment"></a><a name="setpanealignment"></a>CMFCReBar::SetPaneAlignment  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CReBarCtrl-класс](../../mfc/reference/crebarctrl-class.md)   
 [Класс CPane](../../mfc/reference/cpane-class.md)

