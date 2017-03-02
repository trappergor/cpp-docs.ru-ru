---
title: "Класс CAutoHideDockSite | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoHideDockSite
- AllowShowOnPaneMenu
- CAutoHideDockSite::AllowShowOnPaneMenu
- CAutoHideDockSite.AllowShowOnPaneMenu
dev_langs:
- C++
helpviewer_keywords:
- AllowShowOnPaneMenu method
- CAutoHideDockSite class
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
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
ms.openlocfilehash: 58beaa382a2ef04cfaee0fbcf63b9eef36831472
ms.lasthandoff: 02/24/2017

---
# <a name="cautohidedocksite-class"></a>Класс CAutoHideDockSite
`CAutoHideDockSite` Расширяет [CDockSite класса](../../mfc/reference/cdocksite-class.md) для реализации автоматического скрытия областей закрепления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CAutoHideDockSite::CAutoHideDockSite`|Создает объект `CAutoHideDockSite`.|  
|`CAutoHideDockSite::~CAutoHideDockSite`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Указывает, является ли `CAutoHideDockSite` отображается на панели меню.|  
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|Определяет, является ли объект базового области является производным от [CMFCAutoHideBar класса](../../mfc/reference/cmfcautohidebar-class.md).|  
|[CAutoHideDockSite::DockPane](#dockpane)|Закрепляет область это `CAuotHideDockSite` объекта.|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Получает размер сайта закрепления в экранных координатах.|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|Перерисовывает области на `CAutoHideDockSite` с глобальные поля и кнопки интервалы.|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|Задает поле в левой части панели закрепления.|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|Задает поле в правой части панели закрепления.|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|Вызовы [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для объектов в `CAutoHideDockSite`.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|Имя|Описание|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Определяет размер пространства между панелями инструментов и краем закрепления панели. Это пространство отсчитывается от левой или верхней границы, в зависимости от выравнивания место закрепления.|  
  
## <a name="remarks"></a>Примечания  
 При вызове [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), платформа автоматически создает `CAutoHideDockSite` объекта. В большинстве случаев нет необходимости создания экземпляра или непосредственно использовать этот класс.  
  
 Закрепления панели является промежуток между левой области закрепления и с левой стороны [CMFCAutoHideButton класса](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует получение `CAutoHideDockSite` объекта из `CMFCAutoHideBar` объекта и как задать левое и правое поля закрепления панели.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#29;](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxautohidedocksite.h  
  
##  <a name="a-namecanacceptpanea--cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a>CAutoHideDockSite::CanAcceptPane  
 Определяет, является ли базовый области [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объекта или производным от `CMFCAutoHideBar`.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pBar`|Базовый области, в которой платформа тестов.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `pBar` является производным от `CMFCAutoHideBar`; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если объект базового области является производным от `CMFCAutoHideBar`, он может содержать `CAutoHideDockSite`.  
  
##  <a name="a-namedockpanea--cautohidedocksitedockpane"></a><a name="dockpane"></a>CAutoHideDockSite::DockPane  
 Закрепляет область это [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) объекта.  
  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pWnd`|Области, в которой закрепляет платформы.|  
|[in] `dockMethod`|Закрепление панели параметров.|  
|[in] `lpRect`|Прямоугольник, который определяет границы закрепленной панели.|  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию, не используйте параметр `dockMethod`, который предоставляется для использования в будущем.  
  
 Если `lpRect` — `NULL`, платформа помещает области в расположении по умолчанию на сайте закрепления. При горизонтальной сайта закрепления, по умолчанию находится в дальнем левом сайта закрепления. В противном случае — по умолчанию находится в верхней части сайта закрепления.  
  
##  <a name="a-namegetalignrecta--cautohidedocksitegetalignrect"></a><a name="getalignrect"></a>CAutoHideDockSite::GetAlignRect  
 Получает размер сайта закрепления в экранных координатах.  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `rect`|Ссылка в прямоугольник. Метод сохраняет размер сайта закрепления в этот прямоугольник.|  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник корректируется для смещения полей, чтобы они не включены.  
  
##  <a name="a-namemnextraspacea--cautohidedocksitemnextraspace"></a><a name="m_nextraspace"></a>CAutoHideDockSite::m_nExtraSpace  
 Размер пространства между краями [класса CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) и [CMFCAutoHideBar класс](../../mfc/reference/cmfcautohidebar-class.md) объектов.  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>Примечания  
 Когда `CMFCAutoHideBar` закреплена на `CAutoHideDockSite`, он не должен занимать сайта всей закрепления. Этой глобальной переменной управляет дополнительного пространства между левой или верхней границы `CMFCAutoHideBar` и соответствующих `CAutoHideDockSite` edge. Используется ли верхнего или левого края зависит от текущего выравнивания.  
  
##  <a name="a-namesetoffsetlefta--cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a>CAutoHideDockSite::SetOffsetLeft  
 Задает поле в левой части панели закрепления.  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nOffset`  
 Новое смещение.  
  
### <a name="remarks"></a>Примечания  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объекты располагаются на статически `CAutoHideDockSite` объекта. Это означает, что пользователь не может изменить вручную расположение `CMFCAutoHideBar` объектов. `SetOffsetLeft` Метод управляет интервалом между левой части левого `CMFCAutoHideBar` и с левой стороны `CAutoHideDockSite`.  
  
##  <a name="a-namesetoffsetrighta--cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a>CAutoHideDockSite::SetOffsetRight  
 Задает поле в правой части панели закрепления.  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nOffset`  
 Новое смещение.  
  
### <a name="remarks"></a>Примечания  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объекты располагаются на статически `CAutoHideDockSite` объекта. Это означает, что пользователь не может изменить вручную расположение `CMFCAutoHideBar` объектов. `SetOffsetRight` Метод управляет интервалом между правой части крайних правых `CMFCAutoHideBar` и правая часть `CAutoHideDockSite`.  
  
##  <a name="a-namerepositionpanesa--cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a>CAutoHideDockSite::RepositionPanes  
 Перерисовывает области на [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md).  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `rectNewClientArea`|Зарезервированное значение.|  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не использует `rectNewClientArea`. Области с полями главной панели инструментов и интервал выполнить перерисовку.  
  
##  <a name="a-nameunsetautohidemodea--cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a>CAutoHideDockSite::UnSetAutoHideMode  
 Вызовы [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для объектов на сайте закрепления.  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pAutoHideToolbar`|Указатель на [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) область объектов, расположенных на `CAutoHideDockSite`.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод осуществляет поиск строки, содержащей `pAutoHideToolbar`. Он вызывает `CMFCAutoHideBar.UnSetAutoHideMode` для всех `CMFCAutoHideBar` объектов в этой строке. Если `pAutoHideToolbar` не найден или является `NULL`, этот метод вызывает метод `CMFCAutoHideBar.UnSetAutoHideMode` для всех `CMFCAutoHideBar` объектов на `CAutoHideDockSite`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockSite](../../mfc/reference/cdocksite-class.md)

