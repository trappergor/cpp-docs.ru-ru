---
title: "Класс CMFCTabDropTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
dev_langs: C++
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ff17f7312f5e04b6ae900e792523155705a3b4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctabdroptarget-class"></a>Класс CMFCTabDropTarget
Предоставляет механизм взаимодействия между набор вкладок и библиотеками OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание:|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|Вызывается платформой, когда пользователь перетаскивает объект в окно вкладки. (Переопределяет [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|  
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|Вызывается платформой при перетаскивании объекта за пределами вкладки окна, имеющий фокус. (Переопределяет [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|  
|[CMFCTabDropTarget::OnDragOver](#ondragover)|Вызывается платформой, когда пользователь перетаскивает объект в окно вкладки, на который установлен фокус. (Переопределяет [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|  
|[CMFCTabDropTarget::OnDropEx](#ondropex)|Вызывается платформой, когда пользователь отпускает кнопку мыши в конце операции перетаскивания. (Переопределяет [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|  
|[CMFCTabDropTarget::Register](#register)|Регистрирует элемент управления как элемент, который может быть целевым объектом операции перетаскивания и вставки OLE.|  
  
### <a name="remarks"></a>Примечания  
 Этот класс обеспечивает поддержку и перетащите `CMFCBaseTabCtrl` класса. Если приложение инициализирует библиотеки OLE с помощью [AfxOleInit](ole-initialization.md#afxoleinit) функции `CMFCBaseTabCtrl` объекты регистрируются для операций перетаскивания и вставки.  
  
 `CMFCTabDropTarget` Класс расширяет его базовый класс, делая вкладку, находящийся под курсором при активной операции перетаскивания. Дополнительные сведения об операциях и перетащите см. в разделе [перетаскивания и Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется создание объекта `CMFCTabDropTarget` и использование его метода `Register`.  
  
 [!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbasetabctrl.h  
  
##  <a name="ondragenter"></a>CMFCTabDropTarget::OnDragEnter  
 Вызывается платформой, когда пользователь перетаскивает объект в окно вкладки.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `pWnd`|Не используется.|  
|[in] `pDataObject`|Указатель на объект, который пользователь перетаскивает.|  
|[in] `dwKeyState`|Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, и `MK_RBUTTON`.|  
|[in] `point`|Расположение курсора в клиентских координатах.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, получаемый в случае удаления в расположении, заданном `point`. Может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает `DROPEFFECT_NONE` framework инструментов не находится в режиме настройки или формат данных буфер обмена недоступен. В противном случае он возвращает результат вызова `CMFCBaseTabCtrl::OnDragEnter` с помощью указанных параметров.  
  
 Дополнительные сведения о режиме настройки см. в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах данных буфера обмена в разделе [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="ondragleave"></a>CMFCTabDropTarget::OnDragLeave  
 Вызывается платформой при перетаскивании объекта за пределами вкладки окна, имеющий фокус.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `pWnd`|Не используется.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод `CMFCBaseTabCtrl::OnDragLeave` метод для выполнения операции перетаскивания.  
  
##  <a name="ondragover"></a>CMFCTabDropTarget::OnDragOver  
 Вызывается платформой, когда пользователь перетаскивает объект в окно вкладки, на который установлен фокус.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `pWnd`|Не используется.|  
|[in] `pDataObject`|Указатель на объект, который пользователь перетаскивает.|  
|[in] `dwKeyState`|Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, и `MK_RBUTTON`.|  
|[in] `point`|Расположение указателя мыши в клиентских координатах.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, получаемый в случае удаления в расположении, заданном `point`. Может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Примечания  
 Этот метод делает вкладку, находящийся под курсором при активной операции перетаскивания. Он возвращает `DROPEFFECT_NONE` framework инструментов не находится в режиме настройки или формат данных буфер обмена недоступен. В противном случае он возвращает результат вызова `CMFCBaseTabCtrl::OnDragOver` с помощью указанных параметров.  
  
 Дополнительные сведения о режиме настройки см. в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах данных буфера обмена в разделе [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="ondropex"></a>CMFCTabDropTarget::OnDropEx  
 Вызывается платформой, когда пользователь отпускает кнопку мыши в конце операции перетаскивания.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `pWnd`|Не используется.|  
|[in] `pDataObject`|Указатель на объект, который пользователь перетаскивает.|  
|[in] `dropEffect`|Операция перетаскивания по умолчанию.|  
|[in] `dropList`|Не используется.|  
|[in] `point`|Расположение указателя мыши в клиентских координатах.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результирующий эффект перетаскивания. Может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод `CMFCBaseTabCtrl::OnDrop` Если инструментов framework устанавливается в режим настройки и формат данных буфер обмена. Если вызов `CMFCBaseTabCtrl::OnDrop` возвращает ненулевое значение, этот метод возвращает эффект перетаскивания по умолчанию, определяемое `dropEffect`. В противном случае этот метод возвращает `DROPEFFECT_NONE`. Дополнительные сведения о эффектов перетаскивания см. в разделе [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).  
  
 Дополнительные сведения о режиме настройки см. в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах данных буфера обмена в разделе [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="register"></a>CMFCTabDropTarget::Register  
 Регистрирует элемент управления как элемент, который может быть целевым объектом операции перетаскивания и вставки OLE.  
  
```  
BOOL Register(CMFCBaseTabCtrl *pOwner);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `pOwner`|Элемент управления вкладки для регистрации в качестве конечного расположения сброса.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если регистрация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) Чтобы зарегистрировать элемент управления для операций перетаскивания и вставки.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Перетаскивание (OLE)](../../mfc/drag-and-drop-ole.md)



