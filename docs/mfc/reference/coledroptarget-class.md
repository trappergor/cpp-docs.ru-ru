---
title: Класс Коледроптаржет
ms.date: 11/04/2016
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
ms.openlocfilehash: f5f101ca2c505e1b7c6b50b21af7d5aeef4ae625
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127885"
---
# <a name="coledroptarget-class"></a>Класс Коледроптаржет

Предоставляет механизм взаимодействия между окном и библиотеками OLE.

## <a name="syntax"></a>Синтаксис

```
class COleDropTarget : public CCmdTarget
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Коледроптаржет:: Коледроптаржет](#coledroptarget)|Формирует объект `COleDropTarget`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Коледроптаржет:: OnDragEnter](#ondragenter)|Вызывается, когда курсор впервые попадает в окно.|
|[Коледроптаржет:: OnDragLeave](#ondragleave)|Вызывается, когда курсор перетаскивается из окна.|
|[Коледроптаржет:: OnDragOver](#ondragover)|Вызывается повторно при перетаскивании курсора на окно.|
|[Коледроптаржет:: Ондрагскролл](#ondragscroll)|Вызывается для определения того, перетаскивается ли курсор в область прокрутки окна.|
|[Коледроптаржет:: OnDrop](#ondrop)|Вызывается при перетаскивании данных в окно обработчик по умолчанию.|
|[Коледроптаржет:: Ондропекс](#ondropex)|Вызывается при перетаскивании данных в окно, начальный обработчик.|
|[Коледроптаржет:: Register](#register)|Регистрирует окно в качестве допустимого целевого объекта перетаскивания.|
|[Коледроптаржет:: REVOKE](#revoke)|Приводит к тому, что окно перестанет быть допустимым целевым объектом перетаскивания.|

## <a name="remarks"></a>Remarks

Создание объекта этого класса позволяет окну принимать данные с помощью механизма перетаскивания OLE.

Чтобы окно принимало команды Drop, сначала необходимо создать объект класса `COleDropTarget`, а затем вызвать функцию [Register](#register) с указателем на нужный объект `CWnd` в качестве единственного параметра.

Дополнительные сведения об операциях перетаскивания с помощью OLE см. в разделе [перетаскивание OLE](../../mfc/drag-and-drop-ole.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле. h

##  <a name="coledroptarget"></a>Коледроптаржет:: Коледроптаржет

Конструирует объект класса `COleDropTarget`.

```
COleDropTarget();
```

### <a name="remarks"></a>Remarks

Выполните вызов [Register](#register) , чтобы связать этот объект с окном.

##  <a name="ondragenter"></a>Коледроптаржет:: OnDragEnter

Вызывается структурой при первом перетаскивании курсора в окно.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно, которое вводится курсором.

*pDataObject*<br/>
Указывает на объект данных, содержащий данные, которые могут быть удалены.

*двкэйстате*<br/>
Содержит состояние клавиш модификатора. Это сочетание любого числа следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

*point*<br/>
Содержит текущее расположение курсора в координатах клиента.

### <a name="return-value"></a>Возвращаемое значение

Результат, который может возникнуть при попыток удаления в месте, указанном параметром *Point*. Это может быть одно или несколько из следующих:

- DROPEFFECT_NONE удаление запрещено.

- DROPEFFECT_COPY выполнить операцию копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK будет установлена ссылка из удаленных данных в исходные.

- DROPEFFECT_SCROLL, что операция перетаскивания прокрутки собирается или происходит в целевом объекте.

### <a name="remarks"></a>Remarks

Переопределите эту функцию, чтобы разрешить выполнение операций удаления в окне. Реализация по умолчанию вызывает метод [CView:: OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), который просто возвращает DROPEFFECT_NONE по умолчанию.

Дополнительные сведения см. в разделе [интерфейс IDropTarget::D ражентер](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) в Windows SDK.

##  <a name="ondragleave"></a>Коледроптаржет:: OnDragLeave

Вызывается структурой, когда курсор покидает окно, пока действует операция перетаскивания.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно, в котором находится курсор.

### <a name="remarks"></a>Remarks

Переопределите эту функцию, если требуется специальное поведение, когда операция перетаскивания покидает заданное окно. Реализация по умолчанию этой функции вызывает метод [CView:: OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).

Дополнительные сведения см. в разделе [интерфейс IDropTarget::D раглеаве](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragleave) в Windows SDK.

##  <a name="ondragover"></a>Коледроптаржет:: OnDragOver

Вызывается структурой при перетаскивании курсора над окном.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно, на которое наведен курсор.

*pDataObject*<br/>
Указывает на объект данных, который содержит удаляемые данные.

*двкэйстате*<br/>
Содержит состояние клавиш модификатора. Это сочетание любого числа следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

*point*<br/>
Содержит текущее расположение курсора в координатах клиента.

### <a name="return-value"></a>Возвращаемое значение

Результат, который может возникнуть при попыток удаления в месте, указанном параметром *Point*. Это может быть одно или несколько из следующих:

- DROPEFFECT_NONE удаление запрещено.

- DROPEFFECT_COPY выполнить операцию копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK будет установлена ссылка из удаленных данных в исходные.

- DROPEFFECT_SCROLL указывает на то, что операция перетаскивания будет выполнена или выполняется в целевом объекте.

### <a name="remarks"></a>Remarks

Эта функция должна быть переопределена, чтобы разрешить выполнение операций DROP в окне. Реализация по умолчанию этой функции вызывает метод [CView:: OnDragOver](../../mfc/reference/cview-class.md#ondragover), который по умолчанию возвращает DROPEFFECT_NONE. Поскольку эта функция часто вызывается во время операции перетаскивания, она должна быть максимально оптимизирована.

Дополнительные сведения см. в разделе [интерфейс IDropTarget::D раговер](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

##  <a name="ondragscroll"></a>Коледроптаржет:: Ондрагскролл

Вызывается структурой перед вызовом [OnDragEnter](#ondragenter) или [OnDragOver](#ondragover) для определения того, находится ли *точка* в области прокрутки.

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно, на которое в данный момент находится курсор.

*двкэйстате*<br/>
Содержит состояние клавиш модификатора. Это сочетание любого числа следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.

*point*<br/>
Содержит расположение курсора в пикселях относительно экрана.

### <a name="return-value"></a>Возвращаемое значение

Результат, который может возникнуть при попыток удаления в месте, указанном параметром *Point*. Это может быть одно или несколько из следующих:

- DROPEFFECT_NONE удаление запрещено.

- DROPEFFECT_COPY выполнить операцию копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK будет установлена ссылка из удаленных данных в исходные.

- DROPEFFECT_SCROLL указывает на то, что операция перетаскивания будет выполнена или выполняется в целевом объекте.

### <a name="remarks"></a>Remarks

Переопределите эту функцию, чтобы обеспечить специальное поведение для этого события. Реализация по умолчанию этой функции вызывает метод [CView:: ондрагскролл](../../mfc/reference/cview-class.md#ondragscroll), который возвращает DROPEFFECT_NONE и прокручивает окно при перетаскивании курсора в область прокрутки по умолчанию внутри границы окна.

##  <a name="ondrop"></a>Коледроптаржет:: OnDrop

Вызывается платформой при возникновении операции DROP.

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно, на которое в данный момент находится курсор.

*pDataObject*<br/>
Указывает на объект данных, который содержит удаляемые данные.

*дропеффект*<br/>
Результат, который пользователь выбрал для операции DROP. Это может быть одно или несколько из следующих:

- DROPEFFECT_COPY выполнить операцию копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK будет установлена ссылка из удаленных данных в исходные.

*point*<br/>
Содержит расположение курсора в пикселях относительно экрана.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если удаление выполнено успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

Платформа сначала вызывает [ондропекс](#ondropex). Если функция `OnDropEx` не обрабатывает Drop, платформа вызывает эту функцию члена, `OnDrop`. Как правило, приложение переопределяет [ондропекс](../../mfc/reference/cview-class.md#ondropex) в классе представления, чтобы обрабатывал Перетаскивание правой кнопкой мыши. Как правило, для работы с простым перетаскиванием используется класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) .

Реализация `COleDropTarget::OnDrop` по умолчанию вызывает метод [CView:: OnDrop](../../mfc/reference/cview-class.md#ondrop), который по умолчанию просто возвращает значение false.

Дополнительные сведения см. в разделе [интерфейс IDropTarget::D верхнем](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) в Windows SDK.

##  <a name="ondropex"></a>Коледроптаржет:: Ондропекс

Вызывается платформой при возникновении операции DROP.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно, на которое в данный момент находится курсор.

*pDataObject*<br/>
Указывает на объект данных, который содержит удаляемые данные.

*Событие dropdefault*<br/>
Результат, который пользователь выбрал для операции удаления по умолчанию на основе текущего состояния ключа. Его можно DROPEFFECT_NONE. Эффекты перетаскивания обсуждаются в разделе "Примечания".

*дроплист*<br/>
Список эффектов перетаскивания, поддерживаемых источником перетаскивания. Значения эффектов перетаскивания можно комбинировать с помощью операции побитового или ( **&#124;** ). Эффекты перетаскивания обсуждаются в разделе "Примечания".

*point*<br/>
Содержит расположение курсора в пикселях относительно экрана.

### <a name="return-value"></a>Возвращаемое значение

Результат перетаскивания, полученный в результате попытки удаления в месте, указанном параметром *Point*. Эффекты перетаскивания обсуждаются в разделе "Примечания".

### <a name="remarks"></a>Remarks

Платформа сначала вызывает эту функцию. Если он не обрабатывает Drop, платформа вызывает метод [OnDrop](#ondrop). Как правило, [ондропекс](../../mfc/reference/cview-class.md#ondropex) в классе View переопределяется для поддержки перетаскивания правой кнопкой мыши. Как правило, класс представления [OnDrop](../../mfc/reference/cview-class.md#ondrop) используется для поддержки простого перетаскивания.

Реализация `COleDropTarget::OnDropEx` по умолчанию вызывает [CView:: ондропекс](../../mfc/reference/cview-class.md#ondropex). По умолчанию метод [CView:: ондропекс](../../mfc/reference/cview-class.md#ondropex) просто возвращает фиктивное значение, указывающее, что должна быть вызвана функция-член [OnDrop](#ondrop) .

Эффекты перетаскивания описывают действие, связанное с операцией Drop. См. следующий список эффектов перетаскивания:

- DROPEFFECT_NONE удаление запрещено.

- DROPEFFECT_COPY выполнить операцию копирования.

- DROPEFFECT_MOVE будет выполнена операция перемещения.

- DROPEFFECT_LINK будет установлена ссылка из удаленных данных в исходные.

- DROPEFFECT_SCROLL указывает на то, что операция перетаскивания будет выполнена или выполняется в целевом объекте.

Дополнительные сведения см. в разделе [интерфейс IDropTarget::D верхнем](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) в Windows SDK.

##  <a name="register"></a>Коледроптаржет:: Register

Вызывайте эту функцию для регистрации окна с помощью DLL-библиотек OLE в качестве допустимого целевого объекта перетаскивания.

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно, которое должно быть зарегистрировано в качестве цели перетаскивания.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если регистрация прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

Эта функция должна вызываться для принятия операций удаления.

Дополнительные сведения см. в разделе [регистердрагдроп](/windows/win32/api/ole2/nf-ole2-registerdragdrop) в Windows SDK.

##  <a name="revoke"></a>Коледроптаржет:: REVOKE

Вызовите эту функцию перед удалением любого окна, зарегистрированного в качестве цели перетаскивания, с помощью вызова функции [Register](#register) , чтобы удалить его из списка целевых объектов перетаскивания.

```
virtual void Revoke();
```

### <a name="remarks"></a>Remarks

Эта функция вызывается автоматически из обработчика [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) для зарегистрированного окна, поэтому обычно нет необходимости вызывать эту функцию явным образом.

Дополнительные сведения см. в разделе [ревокедрагдроп](/windows/win32/api/ole2/nf-ole2-revokedragdrop) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Пример MFC для примера HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Пример OCLIENT MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDropSource](../../mfc/reference/coledropsource-class.md)
