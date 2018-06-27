---
title: Класс CAutoHideDockSite | Документы Microsoft
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
ms.openlocfilehash: 0792601ae773cf9abc8bb44218eb7395ff68da77
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952788"
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
|Имя|Описание:|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Указывает, является ли `CAutoHideDockSite` отображается на панели меню.|  
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|Определяет, является ли объект базового области является производным от [класс CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md).|  
|[CAutoHideDockSite::DockPane](#dockpane)|Закрепляет область это `CAuotHideDockSite` объекта.|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Получает размер сайте закрепления в экранных координатах.|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|Перерисовывает области на `CAutoHideDockSite` с глобальные поля и интервал кнопки.|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|Задает поле в левой части панели закрепления.|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|Задает поле в правой части панели закрепления.|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|Вызовы [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для объектов в `CAutoHideDockSite`.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|name|Описание:|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Определяет размер пространства между панелями инструментов и краем закрепляемую панель. Это пространство отсчитывается от левого края или верхнего края, в зависимости от выравнивания для места закрепления.|  
  
## <a name="remarks"></a>Примечания  
 При вызове [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), платформа автоматически создает `CAutoHideDockSite` объекта. В большинстве случаев нет необходимости создания экземпляра или использовать его напрямую.  
  
 Закрепляемую панель является промежуток между левой части области закрепления и левой части [класс CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует способ получения `CAutoHideDockSite` объекта из `CMFCAutoHideBar` объекта и как задать левое и правое поля закрепления панели.  
  
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
|Параметр|Описание:|  
|[in] *pBar*|Базовый области, в которой проверяет платформу.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если *pBar* является производным от `CMFCAutoHideBar`; `FALSE` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если объект базового области является производным от `CMFCAutoHideBar`, он может содержать `CAutoHideDockSite`.  
  
##  <a name="dockpane"></a>  CAutoHideDockSite::DockPane  
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
|Параметр|Описание:|  
|[in] *pWnd*|Области, в которой закрепляет платформу.|  
|[in] *dockMethod*|Закрепление панели параметров.|  
|[in] *lpRect*|Прямоугольник, который определяет границы закрепленной панели.|  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию, не используйте параметр *dockMethod*, предоставляемое для использования в будущем.  
  
 Если *lpRect* — `NULL`, платформа помещает области в расположении по умолчанию на сайте закрепления. Если сайта закрепления располагаются горизонтально, по умолчанию находится в крайнем левом сайта закрепления. В противном случае по умолчанию находится в верхней части сайта закрепления.  
  
##  <a name="getalignrect"></a>  CAutoHideDockSite::GetAlignRect  
 Получает размер сайте закрепления в экранных координатах.  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] *rect*|Ссылка в прямоугольник. Метод сохраняет размер сайте закрепления в этот прямоугольник.|  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник будет настроена для смещения полей, чтобы они не включаются.  
  
##  <a name="m_nextraspace"></a>  CAutoHideDockSite::m_nExtraSpace  
 Размер пространства между содержимым [класс CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) и [класс CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объектов.  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>Примечания  
 Когда `CMFCAutoHideBar` закреплена на `CAutoHideDockSite`, он не должен занимать закрепления всего сайта. Этой глобальной переменной управляет дополнительного пространства между границей левого или верхнего `CMFCAutoHideBar` и соответствующий `CAutoHideDockSite` edge. Используется ли верхнего или левого края зависит текущее выравнивание.  
  
##  <a name="setoffsetleft"></a>  CAutoHideDockSite::SetOffsetLeft  
 Задает поле в левой части панели закрепления.  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nOffset*  
 Новое смещение.  
  
### <a name="remarks"></a>Примечания  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объекты, расположенные на статически `CAutoHideDockSite` объекта. Это означает, что пользователь не может изменить вручную расположение `CMFCAutoHideBar` объектов. `SetOffsetLeft` Метод управляет расстояние между левой части слева `CMFCAutoHideBar` и левой части `CAutoHideDockSite`.  
  
##  <a name="setoffsetright"></a>  CAutoHideDockSite::SetOffsetRight  
 Задает поле в правой части панели закрепления.  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nOffset*  
 Новое смещение.  
  
### <a name="remarks"></a>Примечания  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) объекты, расположенные на статически `CAutoHideDockSite` объекта. Это означает, что пользователь не может изменить вручную расположение `CMFCAutoHideBar` объектов. `SetOffsetRight` Метод управляет интервалом между правой части самый правый `CMFCAutoHideBar` и в правой части `CAutoHideDockSite`.  
  
##  <a name="repositionpanes"></a>  CAutoHideDockSite::RepositionPanes  
 Перерисовывает панелей на [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md).  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] *rectNewClientArea*|Зарезервированное значение.|  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию не использует *rectNewClientArea*. Он перерисовывает областей с полями главной панели инструментов и интервал кнопки.  
  
##  <a name="unsetautohidemode"></a>  CAutoHideDockSite::UnSetAutoHideMode  
 Вызовы [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для объектов на сайте закрепления.  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] *pAutoHideToolbar*|Указатель на [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) область объектов, расположенных на `CAutoHideDockSite`.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод осуществляет поиск строки, содержащей *pAutoHideToolbar*. Он вызывает `CMFCAutoHideBar.UnSetAutoHideMode` для всех `CMFCAutoHideBar` объектов в данной строке. Если *pAutoHideToolbar* не найден или является `NULL`, этот метод вызывает метод `CMFCAutoHideBar.UnSetAutoHideMode` для всех `CMFCAutoHideBar` объектов на `CAutoHideDockSite`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockSite](../../mfc/reference/cdocksite-class.md)
