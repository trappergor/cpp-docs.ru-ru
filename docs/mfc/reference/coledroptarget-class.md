---
title: Класс COleDropTarget | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d54a22bd215a80f3e7cab3770a4ba12cd7baffb
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027446"
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
|[COleDropTarget::OnDragEnter](#ondragenter)|Вызывается, когда указатель мыши впервые входит окна.|  
|[COleDropTarget::OnDragLeave](#ondragleave)|Вызывается, когда курсор перемещается за пределы окна.|  
|[COleDropTarget::OnDragOver](#ondragover)|Вызывается несколько раз, когда курсор перемещается над окном.|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|Вызывается для определения ли курсор перемещается в область прокрутки окна.|  
|[COleDropTarget::OnDrop](#ondrop)|Вызывается при удалении данных в окно, обработчик по умолчанию.|  
|[COleDropTarget::OnDropEx](#ondropex)|Вызывается при вставке данных в окне начальной обработчика.|  
|[COleDropTarget::Register](#register)|Регистрирует окно как допустимым конечным расположением сброса.|  
|[COleDropTarget::Revoke](#revoke)|Вызывает окно к прекращению будет допустимым конечным расположением сброса.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта данного класса разрешает окну для приема данных через механизм перетаскивания и вставки OLE.  
  
 Чтобы получить окна для принятия команд drop, необходимо сначала создать объект `COleDropTarget` класса, а затем вызвать [зарегистрировать](#register) функции с указателем на нужный `CWnd` объект в качестве единственного параметра.  
  
 Дополнительные сведения об операциях перетаскивания и вставки через интерфейсы OLE, см. в статье [Drag and Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coledroptarget"></a>  COleDropTarget::COleDropTarget  
 Создает объект класса `COleDropTarget`.  
  
```  
COleDropTarget();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите [зарегистрировать](#register) должен быть сопоставлен этот объект окна.  
  
##  <a name="ondragenter"></a>  COleDropTarget::OnDragEnter  
 Вызывается платформой, когда курсор сначала перетаскивается в окне.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Вводит точек в окно курсор.  
  
 *pDataObject*  
 Указывает объект данных, содержащий данные, которые могут быть удалены.  
  
 *dwKeyState*  
 Содержит состояние клавиши-модификаторы. Это представляет собой сочетание любое количество следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.  
  
 *точка*  
 Содержит текущее положение курсора в координатах клиентской области окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, который создается в результате перетаскивания была предпринята в расположении, указанном по *точки*. Это может быть один или несколько из следующих:  
  
- Не сможет достичь DROPEFFECT_NONE объект перетаскивания.  
  
- DROPEFFECT_COPY, операция копирования будет выполнена.  
  
- Выполняется операция перемещения объект DROPEFFECT_MOVE.  
  
- Будет установлено DROPEFFECT_LINK ссылку по почте из перенесенных данных с исходными данными.  
  
- Операция прокрутки перетащите объект DROPEFFECT_SCROLL о или происходит в целевом объекте.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы разрешить выполнение операций перетаскивания в окне. По умолчанию реализация вызывает [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), который просто возвращает DROPEFFECT_NONE по умолчанию.  
  
 Дополнительные сведения см. в разделе [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) в пакете Windows SDK.  
  
##  <a name="ondragleave"></a>  COleDropTarget::OnDragLeave  
 Вызывается платформой, когда курсор покидает окно, пока действует операцию перетаскивания.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Выходит из точек в окно курсор.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если требуется специальное поведение, когда операция перетаскивания выходит за пределы указанного окна. Реализация по умолчанию эта функция вызывает [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).  
  
 Дополнительные сведения см. в разделе [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110) в пакете Windows SDK.  
  
##  <a name="ondragover"></a>  COleDropTarget::OnDragOver  
 Вызывается платформой, когда курсор перемещается над окном.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Точки в окно, в которой находится курсор над.  
  
 *pDataObject*  
 Указывает объект данных, содержащий данные для удаления.  
  
 *dwKeyState*  
 Содержит состояние клавиши-модификаторы. Это представляет собой сочетание любое количество следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.  
  
 *точка*  
 Содержит текущее положение курсора в координатах клиентской области окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, который создается в результате перетаскивания была предпринята в расположении, указанном по *точки*. Это может быть один или несколько из следующих:  
  
- Не сможет достичь DROPEFFECT_NONE объект перетаскивания.  
  
- DROPEFFECT_COPY, операция копирования будет выполнена.  
  
- Выполняется операция перемещения объект DROPEFFECT_MOVE.  
  
- Будет установлено DROPEFFECT_LINK ссылку по почте из перенесенных данных с исходными данными.  
  
- DROPEFFECT_SCROLL указывает, что операции перетаскивания прокрутки о или происходит в целевом объекте.  
  
### <a name="remarks"></a>Примечания  
 Разрешить выполнение операций перетаскивания в окне, следует переопределить эту функцию. Реализация по умолчанию эта функция вызывает [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), который возвращает DROPEFFECT_NONE по умолчанию. Так как эта функция вызывается часто во время операции перетаскивания и вставки, ее следует оптимизировать насколько это возможно.  
  
 Дополнительные сведения см. в разделе [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129) в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="ondragscroll"></a>  COleDropTarget::OnDragScroll  
 Вызвано структурой перед вызовом [OnDragEnter](#ondragenter) или [OnDragOver](#ondragover) для определения ли *точки* находится в области прокрутки.  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Указывает на окно, которое наведен курсор.  
  
 *dwKeyState*  
 Содержит состояние клавиши-модификаторы. Это представляет собой сочетание любое количество следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.  
  
 *точка*  
 Содержит расположение курсора, в пикселях, относительно экрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, который создается в результате перетаскивания была предпринята в расположении, указанном по *точки*. Это может быть один или несколько из следующих:  
  
- Не сможет достичь DROPEFFECT_NONE объект перетаскивания.  
  
- DROPEFFECT_COPY, операция копирования будет выполнена.  
  
- Выполняется операция перемещения объект DROPEFFECT_MOVE.  
  
- Будет установлено DROPEFFECT_LINK ссылку по почте из перенесенных данных с исходными данными.  
  
- DROPEFFECT_SCROLL указывает, что операции перетаскивания прокрутки о или происходит в целевом объекте.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите создать специальное поведение для этого события. Реализация по умолчанию эта функция вызывает [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), который возвращает DROPEFFECT_NONE и прокрутка окна, когда указатель перетаскивается в область прокрутки по умолчанию внутри границы окна.  
  
##  <a name="ondrop"></a>  COleDropTarget::OnDrop  
 Вызывается платформой при операции перетаскивания.  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
*pWnd*  
 Указывает на окно, которое наведен курсор.  
  
*pDataObject*  
Указывает объект данных, содержащий данные для удаления.  
  
*dropEffect*  
Эффект, который пользователь выбрал для операции удаления. Это может быть один или несколько из следующих:  
  
 - DROPEFFECT_COPY, операция копирования будет выполнена.  
       
 - Выполняется операция перемещения объект DROPEFFECT_MOVE.  
      
 - Будет установлено DROPEFFECT_LINK ссылку по почте из перенесенных данных с исходными данными.  
  
*точка*  
Содержит расположение курсора, в пикселях, относительно экрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если освобождение прошло успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Сначала вызывает framework [OnDropEx](#ondropex). Если `OnDropEx` функция не обрабатывает удаления, затем вызывается эта функция-член, `OnDrop`. Как правило, оно переопределяет [OnDropEx](../../mfc/reference/cview-class.md#ondropex) в классе представления для обработки правой кнопки мыши путем перетаскивания. Как правило, класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) используется для обработки простой операции перетаскивания.  
  
 Реализация по умолчанию `COleDropTarget::OnDrop` вызовы [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), который просто возвращает значение FALSE по умолчанию.  
  
 Дополнительные сведения см. в разделе [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) в пакете Windows SDK.  
  
##  <a name="ondropex"></a>  COleDropTarget::OnDropEx  
 Вызывается платформой при операции перетаскивания.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Указывает на окно, которое наведен курсор.  
  
 *pDataObject*  
 Указывает объект данных, содержащий данные для удаления.  
  
 *dropDefault*  
 Эффект, который пользователь выбрал для операции удаления по умолчанию, на основании текущего состояния ключа. Это может быть DROPEFFECT_NONE. Эффекты перетаскивания рассматриваются в разделе "Примечания".  
  
 *из раскрывающегося списка*  
 Список эффектов перетаскивания, поддерживаемый источником перетаскивания. Значения эффект перетаскивания могут быть объединены с помощью побитовой операции или (**&#124;**) операции. Эффекты перетаскивания рассматриваются в разделе "Примечания".  
  
 *точка*  
 Содержит расположение курсора, в пикселях, относительно экрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект падающей, полученное в результате попытка удаления в расположении, указанном по *точки*. Эффекты перетаскивания рассматриваются в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Во-первых, платформа вызывает эту функцию. Если он не обрабатывает удаления, затем вызывается платформой [OnDrop](#ondrop). Как правило, будут переопределены [OnDropEx](../../mfc/reference/cview-class.md#ondropex) в классе представления для поддержки правой кнопки мыши путем перетаскивания. Как правило, класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) используется для обработки случая, поддержку простого перетаскивания.  
  
 Реализация по умолчанию `COleDropTarget::OnDropEx` вызовы [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). По умолчанию [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) просто возвращает значение, указывающее фиктивный [OnDrop](#ondrop) следует вызвать функцию-член.  
  
 Эффекты перетаскивания описывают действие, связанное с операцией перетаскивания. См. ниже приведен список эффектов перетаскивания.  
  
 - Не сможет достичь DROPEFFECT_NONE объект перетаскивания.  
  
 - DROPEFFECT_COPY, операция копирования будет выполнена.  
  
 - Выполняется операция перемещения объект DROPEFFECT_MOVE.  
  
 - Будет установлено DROPEFFECT_LINK ссылку по почте из перенесенных данных с исходными данными.  
  
 - DROPEFFECT_SCROLL указывает, что операции перетаскивания прокрутки о или происходит в целевом объекте.  
  
 Дополнительные сведения см. в разделе [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) в пакете Windows SDK.  
  
##  <a name="register"></a>  COleDropTarget::Register  
 Эта функция вызывается для регистрации вашего окна OLE библиотек DLL как допустимым конечным расположением сброса.  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Указывает на окно, которое должно быть зарегистрировано в качестве цели перетаскивания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если регистрация прошла успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию необходимо вызывать для операции удаления принятия.  
  
 Дополнительные сведения см. в разделе [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405) в пакете Windows SDK.  
  
##  <a name="revoke"></a>  COleDropTarget::Revoke  
 Вызывайте эту функцию перед удалением любого окна, который был зарегистрирован в качестве целевого объекта перетаскивания путем вызова [зарегистрировать](#register) Чтобы удалить его из списка мест назначения перетаскивания.  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается автоматически из [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) обработчик для окна, которое было зарегистрировано, поэтому он обычно нет необходимости явно вызов этой функции.  
  
 Дополнительные сведения см. в разделе [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643) в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDropSource](../../mfc/reference/coledropsource-class.md)
