---
title: "Класс CMFCRibbonMiniToolBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMiniToolBar class
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
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
ms.openlocfilehash: 7c69880578c0aba88a8463112f4d1e05f6032497
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonminitoolbar-class"></a>Класс CMFCRibbonMiniToolBar
Реализует контекстно-зависимую панель инструментов контекстного меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Конструктор по умолчанию.|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Переопределяет `CMFCPopupMenu::IsRibbonMiniToolBar`.)|  
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|Задает список команд, отображаемых на панели инструментов.|  
|[CMFCRibbonMiniToolBar::Show](#show)|Отображает мини-панель инструментов по указанным координатам экрана.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Отображает мини-панель инструментов вместе с контекстным меню.|  
  
## <a name="remarks"></a>Примечания  
 Мини-панель инструментов обычно отображается, когда пользователь выделяет объект в документе. Например, после выделения блока текста в текстовом редакторе отображается мини-панель инструментов с командами форматирования текста.  
  
 Когда указатель мыши выходит за пределы мини-панели инструментов, она становится прозрачной.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonMiniToolBar.h  
  
##  <a name="setcommands"></a>CMFCRibbonMiniToolBar::SetCommands  
 Задает список команд, отображаемых на панели инструментов.  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRibbonBar`  
 Область ленты, мини-панель инструментов ищет кнопки для отображения.  
  
 [in] `lstCommands`  
 Список команд, отображаемый на мини-панель инструментов. Все категории ленты производится поиск соответствующие кнопки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для задания списка команд, отображаемых в мини-панель инструментов.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetCommands` метод `CMFCRibbonMiniToolBar` класса. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo №&9;](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>CMFCRibbonMiniToolBar::Show  
 Отображает мини-панель инструментов по указанным координатам экрана.  
  
```  
BOOL Show(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `x`  
 Задает горизонтальное положение мини-панель инструментов в экранных координатах.  
  
 [in] `y`  
 Задает вертикальное положение мини-панель инструментов в экранных координатах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если мини-панель инструментов отображается успешно; в противном случае — `FALSE`.  
  
##  <a name="showwithcontextmenu"></a>CMFCRibbonMiniToolBar::ShowWithContextMenu  
 Отображает мини-панель инструментов вместе с контекстным меню.  
  
```  
BOOL ShowWithContextMenu(
    int x,  
    int y,  
    UINT uiMenuResID,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `x`  
 Задает горизонтальное положение контекстного меню в экранных координатах.  
  
 [in] `y`  
 Задает вертикальное положение контекстного меню в экранных координатах.  
  
 [in] `uiMenuResID`  
 Указывает идентификатор ресурса для отображения контекстного меню.  
  
 [in] `pWndOwner`  
 Определяет окно, которое получает сообщения из контекстного меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если контекстное меню отображается успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для отображения мини-панель инструментов, которая содержит контекстное меню. В контекстном меню является позиционированной 15 пикселей ниже мини-панель инструментов.  
  
##  <a name="iscontextmenumode"></a>CMFCRibbonMiniToolBar::IsContextMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isribbonminitoolbar"></a>CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

