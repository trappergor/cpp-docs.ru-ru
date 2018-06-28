---
title: Класс CMFCColorPopupMenu | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54999252af2ec55c67e1afc69c2788f96cfc640e
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037308"
---
# <a name="cmfccolorpopupmenu-class"></a>Класс CMFCColorPopupMenu
Представляет контекстное меню, которая используется, чтобы выбрать цвета в документ или приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|Создает объект `CMFCColorPopupMenu`.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Создает закрепляемую перемещаемые цветовую шкалу. (Переопределяет [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Возвращает [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , внедренные во всплывающем меню. (Переопределяет [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Задает объект элемента управления сетки свойств внедренной `CMFCColorBar` объекта.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|name|Описание:|  
|`m_bEnabledInCustomizeMode`|Логическое значение, определяющее, следует ли отображать цветовую шкалу.|  
|`m_wndColorBar`|`CMFCColorBar` Объект, который предоставляет выбор цвета.|  
  
### <a name="remarks"></a>Примечания  
 Этот класс наследует функциональные возможности всплывающего меню `CMFCPopupMenu` класса и управляет `CMFCColorBar` объект, который предоставляет выбор цвета. Если платформа панель инструментов находится в режим настройки и `m_bEnabledInCustomizeMode` член имеет значение `FALSE`, объект цветовой шкалы не отображаются. Дополнительные сведения о режиме настройки см. в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
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
  
##  <a name="cmfccolorpopupmenu"></a>  CMFCColorPopupMenu::CMFCColorPopupMenu  
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
 [in] *цвета*  
 Массив цветов, отображаемых структурой в контекстном меню.  
  
 [in] *цвет*  
 Значение по умолчанию выбранный цвет.  
  
 [in] *lpszAutoColor*  
 Текстовая метка *автоматического* кнопку цвета (по умолчанию), или `NULL`.  
  
 Стандартная метки для кнопки автоматического **автоматического**.  
  
 [in] *lpszOtherColor*  
 Текстовая метка *других* кнопку, которая отображает дополнительные параметры цветов, или `NULL`.  
  
 Метки стандартной кнопки выбора другого **Дополнительные цвета...** .  
  
 [in] *lpszDocColors*  
 Текстовая подпись кнопки цветов документа. Палитра цветов документа перечислены все цвета, которые в настоящее время используются.  
  
 [in] *lstDocColors*  
 Список цветов, которые в настоящее время используются.  
  
 [in] *nColumns*  
 Число столбцов, которые содержит массив цветов.  
  
 [in] *nHorzDockRows*  
 Число строк, которые имеет цветовую шкалу, если она закреплена горизонтально.  
  
 [in] *nVertDockColumns*  
 Число столбцов, которые цветовую шкалу при его закреплены по вертикали.  
  
 [in] *colorAutomatic*  
 Цвет по умолчанию платформа применяется при нажатии кнопки «автоматический».  
  
 [in] *uiCommandID*  
 ИД команды управления цветовой шкалы.  
  
 [in] *bStdColorDlg*  
 Логическое значение, указывающее, следует ли отображать диалоговое окно стандартный системный цвет или [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно.  
  
 [in] *pParentBtn*  
 Указатель на кнопку родительского.  
  
 [in] *nID*  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Каждая перегрузка конструктора задает `m_bEnabledInCustomizeMode` члена `FALSE`.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCColorPopupMenu` объекта.  
  
 [!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar  
 Создает закрепляемую перемещаемые цветовую шкалу.  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] *pWndMain*|Указатель на родительское окно перемещаемой панелью.|  
|[in] *uiID*|Идентификатор команды перемещаемой панелью.|  
|[in] *lpszName*|Текст окна перемещаемой панелью.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новый объект строки перемещаемые управления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) объекта и приводит его к [класса CPane](../../mfc/reference/cpane-class.md) указателя. Можно привести это значение к [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) указателя с помощью одного из макросы приведения, описанной в [тип-приведения для объектов классов MFC](../../mfc/reference/type-casting-of-mfc-class-objects.md).  
  
##  <a name="getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar  
 Возвращает [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , внедренные во всплывающем меню.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на встроенный `CMFCPopupMenuBar`.  
  
### <a name="remarks"></a>Примечания  
 Всплывающее меню цвета имеет встроенный [класс CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) объекта. Переопределите этот метод в производном классе, если приложение использует другой внедренного типа.  
  
##  <a name="setproplist"></a>  CMFCColorPopupMenu::SetPropList  
 Задает объект элемента управления сетки свойств внедренной `CMFCColorBar` объекта.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pWndList*  
 Указатель на объект элемента управления сетки свойств.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
