---
title: Класс CMFCRibbonMiniToolBar | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d8aebd796e0edb587e18db910df808fa349ca37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371677"
---
# <a name="cmfcribbonminitoolbar-class"></a>Класс CMFCRibbonMiniToolBar
Реализует контекстно-зависимую панель инструментов контекстного меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Конструктор по умолчанию.|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
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
  
##  <a name="setcommands"></a>  CMFCRibbonMiniToolBar::SetCommands  
 Задает список команд, отображаемых на панели инструментов.  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRibbonBar`  
 Панель ленты, мини-панель инструментов ищет кнопки для отображения.  
  
 [in] `lstCommands`  
 Список команд, который будет отображаться на мини-панель инструментов. Все категории ленты производится поиск соответствующие кнопки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется, чтобы задать список команд, отображаемых в мини-панель инструментов.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `SetCommands` метод `CMFCRibbonMiniToolBar` класса. Этот фрагмент кода является частью [MS Office 2007 демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>  CMFCRibbonMiniToolBar::Show  
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
 `TRUE` Если мини-панель инструментов отображается успешно. в противном случае `FALSE`.  
  
##  <a name="showwithcontextmenu"></a>  CMFCRibbonMiniToolBar::ShowWithContextMenu  
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
 Указывает идентификатор ресурса контекстного меню для отображения.  
  
 [in] `pWndOwner`  
 Идентифицирует окно, которое получает сообщения из контекстного меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если в контекстном меню отображается успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для отображения мини-панель инструментов, которая содержит контекстное меню. В контекстном меню — позиционированные 15 пикселей ниже мини-панель инструментов.  
  
##  <a name="iscontextmenumode"></a>  CMFCRibbonMiniToolBar::IsContextMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isribbonminitoolbar"></a>  CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
