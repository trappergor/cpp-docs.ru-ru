---
title: "Класс COleDropTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDropTarget
- AFXOLE/COleDropTarget
- AFXOLE/COleDropTarget::COleDropTarget
- AFXOLE/COleDropTarget::OnDragEnter
- AFXOLE/COleDropTarget::OnDragLeave
- AFXOLE/COleDropTarget::OnDragOver
- AFXOLE/COleDropTarget::OnDragScroll
- AFXOLE/COleDropTarget::OnDrop
- AFXOLE/COleDropTarget::OnDropEx
- AFXOLE/COleDropTarget::Register
- AFXOLE/COleDropTarget::Revoke
dev_langs: C++
helpviewer_keywords:
- COleDropTarget [MFC], COleDropTarget
- COleDropTarget [MFC], OnDragEnter
- COleDropTarget [MFC], OnDragLeave
- COleDropTarget [MFC], OnDragOver
- COleDropTarget [MFC], OnDragScroll
- COleDropTarget [MFC], OnDrop
- COleDropTarget [MFC], OnDropEx
- COleDropTarget [MFC], Register
- COleDropTarget [MFC], Revoke
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fecdedc84f4fd93cbd9efe5e525c1771c5eb1c7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coledroptarget-class"></a>Класс COleDropTarget
Предоставляет механизм взаимодействия между окном и библиотеками OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDropTarget::COleDropTarget](#coledroptarget)|Создает объект `COleDropTarget`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDropTarget::OnDragEnter](#ondragenter)|Вызывается, когда курсор в первый раз входит окна.|  
|[COleDropTarget::OnDragLeave](#ondragleave)|Вызывается, когда курсор перемещается за пределы окна.|  
|[COleDropTarget::OnDragOver](#ondragover)|Вызывается несколько раз, когда курсор перемещается над окном.|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|Вызывается для определения, является ли курсор перетаскивается в область прокрутки окна.|  
|[COleDropTarget::OnDrop](#ondrop)|Вызывается при удалении данных в окно, обработчик по умолчанию.|  
|[COleDropTarget::OnDropEx](#ondropex)|Вызывается при удалении данных в окно начальной обработчика.|  
|[COleDropTarget::Register](#register)|Регистры-окно допустимым местом назначения.|  
|[COleDropTarget::Revoke](#revoke)|В результате окно, чтобы прекратить выполняется допустимым местом назначения.|  
  
## <a name="remarks"></a>Примечания  
 Для создания объекта этот класс разрешает окну для приема данных через механизм перетаскивания и вставки OLE.  
  
 Чтобы получить окно, чтобы принять команд drop, необходимо сначала создать объект `COleDropTarget` класса, а затем вызвать [зарегистрировать](#register) функция с указателем на нужном `CWnd` объекта является единственным параметром.  
  
 Дополнительные сведения об операциях и перетащите с помощью OLE, см. в статье [перетаскивания и Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coledroptarget"></a>COleDropTarget::COleDropTarget  
 Создает объект класса `COleDropTarget`.  
  
```  
COleDropTarget();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите [зарегистрировать](#register) для связи этого объекта с окном.  
  
##  <a name="ondragenter"></a>COleDropTarget::OnDragEnter  
 Вызывается платформой, когда курсор сначала перетаскивается в окне.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает на окно курсор ввода.  
  
 `pDataObject`  
 Указывает на объект данных, содержащая данные, которые могут быть удалены.  
  
 `dwKeyState`  
 Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, и **MK_RBUTTON**.  
  
 `point`  
 Содержит текущее положение курсора в клиентских координатах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, который создается в результате перетаскивания была предпринята попытка в расположении, заданном `point`. Может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`Удаление не допускается.  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Выполняется операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL`Операции перетаскивания прокрутки о или происходит в целевом объекте.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы разрешить операции удаления в окне. Реализация по умолчанию вызывает [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), возвращающая просто значение `DROPEFFECT_NONE` по умолчанию.  
  
 Дополнительные сведения см. в разделе [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) в Windows SDK.  
  
##  <a name="ondragleave"></a>COleDropTarget::OnDragLeave  
 Вызывается платформой, когда курсор покидает окно при операции перетаскивания.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает на окно курсор выходит из системы.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если требуется специальное поведение, когда операция перетаскивания выходит за пределы указанного окна. Реализация по умолчанию эта функция вызывает [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).  
  
 Дополнительные сведения см. в разделе [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110) в Windows SDK.  
  
##  <a name="ondragover"></a>COleDropTarget::OnDragOver  
 Вызывается платформой, когда курсор перемещается над окном.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Точки окна, которое наведен курсор.  
  
 `pDataObject`  
 Указывает объект данных, который содержит данные для удаления.  
  
 `dwKeyState`  
 Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, и **MK_RBUTTON**.  
  
 `point`  
 Содержит текущее положение курсора в клиентских координатах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, который создается в результате перетаскивания была предпринята попытка в расположении, заданном `point`. Может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`Удаление не допускается.  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Выполняется операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL`Указывает, что операции перетаскивания прокрутки о или происходит в целевом объекте.  
  
### <a name="remarks"></a>Примечания  
 Чтобы разрешить операции удаления в окне, следует переопределить эту функцию. Реализация по умолчанию эта функция вызывает [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), который возвращает `DROPEFFECT_NONE` по умолчанию. Поскольку эта функция вызывается часто во время операции перетаскивания и вставки, ее следует оптимизировать максимальной.  
  
 Дополнительные сведения см. в разделе [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="ondragscroll"></a>COleDropTarget::OnDragScroll  
 Вызывается платформой перед вызовом [OnDragEnter](#ondragenter) или [OnDragOver](#ondragover) для определения ли `point` находится в области прокрутки.  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, в которое наведен курсор.  
  
 `dwKeyState`  
 Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, и **MK_RBUTTON**.  
  
 `point`  
 Содержит расположение курсора в пикселях относительно экрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, который создается в результате перетаскивания была предпринята попытка в расположении, заданном `point`. Может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`Удаление не допускается.  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Выполняется операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL`Указывает, что операции перетаскивания прокрутки о или происходит в целевом объекте.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите предоставить особое поведение для данного события. Реализация по умолчанию эта функция вызывает [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), который возвращает `DROPEFFECT_NONE` и прокрутка окна при перетаскивании курсор в область прокрутки по умолчанию внутри границы окна.  
  
##  <a name="ondrop"></a>COleDropTarget::OnDrop  
 Вызывается платформой при операции удаления.  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, в которое наведен курсор.  
  
 `pDataObject`  
 Указывает объект данных, который содержит данные для удаления.  
  
 `dropEffect`  
 Эффект, который пользователь выбрал для операции удаления. Может быть один или несколько из следующих:  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Выполняется операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
 `point`  
 Содержит расположение курсора в пикселях относительно экрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если удаления прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Сначала вызывает framework [OnDropEx](#ondropex). Если `OnDropEx` функция обрабатывает удаления, затем, платформа вызывает эту функцию-член, `OnDrop`. Как правило, оно переопределяет [OnDropEx](../../mfc/reference/cview-class.md#ondropex) в классе представления для обработки правой кнопки мыши путем перетаскивания. Как правило, класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) используется для обработки простой операции перетаскивания.  
  
 Реализация по умолчанию `COleDropTarget::OnDrop` вызовы [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), возвращающая просто значение **FALSE** по умолчанию.  
  
 Дополнительные сведения см. в разделе [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) в Windows SDK.  
  
##  <a name="ondropex"></a>COleDropTarget::OnDropEx  
 Вызывается платформой при операции удаления.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на окно, в которое наведен курсор.  
  
 `pDataObject`  
 Указывает объект данных, который содержит данные для удаления.  
  
 `dropDefault`  
 Эффект, который пользователь выбрал для операции удаления по умолчанию, исходя из текущего состояния ключа. Это может быть `DROPEFFECT_NONE`. Эффектов перетаскивания описаны в разделе "Примечания".  
  
 `dropList`  
 Список эффектов перетаскивания, которые поддерживает источнику. DROP эффект значения могут быть объединены с помощью побитового или ( **&#124;**) операции. Эффектов перетаскивания описаны в разделе "Примечания".  
  
 `point`  
 Содержит расположение курсора в пикселях относительно экрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект сброса, полученным в результате попытка удаления в местоположении, заданном свойством `point`. Эффектов перетаскивания описаны в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Во-первых, платформа вызывает эту функцию. Если он не обрабатывает удаления, затем вызывается метод [OnDrop](#ondrop). Как правило, будут переопределены [OnDropEx](../../mfc/reference/cview-class.md#ondropex) в классе представления для поддержки правой кнопки мыши путем перетаскивания. Как правило, класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) используется для обработки случая поддержка простой операции перетаскивания.  
  
 Реализация по умолчанию `COleDropTarget::OnDropEx` вызовы [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). По умолчанию [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) просто возвращает фиктивное значение, указывающее [OnDrop](#ondrop) следует вызвать функцию-член.  
  
 Эффектов перетаскивания описаны действия, связанные с операцией перетаскивания. Ниже представлен список эффектов перетаскивания:  
  
- `DROPEFFECT_NONE`Удаление не допускается.  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Выполняется операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL`Указывает, что операции перетаскивания прокрутки о или происходит в целевом объекте.  
  
 Дополнительные сведения см. в разделе [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) в Windows SDK.  
  
##  <a name="register"></a>COleDropTarget::Register  
 Эта функция вызывается для регистрации вашего окна OLE библиотек DLL допустимым местом назначения.  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Точки окна, которое должно быть зарегистрировано в качестве цели перетаскивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если регистрация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это функция должна вызываться для операции удаления могут быть приняты.  
  
 Дополнительные сведения см. в разделе [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405) в Windows SDK.  
  
##  <a name="revoke"></a>COleDropTarget::Revoke  
 Вызывайте эту функцию перед удалением любого окна, который был зарегистрирован в качестве цели перетаскивания путем вызова [зарегистрировать](#register) Чтобы удалить его из списка мест перетаскивания.  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается автоматически из [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) обработчик для окна, которое был зарегистрирован, поэтому он обычно не требуется явно вызывать эту функцию.  
  
 Дополнительные сведения см. в разделе [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDropSource](../../mfc/reference/coledropsource-class.md)
