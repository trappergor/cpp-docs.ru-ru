---
title: "Класс COleDropSource | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
dev_langs:
- C++
helpviewer_keywords:
- drag operations
- drop target, dragging data to
- COleDropSource class
- drag and drop, drop source
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f3d0e5b7184cf305459173065b8e1cc07e032aef
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="coledropsource-class"></a>Класс COleDropSource
Позволяет данным путем перетаскивания объекта-приемника.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDropSource::COleDropSource](#coledropsource)|Создает объект `COleDropSource`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDropSource::GiveFeedback](#givefeedback)|Курсор изменяется во время операции перетаскивания и drop.|  
|[COleDropSource::OnBeginDrag](#onbegindrag)|Обрабатывает захват мыши во время операции перетаскивания и drop.|  
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Проверяет, является ли перетаскивание следует продолжить.|  
  
## <a name="remarks"></a>Примечания  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md) класс обрабатывает принимающей часть операции, и перетащите. `COleDropSource` Объект отвечает за определение, когда начинается операция перетаскивания, обратная связь во время операции перетаскивания и определение, когда завершается операция перетаскивания.  
  
 Для использования `COleDropSource` , просто вызовите конструктор. Это упрощает процесс определения, какие события, такие как щелчок мыши начать операцию перетаскивания с помощью [COleDataSource::DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), или [COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) функции. Эти функции будут создавать `COleDropSource` объект. Может возникнуть необходимость изменить поведение по умолчанию `COleDropSource` переопределяемые функции. Эти функции-члены будут вызываться в нужное время платформа.  
  
 Дополнительные сведения об операциях и перетащите с помощью OLE, см. в статье [перетаскивания и Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Дополнительные сведения см. в разделе [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coledropsource"></a>COleDropSource::COleDropSource  
 Создает объект `COleDropSource`.  
  
```  
COleDropSource();
```  
  
##  <a name="givefeedback"></a>COleDropSource::GiveFeedback  
 Вызывается платформой после вызова метода [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) или [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).  
  
```  
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```  
  
### <a name="parameters"></a>Параметры  
 `dropEffect`  
 Эффект, который вы хотите отобразить для пользователя, как правило, указывающее, что произойдет при перетаскивании на этом этапе с помощью выбранных данных. Как правило, это значение, возвращенное в последнем вызове [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) или [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Это может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE`Удаление не допускается.  
  
- `DROPEFFECT_COPY`Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE`Будет выполнена операция перемещения.  
  
- `DROPEFFECT_LINK`Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL`Операции перетаскивания прокрутки о или происходит в целевой базе данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **DRAGDROP_S_USEDEFAULTCURSORS** Если перетаскивание выполняется, **значение NOERROR** Если это не так.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для предоставления отзывов о что произойдет при перетаскивании на этом этапе. Реализация по умолчанию использует курсоры по умолчанию OLE. Дополнительные сведения об операциях и перетащите с помощью OLE, см. в статье [перетаскивания и Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Дополнительные сведения см. в разделе [IDropSource::GiveFeedback](http://msdn.microsoft.com/library/windows/desktop/ms693723), [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129), и [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onbegindrag"></a>COleDropSource::OnBeginDrag  
 Вызывается методом framework, когда происходит событие, которое может начать операцию перетаскивания, например нажатия левой кнопки мыши.  
  
```  
virtual BOOL OnBeginDrag(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает элемент окна, содержащего выбранные данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если перетаскивание разрешен, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если требуется изменить способ запуска перетаскивания процесса. Реализация по умолчанию захват мыши и остается в режим перетаскивания, пока пользователь не нажимает кнопку мыши влево или вправо или достигает ESC, после чего он отпускает кнопку мыши.  
  
##  <a name="querycontinuedrag"></a>COleDropSource::QueryContinueDrag  
 После начала перетаскивания, эта функция вызывается платформой многократно до отмены или завершения операции перетаскивания.  
  
```  
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed, 
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>Параметры  
 *bEscapePressed*  
 Указывает, была ли нажата клавиша ESC с момента последнего вызова `COleDropSource::QueryContinueDrag`.  
  
 `dwKeyState`  
 Содержит состояние клавиш на клавиатуре. Это сочетание любое количество следующих: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, и **MK_RBUTTON**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **DRAGDROP_S_CANCEL** при нажатии клавиши ESC или правая кнопка или левой кнопки мыши возникает перед перетаскиванием начинается. **DRAGDROP_S_DROP** Если происходит операция перетаскивания. В противном случае `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределение, эту функцию, если вы хотите изменить точку, в которой перетаскивание отменена или drop выполняется.  
  
 Реализация по умолчанию инициирует раскрывающегося или отменяет перетаскивание следующим образом. Он отменяет операцию перетаскивания при нажатии клавиши ESC или правая кнопка мыши. При возникновении левую кнопку мыши после перетаскивания инициирует операцию перетаскивания. В противном случае возвращается `S_OK` и выполняет никакие дополнительные операции.  
  
 Поскольку эта функция вызывается часто, его необходимо оптимизировать максимальной.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




