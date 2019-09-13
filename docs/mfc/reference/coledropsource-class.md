---
title: Класс Коледропсаурце
ms.date: 11/04/2016
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
ms.openlocfilehash: 3a1e27ca6c1019eb8716194b3b7711238d015d6d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503999"
---
# <a name="coledropsource-class"></a>Класс Коледропсаурце

Позволяет перетаскивать данные в целевой объект перетаскивания.

## <a name="syntax"></a>Синтаксис

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Коледропсаурце:: Коледропсаурце](#coledropsource)|Создает объект `COleDropSource`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Коледропсаурце:: GiveFeedback](#givefeedback)|Изменяет курсор во время операции перетаскивания.|
|[Коледропсаурце:: Онбегиндраг](#onbegindrag)|Обрабатывает захват мыши во время операции перетаскивания.|
|[Коледропсаурце:: QueryContinueDrag](#querycontinuedrag)|Проверяет, следует ли продолжать перетаскивание.|

## <a name="remarks"></a>Примечания

Класс [коледроптаржет](../../mfc/reference/coledroptarget-class.md) обрабатывает принимающую часть операции перетаскивания. `COleDropSource` Объект отвечает за определение времени начала операции перетаскивания, предоставление обратной связи во время операции перетаскивания и определение момента завершения операции перетаскивания.

Чтобы использовать `COleDropSource` объект, просто вызовите конструктор. Это упрощает процесс определения событий, например щелчка мышью, начала операции перетаскивания с помощью [COleDataSource::D одрагдроп](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::D одрагдроп](../../mfc/reference/coleclientitem-class.md#dodragdrop)или [COleServerItem::D одрагдроп](../../mfc/reference/coleserveritem-class.md#dodragdrop) . Эти функции будут создавать `COleDropSource` объект. Может потребоваться изменить поведение `COleDropSource` по умолчанию для переопределяемых функций. Эти функции элементов будут вызываться в нужное время платформой.

Дополнительные сведения об операциях перетаскивания с помощью OLE см. в статье перетаскивание [(OLE)](../../mfc/drag-and-drop-ole.md).

Дополнительные сведения см. в разделе [идропсаурце](/windows/win32/api/oleidl/nn-oleidl-idropsource) в Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле. h

##  <a name="coledropsource"></a>Коледропсаурце:: Коледропсаурце

Создает объект `COleDropSource`.

```
COleDropSource();
```

##  <a name="givefeedback"></a>Коледропсаурце:: GiveFeedback

Вызвано структурой после вызова [коледроптаржет:: OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) или [Коледроптаржет::D ражентер](../../mfc/reference/coledroptarget-class.md#ondragenter).

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>Параметры

*дропеффект*<br/>
Результат, который необходимо отобразить пользователю, обычно указывающий, что произойдет, если в данный момент на выбранном этапе было выполнено перетаскивание. Как правило, это значение, возвращаемое последним вызовом [CView:: OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) или [CView:: OnDragOver](../../mfc/reference/cview-class.md#ondragover). Это может быть одно или несколько из следующих:

- DROPEFFECT_NONE удаление запрещено.

- DROPEFFECT_COPY будет выполнена операция копирования.

- DROPEFFECT_MOVE операция перемещения будет выполнена.

- DROPEFFECT_LINK связь из удаленных данных с исходными данными.

- DROPEFFECT_SCROLL операция перетаскивания будет выполнена или в целевом объекте.

### <a name="return-value"></a>Возвращаемое значение

Возвращает DRAGDROP_S_USEDEFAULTCURSORS, если выполняется перетаскивание, в противном случае — ошибка.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы предоставить пользователю отзыв о том, что произойдет, если в этот момент происходило перетаскивание. Реализация по умолчанию использует курсоры по умолчанию OLE. Дополнительные сведения об операциях перетаскивания с помощью OLE см. в статье перетаскивание [(OLE)](../../mfc/drag-and-drop-ole.md).

Дополнительные сведения см. в разделе [идропсаурце:: GiveFeedback](/windows/win32/api/oleidl/nf-oleidl-idropsource-givefeedback), [интерфейс IDropTarget::D раговер](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover)и [интерфейс idroptarget::D ражентер](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) в Windows SDK.

##  <a name="onbegindrag"></a>Коледропсаурце:: Онбегиндраг

Вызывается платформой при возникновении события, которое может начать операцию перетаскивания, например нажатие левой кнопки мыши.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно, содержащее выбранные данные.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если перетаскивание запрещено; в противном случае — 0.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, если необходимо изменить способ запуска процесса перетаскивания. Реализация по умолчанию захватывает мышь и остается в режиме перетаскивания до тех пор, пока пользователь не нажмет левую или правую кнопку мыши или не нажимает клавишу ESC, при этом она освобождает мышь.

##  <a name="querycontinuedrag"></a>Коледропсаурце:: QueryContinueDrag

После начала перетаскивания эта функция вызывается повторно, пока операция перетаскивания не будет отменена или завершена.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>Параметры

*бескапепрессед*<br/>
Указывает, была ли нажата клавиша ESC с момента последнего вызова `COleDropSource::QueryContinueDrag`.

*двкэйстате*<br/>
Содержит состояние клавиш со модификатором на клавиатуре. Это сочетание любого числа следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

### <a name="return-value"></a>Возвращаемое значение

DRAGDROP_S_CANCEL если нажата клавиша ESC или правая кнопка, то перед началом перетаскивания появляется левая кнопка. DRAGDROP_S_DROP, если должна произойти операция Drop. В противном случае значение S_OK.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, если нужно изменить точку, в которой перетаскивание отменяется, или происходит перетаскивание.

Реализация по умолчанию инициирует перетаскивание или отменяет перетаскивание следующим образом. Она отменяет операцию перетаскивания при нажатии клавиши ESC или щелчка правой кнопки мыши. Она инициирует операцию Drop, когда левая кнопка мыши вызывается после начала перетаскивания. В противном случае он возвращает значение S_OK и не выполняет дальнейших операций.

Так как эта функция вызывается часто, ее следует оптимизировать как можно больше.

## <a name="see-also"></a>См. также

[Пример MFC для примера HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Пример OCLIENT MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
