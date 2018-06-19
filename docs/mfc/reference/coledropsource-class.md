---
title: Класс COleDropSource | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e510811fcaac81aa54699250ef37f48ffe1f40e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374901"
---
# <a name="coledropsource-class"></a>Класс COleDropSource
Позволяет перетаскивать конечное расположение сброса данные.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDropSource::COleDropSource](#coledropsource)|Создает объект `COleDropSource`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDropSource::GiveFeedback](#givefeedback)|Изменение курсора во время операции перетаскивания и вставки.|  
|[COleDropSource::OnBeginDrag](#onbegindrag)|Захват мыши обрабатываются во время операции перетаскивания и вставки.|  
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Проверяет, является ли перетаскивания следует продолжить.|  
  
## <a name="remarks"></a>Примечания  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md) класс обрабатывает принимающей часть операции перетаскивания и вставки. `COleDropSource` Объект отвечает за определение, когда начинается операция перетаскивания, обратная связь во время операции перетаскивания и определение, когда операция перетаскивания завершается.  
  
 Чтобы использовать `COleDropSource` , просто вызовите конструктор. Это упрощает процесс определения, какие события, например, щелчок мыши начать операцию перетаскивания с помощью [COleDataSource::DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), или [ COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) функции. Эти функции создаст `COleDropSource` объект. Может возникнуть необходимость изменить поведение по умолчанию `COleDropSource` переопределяемые функции. Эти функции-члены будут вызываться в нужное время платформой.  
  
 Дополнительные сведения об операциях и перетащите с помощью OLE, см. в статье [перетаскивания и Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Дополнительные сведения см. в разделе [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) в Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coledropsource"></a>  COleDropSource::COleDropSource  
 Создает объект `COleDropSource`.  
  
```  
COleDropSource();
```  
  
##  <a name="givefeedback"></a>  COleDropSource::GiveFeedback  
 Вызывается структурой после вызова [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) или [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).  
  
```  
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```  
  
### <a name="parameters"></a>Параметры  
 `dropEffect`  
 Эффект, который вы хотите отображать для пользователя, как правило, позволяющее определить, что произойдет при перетаскивании на этом этапе с помощью выбранных данных. Как правило, это значение, возвращаемое последний вызов [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) или [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Может быть один или несколько из следующих:  
  
- `DROPEFFECT_NONE` Удаление не допускается.  
  
- `DROPEFFECT_COPY` Операция копирования будет выполнена.  
  
- `DROPEFFECT_MOVE` Выполняется операция перемещения.  
  
- `DROPEFFECT_LINK` Ссылка из перетаскиваемых данных с исходными данными будет установлено.  
  
- `DROPEFFECT_SCROLL` Операции перетаскивания прокрутки о или происходит в целевом объекте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **DRAGDROP_S_USEDEFAULTCURSORS** Если в ходе выполнения, перетащив **значение NOERROR** Если это не так.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для предоставления отзывов пользователей о том, что произойдет при перетаскивании на этом этапе. Реализация по умолчанию использует курсоры по умолчанию OLE. Дополнительные сведения об операциях и перетащите с помощью OLE, см. в статье [перетаскивания и Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Дополнительные сведения см. в разделе [IDropSource::GiveFeedback](http://msdn.microsoft.com/library/windows/desktop/ms693723), [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129), и [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) в Windows SDK.  
  
##  <a name="onbegindrag"></a>  COleDropSource::OnBeginDrag  
 Вызывается методом framework, когда происходит событие, которое может начать операцию перетаскивания, например нажатие левой кнопки мыши.  
  
```  
virtual BOOL OnBeginDrag(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает для окна, содержащего выбранные данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если перетаскивание разрешен, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите изменить способ запуска перетаскивания процесса. Реализация по умолчанию захватывает мышь и остается в режиме перетаскивания, пока пользователь нажимает кнопку мыши влево или вправо или достигает ESC, после чего он отпускает кнопку мыши.  
  
##  <a name="querycontinuedrag"></a>  COleDropSource::QueryContinueDrag  
 После начала перетаскивания, эта функция вызывается платформой несколько раз до отмены или выполнить операции перетаскивания.  
  
```  
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed, 
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>Параметры  
 *bEscapePressed*  
 Указывает, была ли нажата клавиша ESC с момента последнего вызова `COleDropSource::QueryContinueDrag`.  
  
 `dwKeyState`  
 Содержит состояние клавиш на клавиатуре. Это сочетание любое количество следующих: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, и **MK_RBUTTON**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **DRAGDROP_S_CANCEL** при нажатии клавиши ESC или правой кнопки мыши или левой кнопки мыши возникает перед перетаскиванием начинается. **DRAGDROP_S_DROP** Если происходит операция перетаскивания. В противном случае `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределение, эту функцию, если вы хотите изменить точку, в которой перетаскивание отменена или удаление не выполняется.  
  
 Реализация по умолчанию инициирует раскрывающегося или отменяет перетаскивание следующим образом. Он отменяет операцию перетаскивания при нажатии клавиши ESC или правую кнопку мыши. При возникновении левую кнопку мыши после перетаскивания запуска инициирует операцию перетаскивания. В противном случае он возвращает `S_OK` и выполняет дальнейшие операции.  
  
 Поскольку эта функция вызывается часто, ее следует оптимизировать максимальной.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



