---
title: "Класс COleDropTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- COleDropTarget class
- drag and drop, drop target
- drop commands, accepting
- drop commands
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0e9429d531d6af86bc571b1f871fbcd4a8fe2532
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="coledroptarget-class"></a>Класс COleDropTarget
Предоставляет механизм взаимодействия между окном и библиотеками OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDropTarget::COleDropTarget](#coledroptarget)|Создает объект `COleDropTarget`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDropTarget::OnDragEnter](#ondragenter)|Вызывается, когда указатель мыши впервые входит окна.|  
|[COleDropTarget::OnDragLeave](#ondragleave)|Вызывается при перемещении курсора за окна.|  
|[COleDropTarget::OnDragOver](#ondragover)|Вызывается многократно при перетаскивании курсора над окном.|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|Вызывается, чтобы определить, является ли курсор перетаскивается в область прокрутки окна.|  
|[COleDropTarget::OnDrop](#ondrop)|Вызывается при удалении данных в окно, обработчик по умолчанию.|  
|[COleDropTarget::OnDropEx](#ondropex)|Вызывается при удалении данных в окно исходного обработчика.|  
|[COleDropTarget::Register](#register)|Регистры-окно как допустимый целевой объект перетаскивания.|  
|[COleDropTarget::Revoke](#revoke)|В результате окно, чтобы прекратить, который является допустимой целью перетаскивания.|  
  
## <a name="remarks"></a>Примечания  
 Для создания объекта этого класса позволяет окна для приема данных через механизм и перетаскивания OLE.  
  
 Чтобы получить окна для принятия команд drop, необходимо сначала создать объект `COleDropTarget` класса, а затем вызвать [зарегистрировать](#register) функция с указателем на нужный `CWnd` объект в качестве единственного параметра.  
  
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
 Вызов [зарегистрировать](#register) для связи этого объекта с окном.  
  
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
 Указывает объект данных, содержащий данные, которые могут быть удалены.  
  
 `dwKeyState`  
 Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, и **MK_RBUTTON**.  
  
 `point`  
 Содержит текущее положение курсора в координатах клиента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, который создается в результате перетаскивания была предпринята попытка в расположении, указанном в `point`. Это может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`Удаление не допускается.  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Будет выполнена операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL`Операции перетаскивания прокрутки о или происходит в целевой базе данных.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы разрешить операции удаления в окне. Реализация по умолчанию вызывает [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), который просто возвращает `DROPEFFECT_NONE` по умолчанию.  
  
 Дополнительные сведения см. в разделе [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondragleave"></a>COleDropTarget::OnDragLeave  
 Вызывается платформой, когда курсор перемещается за границы окна пока операцию перетаскивания.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает на окно курсор оставляет.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если требуется специальное поведение, когда операция перетаскивания выходит за пределы указанного окна. Реализация по умолчанию эта функция вызывает [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).  
  
 Дополнительные сведения см. в разделе [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondragover"></a>COleDropTarget::OnDragOver  
 Вызывается инфраструктурой при перемещении курсора над окном.  
  
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
 Указывает объект данных, содержащий данные для удаления.  
  
 `dwKeyState`  
 Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, и **MK_RBUTTON**.  
  
 `point`  
 Содержит текущее положение курсора в координатах клиента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, который создается в результате перетаскивания была предпринята попытка в расположении, указанном в `point`. Это может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`Удаление не допускается.  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Будет выполнена операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL`Указывает, что операция перетаскивания прокрутки о или происходит в целевой базе данных.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию следует переопределить, чтобы разрешить операции удаления в окне. Реализация по умолчанию эта функция вызывает [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), который возвращает `DROPEFFECT_NONE` по умолчанию. Поскольку эта функция вызывается часто во время операции и перетаскивания, его необходимо оптимизировать максимальной.  
  
 Дополнительные сведения см. в разделе [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#21;](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="ondragscroll"></a>COleDropTarget::OnDragScroll  
 Вызывается средой перед вызовом метода [OnDragEnter](#ondragenter) или [OnDragOver](#ondragover) для определения ли `point` в область прокрутки.  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает на окно, которое наведен курсор.  
  
 `dwKeyState`  
 Содержит состояние клавиши-модификаторы. Это сочетание любое количество следующих: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, и **MK_RBUTTON**.  
  
 `point`  
 Содержит расположение курсора в пикселях, относительно экрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, который создается в результате перетаскивания была предпринята попытка в расположении, указанном в `point`. Это может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`Удаление не допускается.  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Будет выполнена операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL`Указывает, что операция перетаскивания прокрутки о или происходит в целевой базе данных.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите предоставить специальное поведение для данного события. Реализация по умолчанию эта функция вызывает [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), который возвращает `DROPEFFECT_NONE` и прокрутка окна при перетаскивании курсора по умолчанию область прокрутки внутри границы окна.  
  
##  <a name="ondrop"></a>COleDropTarget::OnDrop  
 Вызывается инфраструктурой при операции перетаскивания.  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает на окно, которое наведен курсор.  
  
 `pDataObject`  
 Указывает объект данных, содержащий данные для удаления.  
  
 `dropEffect`  
 Эффект, который пользователь выбрал для операции удаления. Это может быть один или несколько из следующих:  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Будет выполнена операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
 `point`  
 Содержит расположение курсора в пикселях, относительно экрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если освобождение прошло успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Сначала вызывает framework [OnDropEx](#ondropex). Если `OnDropEx` функция обрабатывает удаления, платформа затем вызывает эту функцию-член, `OnDrop`. Как правило, приложение переопределяет [OnDropEx](../../mfc/reference/cview-class.md#ondropex) в классе представления для обработки правой кнопки мыши перетаскивание. Как правило, класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) используется для обработки простой операции перетаскивания.  
  
 Реализация по умолчанию `COleDropTarget::OnDrop` вызовов [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), который просто возвращает **FALSE** по умолчанию.  
  
 Дополнительные сведения см. в разделе [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondropex"></a>COleDropTarget::OnDropEx  
 Вызывается инфраструктурой при операции перетаскивания.  
  
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
 Указывает на окно, которое наведен курсор.  
  
 `pDataObject`  
 Указывает объект данных, содержащий данные для удаления.  
  
 `dropDefault`  
 Эффект, который пользователь выбрал для операции удаления по умолчанию, исходя из текущего состояния ключа. Он может быть `DROPEFFECT_NONE`. Эффектов перетаскивания рассматриваются в разделе «Примечания».  
  
 `dropList`  
 Список эффектов перетаскивания, которые поддерживает источника перетаскивания. Значения эффект перетаскивания можно объединить с помощью побитового или ( **|**) операции. Эффектов перетаскивания рассматриваются в разделе «Примечания».  
  
 `point`  
 Содержит расположение курсора в пикселях, относительно экрана.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эффект, полученным в результате попытки удаления в расположении, заданном по `point`. Эффектов перетаскивания рассматриваются в разделе «Примечания».  
  
### <a name="remarks"></a>Примечания  
 Платформа сначала вызывает эту функцию. Если он не обрабатывает удаления, затем вызывается метод [OnDrop](#ondrop). Как правило, можно переопределить [OnDropEx](../../mfc/reference/cview-class.md#ondropex) в классе представления для поддержки правой кнопки мыши перетаскивание. Как правило, класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) используется для обработки в случае поддержки для простой операции перетаскивания.  
  
 Реализация по умолчанию `COleDropTarget::OnDropEx` вызовов [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). По умолчанию [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) просто возвращает фиктивное значение, указывающее [OnDrop](#ondrop) следует вызывать функции-члена.  
  
 Эффекты перетаскивания описаны действия, связанные с операцией перетаскивания. Следующий список эффектов перетаскивания см.:  
  
- `DROPEFFECT_NONE`Удаление не допускается.  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Будет выполнена операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL`Указывает, что операция перетаскивания прокрутки о или происходит в целевой базе данных.  
  
 Дополнительные сведения см. в разделе [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="register"></a>COleDropTarget::Register  
 Эта функция вызывается для регистрации окна в OLE библиотеки DLL как допустимый целевой объект перетаскивания.  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Точки окна, которое должно быть зарегистрировано в качестве объекта-приемника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если регистрация успешна; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это функция должна вызываться для операции удаления могут быть приняты.  
  
 Дополнительные сведения см. в разделе [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="revoke"></a>COleDropTarget::Revoke  
 Эта функция вызывается перед удалением любого окна, который зарегистрирован в качестве цели перетаскивания путем вызова [зарегистрировать](#register) необходимо удалить его из списка целевых объектов перетаскивания.  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается автоматически [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) обработчик для окна, которое было зарегистрировано, поэтому он обычно нет необходимости явно вызывать данную функцию.  
  
 Дополнительные сведения см. в разделе [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDropSource](../../mfc/reference/coledropsource-class.md)

