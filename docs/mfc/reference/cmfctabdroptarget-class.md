---
title: "Класс CMFCTabDropTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabDropTarget class
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
caps.latest.revision: 22
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
ms.openlocfilehash: 31f9950df5974fe1561d601d4e9c26b3e8a96a62
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabdroptarget-class"></a>Класс CMFCTabDropTarget
Предоставляет механизм взаимодействия между вкладок и библиотеками OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|Вызывается платформой, когда пользователь перетаскивает объект в окно вкладки. (Переопределяет [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|  
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|Вызывается инфраструктурой при перетаскивании объекта за пределами вкладки окна, имеющий фокус. (Переопределяет [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|  
|[CMFCTabDropTarget::OnDragOver](#ondragover)|Вызывается инфраструктурой при перетаскивании объекта на вкладке окна, имеющий фокус. (Переопределяет [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|  
|[CMFCTabDropTarget::OnDropEx](#ondropex)|Вызывается платформой, когда пользователь отпускает кнопку мыши в конце операции перетаскивания. (Переопределяет [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|  
|[CMFCTabDropTarget::Register](#register)|Регистрирует элемент управления как элемент, который может быть целевым объектом операции и перетаскивания OLE.|  
  
### <a name="remarks"></a>Примечания  
 Этот класс обеспечивает поддержку и перетащите `CMFCBaseTabCtrl` класса. При инициализации приложения библиотеки OLE с помощью [AfxOleInit](ole-initialization.md#afxoleinit) функции `CMFCBaseTabCtrl` объекты регистрируются для операций и перетаскивания.  
  
 `CMFCTabDropTarget` Класс расширяет его базового класса, сделав вкладку, находящийся под курсором при выполнении операции перетаскивания active. Дополнительные сведения об операциях и перетащите см. в разделе [перетаскивания и Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется создание объекта `CMFCTabDropTarget` и использование его метода `Register`.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#39;](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbasetabctrl.h  
  
##  <a name="a-nameondragentera--cmfctabdroptargetondragenter"></a><a name="ondragenter"></a>CMFCTabDropTarget::OnDragEnter  
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
|Параметр|Описание|  
|[in] `pWnd`|Не используется.|  
|[in] `pDataObject`|Указатель на объект, который пользователь перетаскивает.|  
|[in] `dwKeyState`|Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, и `MK_RBUTTON`.|  
|[in] `point`|Расположение курсора в координатах клиента.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, получаемый в случае удаления в расположении, указанном в `point`. Это может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает `DROPEFFECT_NONE` framework инструментов не находится в режиме настройки или формата данных буфера недоступен. В противном случае, возвращается результат вызова метода `CMFCBaseTabCtrl::OnDragEnter` с указанными параметрами.  
  
 Дополнительные сведения о режиме настройки в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах данных буфера обмена в разделе [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="a-nameondragleavea--cmfctabdroptargetondragleave"></a><a name="ondragleave"></a>CMFCTabDropTarget::OnDragLeave  
 Вызывается инфраструктурой при перетаскивании объекта за пределами вкладки окна, имеющий фокус.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pWnd`|Не используется.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод `CMFCBaseTabCtrl::OnDragLeave` метод для выполнения операции перетаскивания.  
  
##  <a name="a-nameondragovera--cmfctabdroptargetondragover"></a><a name="ondragover"></a>CMFCTabDropTarget::OnDragOver  
 Вызывается инфраструктурой при перетаскивании объекта на вкладке окна, имеющий фокус.  
  
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
|Параметр|Описание|  
|[in] `pWnd`|Не используется.|  
|[in] `pDataObject`|Указатель на объект, который пользователь перетаскивает.|  
|[in] `dwKeyState`|Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, и `MK_RBUTTON`.|  
|[in] `point`|Расположение указателя мыши в клиентских координатах.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, получаемый в случае удаления в расположении, указанном в `point`. Это может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Примечания  
 Этот метод делает вкладку, находящийся под курсором при активной операции перетаскивания. Он возвращает `DROPEFFECT_NONE` framework инструментов не находится в режиме настройки или формата данных буфера недоступен. В противном случае, возвращается результат вызова метода `CMFCBaseTabCtrl::OnDragOver` с указанными параметрами.  
  
 Дополнительные сведения о режиме настройки в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах данных буфера обмена в разделе [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="a-nameondropexa--cmfctabdroptargetondropex"></a><a name="ondropex"></a>CMFCTabDropTarget::OnDropEx  
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
|Параметр|Описание|  
|[in] `pWnd`|Не используется.|  
|[in] `pDataObject`|Указатель на объект, который пользователь перетаскивает.|  
|[in] `dropEffect`|Операция удаления по умолчанию.|  
|[in] `dropList`|Не используется.|  
|[in] `point`|Расположение указателя мыши в клиентских координатах.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результирующий эффект перетаскивания. Это может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод `CMFCBaseTabCtrl::OnDrop` Если framework панель инструментов находится в режиме настройки и формата данных буфера обмена. Если вызов `CMFCBaseTabCtrl::OnDrop` возвращает ненулевое значение, этот метод возвращает эффект перетаскивания по умолчанию, определяемое `dropEffect`. В противном случае этот метод возвращает `DROPEFFECT_NONE`. Дополнительные сведения о эффектов перетаскивания см. в разделе [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).  
  
 Дополнительные сведения о режиме настройки в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах данных буфера обмена в разделе [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="a-nameregistera--cmfctabdroptargetregister"></a><a name="register"></a>CMFCTabDropTarget::Register  
 Регистрирует элемент управления как элемент, который может быть целевым объектом операции и перетаскивания OLE.  
  
```  
BOOL Register(CMFCBaseTabCtrl *pOwner);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pOwner`|Элемент управления вкладки для регистрации в качестве объекта-приемника.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если регистрация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) для регистрации элемента управления для операций и перетаскивания.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Перетаскивание (OLE)](../../mfc/drag-and-drop-ole.md)




