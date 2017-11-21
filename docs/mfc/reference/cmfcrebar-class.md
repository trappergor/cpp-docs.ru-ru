---
title: "Класс CMFCReBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
dev_langs: C++
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e5c836c30d67f1d8c5b77e6fbdba4d312fbf6c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcrebar-class"></a>Класс CMFCReBar
Объект `CMFCReBar` объект является панель элементов управления, которая предоставляет макет, сохраняемость и сведения о состоянии для элементов управления главной панели.  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
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
|[CMFCReBar::Create](#create)|Создает контейнер элементов управления и прикрепляет его к `CMFCReBar` объекта.|  
|[CMFCReBar::EnableDocking](#enabledocking)|(Переопределяет [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|  
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||  
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Предоставляет прямой доступ к базовому объекту [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) стандартного элемента управления.|  
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Переопределяет [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Переопределяет [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|  
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Переопределяет [CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/e139f06a-9793-4ee2-bc3d-517389368c77).)|  
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Переопределяет [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|  
  
## <a name="remarks"></a>Примечания  
 Объект `CMFCReBar` объект может содержать множество дочерних окон. Это включает в себя поля ввода, панели инструментов и списки. Вы можете изменить размер главной панели программными средствами или пользователь может вручную изменить размер главной панели, перетащив границу окна. Можно также задать фон объекта главной панели растрового изображения по своему усмотрению.  
  
 На главной панели объект ведет себя аналогично объект панели инструментов. Элемент управления главной панели может содержать один или несколько полосы и каждого диапазона может содержать полосу захвата, битовая карта, текстовую метку и дочернего окна.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCReBar` класса. В примере показано создание элемента управления "Главная панель" и добавление полосе. Функции аппаратного контроллера управления в качестве внутреннего панели инструментов. Этот фрагмент кода является частью [пример главной панели теста](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRebar.h  
  
##  <a name="addbar"></a>CMFCReBar::AddBar  
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
 Содержит стиль, применяемый к полосе. Полный список стилей аппаратного контроллера управления, см. в описании `fStyle` в [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) структуры в документации пакета SDK для Windows.  
  
 [in] `clrFore`  
 Представляет цвет переднего плана для главной панели.  
  
 [in] `clrBack`  
 Представляет цвет фона главной панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если диапазон успешно добавлен в главной панели; в противном случае `FALSE`.  
  
##  <a name="create"></a>CMFCReBar::Create  
 Создает контейнер элементов управления и прикрепляет его к [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) объекта.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pParentWnd`  
 Указатель на родительское окно элемента управления главной панели.  
  
 [in] `dwCtrlStyle`  
 Задает стиль для элемента управления главной панели. Значение по умолчанию стиль — **RBS_BANDBORDERS**, который отображает ограничить строки для разделения смежные полосы в элемент управления главной панели. Список допустимых стили см. в разделе [стили элемента управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774377) документации по пакету Windows SDK.  
  
 [in] `dwStyle`  
 Стиль окна элемента управления главной панели. Список допустимых стили см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `nID`  
 Идентификатор дочернего окна главной панели  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если главной панели был создан успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getrebarctrl"></a>CMFCReBar::GetReBarCtrl  
 Предоставляет прямой доступ к `CReBarCtrl` базового стандартного элемента управления для `CMFCReBar` объектов.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на базовый `CReBarCtrl` объекта.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы воспользоваться преимуществами общие функции управления Windows главной панели, при настройке вашей главной панели.  
  
##  <a name="calcfixedlayout"></a>CMFCReBar::CalcFixedLayout  

  
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
  
##  <a name="canfloat"></a>CMFCReBar::CanFloat  

  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enabledocking"></a>CMFCReBar::EnableDocking  

  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwDockStyle`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getrebarbandinfosize"></a>CMFCReBar::GetReBarBandInfoSize  

  
```  
UINT GetReBarBandInfoSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onshowcontrolbarmenu"></a>CMFCReBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CPoint`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ontoolhittest"></a>CMFCReBar::OnToolHitTest  

  
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
  
##  <a name="onupdatecmdui"></a>CMFCReBar::OnUpdateCmdUI  

  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTarget`  
 [in] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpanealignment"></a>CMFCReBar::SetPaneAlignment  

  
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
