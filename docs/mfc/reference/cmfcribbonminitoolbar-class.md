---
title: Класс CMFCRibbonMiniToolBar | Документация Майкрософт
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
ms.openlocfilehash: ef348275059fd2623ca83b40730f010a7d18d6d5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721179"
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
  
##  <a name="setcommands"></a>  CMFCRibbonMiniToolBar::SetCommands  
 Задает список команд, отображаемых на панели инструментов.  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>Параметры  
*pRibbonBar*<br/>
[in] Панель ленты, мини-панель инструментов поиска для кнопки для отображения.  
  
*lstCommands*<br/>
[in] Список команд, отображаемых в мини-панель инструментов. Все категории ленты выполняется поиск соответствующие кнопки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется, чтобы задать список команд, отображаемых в мини-панель инструментов.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует, как использовать `SetCommands` метод `CMFCRibbonMiniToolBar` класса. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>  CMFCRibbonMiniToolBar::Show  
 Отображает мини-панель инструментов по указанным координатам экрана.  
  
```  
BOOL Show(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>Параметры  
*x*<br/>
[in] Задает горизонтальное положение мини-панель инструментов в экранных координатах.  
  
*y*<br/>
[in] Задает вертикальное положение мини-панель инструментов в экранных координатах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если мини-панель инструментов отображается успешно; в противном случае — значение FALSE.  
  
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
*x*<br/>
[in] Задает горизонтальное положение контекстного меню в экранных координатах.  
  
*y*<br/>
[in] Задает вертикальное положение контекстного меню в экранных координатах.  
  
*uiMenuResID*<br/>
[in] Указывает идентификатор ресурса для контекстного меню для отображения.  
  
*pWndOwner*<br/>
[in] Определяет окно, которое получает сообщения из контекстного меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно; был отображен в контекстном меню в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для отображения мини-панель инструментов, которая содержит контекстное меню. В контекстном меню — позиционированные 15 пикселей ниже мини-панель инструментов.  
  
##  <a name="iscontextmenumode"></a>  CMFCRibbonMiniToolBar::IsContextMenuMode  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isribbonminitoolbar"></a>  CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
