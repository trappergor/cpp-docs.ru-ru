---
title: Класс CAutoHideDockSite | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
dev_langs:
- C++
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5778b5be050fec50d30215a8b9cef2ca6e4b6dd4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709687"
---
# <a name="cautohidedocksite-class"></a>Класс CAutoHideDockSite
`CAutoHideDockSite` Расширяет [класс CDockSite](../../mfc/reference/cdocksite-class.md) для реализации автоматически скрываемые области закрепления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## <a name="members"></a>Участники  
  
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
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|Определяет ли объект базового области является производным от [класс CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md).|  
|[CAutoHideDockSite::DockPane](#dockpane)|Закрепляет область `CAuotHideDockSite` объекта.|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Чтобы получить размер на сайте закрепления в экранных координатах.|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|Перерисовывает области на `CAutoHideDockSite` с глобальные поля и интервал.|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|Задает поле в левой части панели стыковки.|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|Задает поле в правой части панели стыковки.|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|Вызовы [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для объектов на `CAutoHideDockSite`.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|name|Описание|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Определяет размер пространства между панелями инструментов и границей панели стыковки. Это пространство измеряется от левого края или верхнего края, в зависимости от выравнивания для области закрепления.|  
  
## <a name="remarks"></a>Примечания  
 При вызове [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), платформа автоматически создает `CAutoHideDockSite` объекта. В большинстве случаев нет необходимости создания экземпляра или использовать его напрямую.  
  
 Панели стыковки является промежуток между левой части панели закрепления и левой части [класс CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует способы извлечения `CAutoHideDockSite` объекта из `CMFCAutoHideBar` , а также установка полей левой и правой части панели стыковки.  
  
 [!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxautohidedocksite.h  
  
##  <a name="canacceptpane"></a>  CAutoHideDockSite::CanAcceptPane  
 Определяет, является ли базовый области [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объекта или производным от `CMFCAutoHideBar`.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|*pBar*|[in] Базовый объект области того, платформа.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если *pBar* является производным от `CMFCAutoHideBar`; Значение FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если объект базового области является производным от `CMFCAutoHideBar`, он может содержать `CAutoHideDockSite`.  
  
##  <a name="dockpane"></a>  CAutoHideDockSite::DockPane  
 Закрепляет область [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) объекта.  
  
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
|*pWnd*|[in] Области, в которой закрепляет платформы.|  
|*dockMethod*|[in] Закрепление параметры для области.|  
|*lpRect*|[in] Прямоугольник, который указывает границы закрепленной панели.|  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не использует параметр *dockMethod*, предоставляемого для использования в будущем.  
  
 Если *lpRect* имеет значение NULL, платформа помещает области в расположении по умолчанию на сайте закрепления. Если на сайте закрепления по горизонтали, по умолчанию располагается слева сайта закрепления. В противном случае по умолчанию располагается в верхней части сайта закрепления.  
  
##  <a name="getalignrect"></a>  CAutoHideDockSite::GetAlignRect  
 Чтобы получить размер на сайте закрепления в экранных координатах.  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|*Rect*|[in] Ссылка в прямоугольник. Метод сохраняет размер на сайте закрепления в этот прямоугольник.|  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник корректируется для смещения полей, чтобы они не включаются.  
  
##  <a name="m_nextraspace"></a>  CAutoHideDockSite::m_nExtraSpace  
 Размер пространства между границами [класс CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) и [класс CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объектов.  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>Примечания  
 Когда `CMFCAutoHideBar` закреплена на `CAutoHideDockSite`, он не должен занимать на сайте закрепления целиком. Этой глобальной переменной определяет дополнительное пространство между левой или верхней границей `CMFCAutoHideBar` и соответствующих `CAutoHideDockSite` edge. Используется ли верхнего или левого края зависит от текущего выравнивания.  
  
##  <a name="setoffsetleft"></a>  CAutoHideDockSite::SetOffsetLeft  
 Задает поле в левой части панели стыковки.  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>Параметры  
*nOffset*<br/>
[in] Новое смещение.  
  
### <a name="remarks"></a>Примечания  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объекты располагаются на статически `CAutoHideDockSite` объекта. Это означает, что пользователь не может вручную изменить расположение `CMFCAutoHideBar` объектов. `SetOffsetLeft` Метод управляет расстояние между левой стороны крайнего левого `CMFCAutoHideBar` и левой части `CAutoHideDockSite`.  
  
##  <a name="setoffsetright"></a>  CAutoHideDockSite::SetOffsetRight  
 Задает поле в правой части панели стыковки.  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>Параметры  
*nOffset*<br/>
[in] Новое смещение.  
  
### <a name="remarks"></a>Примечания  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объекты располагаются на статически `CAutoHideDockSite` объекта. Это означает, что пользователь не может вручную изменить расположение `CMFCAutoHideBar` объектов. `SetOffsetRight` Метод управляет расстояние между правой стороны крайнего правого `CMFCAutoHideBar` и правой части `CAutoHideDockSite`.  
  
##  <a name="repositionpanes"></a>  CAutoHideDockSite::RepositionPanes  
 Перерисовывает области на [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md).  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|*rectNewClientArea*|[in] Зарезервированное значение.|  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не использует *rectNewClientArea*. Области с помощью поля главной панели инструментов и кнопки интервал перерисовку.  
  
##  <a name="unsetautohidemode"></a>  CAutoHideDockSite::UnSetAutoHideMode  
 Вызовы [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для объектов на сайте закрепления.  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|*pAutoHideToolbar*|[in] Указатель на [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) область объектов, расположенных на `CAutoHideDockSite`.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод осуществляет поиск строки, содержащей *pAutoHideToolbar*. Он вызывает `CMFCAutoHideBar.UnSetAutoHideMode` для всех `CMFCAutoHideBar` объекты в этой строке. Если *pAutoHideToolbar* не найден или он имеет значение NULL, этот метод вызывает метод `CMFCAutoHideBar.UnSetAutoHideMode` для всех `CMFCAutoHideBar` объектов на `CAutoHideDockSite`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockSite](../../mfc/reference/cdocksite-class.md)
