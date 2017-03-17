---
title: "Класс CMFCColorPopupMenu | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPopupMenu class
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
caps.latest.revision: 19
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 14076d78eaf86ef01e68656685dd2fd102d96311
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorpopupmenu-class"></a>Класс CMFCColorPopupMenu
Представляет раскрывающееся меню, которое позволяет пользователям выбирать цвета в документе или приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|Создает объект `CMFCColorPopupMenu`.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Создает фиксируемого перемещаемые цветовую шкалу. (Переопределяет [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Возвращает [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , внедряется в во всплывающем меню. (Переопределяет [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Задает объект элемента управления сетки свойств внедренной `CMFCColorBar` объекта.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|Имя|Описание|  
|`m_bEnabledInCustomizeMode`|Логическое значение, определяющее, следует ли отображать цветовую шкалу.|  
|`m_wndColorBar`|`CMFCColorBar` Объект, который предоставляет выбор цвета.|  
  
### <a name="remarks"></a>Примечания  
 Этот класс наследует функциональные возможности во всплывающем меню `CMFCPopupMenu` класса и управляет `CMFCColorBar` объект, который предоставляет выбор цвета. Когда платформа панель инструментов находится в режиме настройки и `m_bEnabledInCustomizeMode` член имеет значение `FALSE`, цветовую шкалу объект не отображается. Дополнительные сведения о режиме настройки в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 Дополнительные сведения о `CMFCColorBar`, в разделе [CMFCColorBar класса](../../mfc/reference/cmfccolorbar-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcolorpopupmenu.h  
  
##  <a name="cmfccolorpopupmenu"></a>CMFCColorPopupMenu::CMFCColorPopupMenu  
 Создает объект `CMFCColorPopupMenu`.  
  
```  
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    int nHorzDockRows,  
    int nVertDockColumns,  
    COLORREF colorAutomatic,  
    UINT uiCommandID,  
    BOOL bStdColorDlg = FALSE);

 
CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic);

 
CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `colors`  
 Массив цветов, отображаемых структурой в контекстном меню.  
  
 [in] `color`  
 Цвет по умолчанию.  
  
 [in] `lpszAutoColor`  
 Текстовая метка *автоматического* кнопка цвета (по умолчанию), или `NULL`.  
  
 Стандартную метку для автоматического кнопки — **автоматическое**.  
  
 [in] `lpszOtherColor`  
 Текстовая метка *других* кнопку, которая отображает выбор цветов, или `NULL`.  
  
 Стандартная метки другие кнопки **Дополнительные цвета... **.  
  
 [in] `lpszDocColors`  
 Текстовая метка «цвета» документа. Палитра цветов документа перечислены все цвета, которые в настоящее время использует документ.  
  
 [in] `lstDocColors`  
 Список цветов, которые в настоящее время используются.  
  
 [in] `nColumns`  
 Число столбцов, которые содержит массив цветов.  
  
 [in] `nHorzDockRows`  
 Число строк, которые цветовую шкалу при закреплена горизонтально.  
  
 [in] `nVertDockColumns`  
 Число столбцов, которые цветовую шкалу при закреплена вертикально.  
  
 [in] `colorAutomatic`  
 Цвет по умолчанию платформа применяется при нажатии кнопки «автоматический».  
  
 [in] `uiCommandID`  
 Идентификатор команды управления цветовой шкалы.  
  
 [in] `bStdColorDlg`  
 Логическое значение, указывающее, следует ли отображать диалоговое окно стандартный системный цвет или [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно.  
  
 [in] `pParentBtn`  
 Указатель на родительский кнопки.  
  
 [in] `nID`  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Каждая перегрузка конструктора задает `m_bEnabledInCustomizeMode` члена `FALSE`.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCColorPopupMenu` объекта.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#34;](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>CMFCColorPopupMenu::CreateTearOffBar  
 Создает фиксируемого перемещаемые цветовую шкалу.  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pWndMain`|Указатель на родительское окно панели перемещаемые.|  
|[in] `uiID`|Идентификатор команды панели перемещаемые.|  
|[in] `lpszName`|Текст окна перемещаемые строки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый объект панели управления перемещаемыми.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) объекта и приводит его к [CPane класса](../../mfc/reference/cpane-class.md) указателя. Можно привести это значение обратно [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) указателя с помощью одного из макросы приведения типов, описанных в [тип приведения MFC класс объектов](../../mfc/reference/type-casting-of-mfc-class-objects.md).  
  
##  <a name="getmenubar"></a>CMFCColorPopupMenu::GetMenuBar  
 Возвращает [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , внедряется в во всплывающем меню.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на встроенный `CMFCPopupMenuBar`.  
  
### <a name="remarks"></a>Примечания  
 Всплывающее меню цвета имеет встроенный [CMFCPopupMenuBar класс](../../mfc/reference/cmfcpopupmenubar-class.md) объекта. Переопределите этот метод в производном классе, если приложение использует другой внедренного типа.  
  
##  <a name="setproplist"></a>CMFCColorPopupMenu::SetPropList  
 Задает объект элемента управления сетки свойств внедренной `CMFCColorBar` объекта.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndList`  
 Указатель на объект элемента управления сетки свойств.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

