---
title: "Класс CMFCDropDownFrame | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCDropDownFrame class
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
caps.latest.revision: 23
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
ms.openlocfilehash: 5f045e4a3b580f12e64758737495c32963bea6db
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdownframe-class"></a>Класс CMFCDropDownFrame
Предоставляет функциональные возможности окна фрейма раскрывающегося списка в раскрывающемся списке панели инструментов и кнопки раскрывающегося списка на панели инструментов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## <a name="members"></a>Члены  
  
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
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Извлекает меню родительского фрейма раскрывающегося списка.|  
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Извлекает контекстного меню родительского фрейма раскрывающегося списка.|  
|`CMFCDropDownFrame::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Перемещает кадра раскрывающегося списка.|  
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Задает значение, указывающее дочернее окно раскрывающимся списком удаляется автоматически.|  
  
### <a name="remarks"></a>Примечания  
 Этот класс не предназначен для непосредственного использования в коде.  
  
 Платформа использует этот класс для предоставления поведения рамки `CMFCDropDownToolbar` и `CMFCDropDownToolbarButton` классы. Дополнительные сведения об этих классах см. в разделе [класса CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md) и [CMFCDropDownToolbarButton класса](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как получить указатель на `CMFCDropDownFrame` объекта из `CFrameWnd` класс и Установка дочернего окна раскрывающимся списком будут автоматически удаляться.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#36;](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdropdowntoolbar.h  
  
##  <a name="create"></a>CMFCDropDownFrame::Create  
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
|[in] `x`|Горизонтальная экранная координата расположения раскрывающемся кадра.|  
|[in] `y`|Вертикальная экранная координата расположения раскрывающемся кадра.|  
|[in] `pWndOriginToolbar`|Панель инструментов, расположены кнопки раскрывающегося списка, этот метод используется для заполнения нового объекта кадра раскрывающегося списка.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если раскрывающийся список кадров был успешно создан; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает базовый [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) метод для создания окна фрейма раскрывающийся список с `WS_POPUP` стиля. Появится окно раскрывающегося списка указанными экранными координатами. Этот метод не выполняется, если [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) возвращает метод `FALSE`.  
  
 `CMFCDropDownFrame` Класс создает копию указанных `CMFCDropDownToolBar` параметр. Этот метод копирует изображения кнопок и состояний кнопки из `pWndOriginToolbar` параметр `m_pWndOriginToolbar` члена данных.  
  
##  <a name="getparentmenubar"></a>CMFCDropDownFrame::GetParentMenuBar  
 Извлекает меню родительского фрейма раскрывающегося списка.  
  
```  
CMFCMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на меню родительского фрейма раскрывающегося списка или `NULL` Если кадр не имеет родителя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод получает меню родительского меню кнопки «родительский». Этот метод возвращает `NULL` Если кадров имеет нет родительская кнопка или кнопка родительского меню нет родительского.  
  
##  <a name="getparentpopupmenu"></a>CMFCDropDownFrame::GetParentPopupMenu  
 Извлекает контекстного меню родительского фрейма раскрывающегося списка.  
  
```  
CMFCDropDownFrame* GetParentPopupMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель кадра раскрывающегося меню родительского или `NULL` Если кадр не имеет родителя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод получает родительского меню из родительского кнопки. Этот метод возвращает `NULL` Если нет родительская кнопка имеет кадров или родительская кнопка Нет родительского меню.  
  
##  <a name="recalclayout"></a>CMFCDropDownFrame::RecalcLayout  
 Перемещает кадра раскрывающегося списка.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `bNotify`|Не используется.|  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда кадров создается или изменяется родительского окна. Этот метод вычисляет положение и размер кадра раскрывающийся список с помощью положение и размер родительского окна.  
  
##  <a name="setautodestroy"></a>CMFCDropDownFrame::SetAutoDestroy  
 Задает значение, указывающее дочернее окно раскрывающимся списком удаляется автоматически.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAutoDestroy`  
 `TRUE`автоматически уничтожении окна соответствующей раскрывающемся списке панели инструментов; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если `bAutoDestroy` — `TRUE`, то `CMFCDropDownFrame` деструктор уничтожает окно соответствующей панели инструментов в раскрывающемся списке. Значение по умолчанию — `TRUE`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [Класс CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

