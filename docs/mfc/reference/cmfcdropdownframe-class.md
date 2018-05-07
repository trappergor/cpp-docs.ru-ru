---
title: Класс CMFCDropDownFrame | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1680305b359bb273ba492083dd2e99703e2d930d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcdropdownframe-class"></a>Класс CMFCDropDownFrame
Предоставляет функциональные возможности окна фрейма раскрывающийся список для раскрывающийся список панелей инструментов и кнопки панели инструментов раскрывающегося списка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|Конструктор по умолчанию.|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCDropDownFrame::Create](#create)|Создает объект `CMFCDropDownFrame`.|  
|`CMFCDropDownFrame::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Извлекает строки меню родительского фрейма раскрывающегося списка.|  
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Извлекает родительский во всплывающем меню фрейма раскрывающегося списка.|  
|`CMFCDropDownFrame::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Изменяет положение в раскрывающемся списке кадра.|  
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Задает дочернее окно инструментов, раскрывающийся список будет удален автоматически.|  
  
### <a name="remarks"></a>Примечания  
 Этот класс не предназначен для использования непосредственно из программного кода.  
  
 Платформа использует этот класс для предоставления поведение фрейма для `CMFCDropDownToolbar` и `CMFCDropDownToolbarButton` классы. Дополнительные сведения об этих классах см. в разделе [класса CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md) и [CMFCDropDownToolbarButton класса](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить указатель на `CMFCDropDownFrame` объекта из `CFrameWnd` класс и как задать дочерние окна с раскрывающимся списком будут автоматически удаляться.  
  
 [!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdropdowntoolbar.h  
  
##  <a name="create"></a>  CMFCDropDownFrame::Create  
 Создает объект `CMFCDropDownFrame`.  
  
```  
virtual BOOL Create(
    CWnd* pWndParent,  
    int x,  
    int y,  
    CMFCDropDownToolBar* pWndOriginToolbar);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pWndParent`|Родительское окно фрейма раскрывающегося списка.|  
|[in] `x`|Горизонтальная экранная координата для положения раскрывающемся кадра.|  
|[in] `y`|Вертикальная экранная координата для положения раскрывающемся кадра.|  
|[in] `pWndOriginToolbar`|Панель инструментов, расположены кнопки раскрывающегося списка, этот метод использует для заполнения нового объекта кадра раскрывающегося списка.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если раскрывающийся список кадров успешно создан; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает базовый [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) метод для создания окна фрейма раскрывающийся список с `WS_POPUP` стиля. Отображается окно фрейма раскрывающийся список с указанными экранными координатами. Этот метод завершается ошибкой, если [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) возвращает `FALSE`.  
  
 `CMFCDropDownFrame` Класс создает копию указанного `CMFCDropDownToolBar` параметра. Этот метод копирует изображения кнопок и состояния кнопок из `pWndOriginToolbar` параметр `m_pWndOriginToolbar` члена данных.  
  
##  <a name="getparentmenubar"></a>  CMFCDropDownFrame::GetParentMenuBar  
 Извлекает строки меню родительского фрейма раскрывающегося списка.  
  
```  
CMFCMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на меню родительского фрейма раскрывающегося списка или `NULL` Если кадр не имеет родителя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод извлекает строки меню родительского меню кнопки «родительский». Этот метод возвращает `NULL` Если кадра раскрывающийся список содержит кнопки без родительского или родительская кнопка Нет родительской строки меню.  
  
##  <a name="getparentpopupmenu"></a>  CMFCDropDownFrame::GetParentPopupMenu  
 Извлекает родительский во всплывающем меню фрейма раскрывающегося списка.  
  
```  
CMFCDropDownFrame* GetParentPopupMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель кадра раскрывающегося меню родительского или `NULL` Если кадр не имеет родителя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод получает его родительском меню с помощью кнопки родительского. Этот метод возвращает `NULL` Если кадра раскрывающийся список содержит кнопку Нет родительского или родительская кнопка Нет родительского меню.  
  
##  <a name="recalclayout"></a>  CMFCDropDownFrame::RecalcLayout  
 Изменяет положение в раскрывающемся списке кадра.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `bNotify`|Не используется.|  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод после создания фрейма раскрывающегося списка или изменении размера родительского окна. Этот метод вычисляет положение и размер кадра раскрывающегося списка, используя положение и размер родительского окна.  
  
##  <a name="setautodestroy"></a>  CMFCDropDownFrame::SetAutoDestroy  
 Задает дочернее окно инструментов, раскрывающийся список будет удален автоматически.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAutoDestroy`  
 `TRUE` автоматически при уничтожении окна инструментов связанный раскрывающегося списка. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если `bAutoDestroy` — `TRUE`, то `CMFCDropDownFrame` деструктор уничтожает окно инструментов связанный раскрывающегося списка. Значение по умолчанию — `TRUE`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [Класс CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
