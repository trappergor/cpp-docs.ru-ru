---
title: Класс Кдраглистбокс
ms.date: 11/04/2016
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
ms.openlocfilehash: b260d3a88fc8c3f2d341005c1e47cfd9ab668e1e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500353"
---
# <a name="cdraglistbox-class"></a>Класс Кдраглистбокс

Помимо предоставления функциональных возможностей окна списка Windows, `CDragListBox` класс позволяет пользователю перемещать элементы списка, например имена файлов, в поле со списком.

## <a name="syntax"></a>Синтаксис

```
class CDragListBox : public CListBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кдраглистбокс:: Кдраглистбокс](#cdraglistbox)|Формирует объект `CDragListBox`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кдраглистбокс:: Бегиндраг](#begindrag)|Вызывается платформой при запуске операции перетаскивания.|
|[Кдраглистбокс:: Канцелдраг](#canceldrag)|Вызывается структурой при отмене операции перетаскивания.|
|[Кдраглистбокс::D раггинг](#dragging)|Вызывается платформой во время операции перетаскивания.|
|[Кдраглистбокс::D Равинсерт](#drawinsert)|Выводит направляющую в поле со списком перетаскивания.|
|[Кдраглистбокс::D роппед](#dropped)|Вызвано структурой после удаления элемента.|
|[Кдраглистбокс:: Итемфромпт](#itemfrompt)|Возвращает координаты перетаскиваемого элемента.|

## <a name="remarks"></a>Remarks

Списки с такой возможностью позволяют пользователям упорядочивать элементы в списке любым способом, наиболее удобным для них. По умолчанию элемент списка будет перемещен в новое место в списке. Однако `CDragListBox` объекты можно настроить для копирования элементов, а не для их перемещения.

Элемент управления "список", связанный с `CDragListBox` классом, не должен иметь LBS_SORT или стиль LBS_MULTIPLESELECT. Описание стилей списков см. в разделе [стили списков](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).

Чтобы использовать поле со списком перетаскивания в существующем диалоговом окне приложения, добавьте элемент управления "список" в шаблон диалогового окна с помощью редактора диалоговых окон, а затем назначьте переменную-член (категории `Control` и тип переменной `CDragListBox` ), соответствующую элементу управления списка в шаблоне диалогового окна.

Дополнительные сведения о назначении элементов управления переменным элементов см. в разделе [Определение переменных членов для элементов управления диалогового окна](../../windows/adding-editing-or-deleting-controls.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cdraglistboxbegindrag"></a><a name="begindrag"></a> Кдраглистбокс:: Бегиндраг

Вызывается платформой при возникновении события, которое может начать операцию перетаскивания, например нажатие левой кнопки мыши.

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты перетаскиваемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если перетаскивание запрещено; в противном случае — 0.

### <a name="remarks"></a>Remarks

Переопределите эту функцию, если необходимо контролировать, что происходит при начале операции перетаскивания. Реализация по умолчанию захватывает мышь и остается в режиме перетаскивания, пока пользователь не щелкнет левую или правую кнопку мыши или не нажмет клавишу ESC, когда операция перетаскивания отменяется.

## <a name="cdraglistboxcanceldrag"></a><a name="canceldrag"></a> Кдраглистбокс:: Канцелдраг

Вызывается структурой при отмене операции перетаскивания.

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты перетаскиваемого элемента.

### <a name="remarks"></a>Remarks

Переопределите эту функцию для обработки любой специальной обработки элемента управления "список".

## <a name="cdraglistboxcdraglistbox"></a><a name="cdraglistbox"></a> Кдраглистбокс:: Кдраглистбокс

Формирует объект `CDragListBox`.

```
CDragListBox();
```

## <a name="cdraglistboxdragging"></a><a name="dragging"></a> Кдраглистбокс::D раггинг

Вызывается структурой при перетаскивании элемента списка в пределах `CDragListBox` объекта.

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий экранные координаты x и y курсора.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса отображаемого курсора. Возможны следующие значения:

- DL_COPYCURSOR указывает, что элемент будет скопирован.

- DL_MOVECURSOR указывает, что элемент будет перемещен.

- DL_STOPCURSOR указывает, что текущая цель перетаскивания неприемлема.

### <a name="remarks"></a>Remarks

Поведение по умолчанию возвращает DL_MOVECURSOR. Переопределите эту функцию, если требуется предоставить дополнительные функциональные возможности.

## <a name="cdraglistboxdrawinsert"></a><a name="drawinsert"></a> Кдраглистбокс::D Равинсерт

Вызвано структурой для рисования направляющей перед элементом с указанным индексом.

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>Параметры

*нитем*<br/>
Отсчитываемый от нуля индекс точки вставки.

### <a name="remarks"></a>Remarks

Значение-1 очищает направляющую вставки. Переопределите эту функцию, чтобы изменить внешний вид или поведение направляющей вставки.

## <a name="cdraglistboxdropped"></a><a name="dropped"></a> Кдраглистбокс::D роппед

Вызывается структурой при удалении элемента внутри `CDragListBox` объекта.

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>Параметры

*нсрЦиндекс*<br/>
Указывает отсчитываемый от нуля индекс удаленной строки.

*пт*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты узла сброса.

### <a name="remarks"></a>Remarks

Поведение по умолчанию копирует элемент списка и его данные в новое расположение, а затем удаляет исходный элемент. Переопределите эту функцию, чтобы настроить поведение по умолчанию, например Разрешить перетаскивание копий элементов списка в другие расположения в списке.

## <a name="cdraglistboxitemfrompt"></a><a name="itemfrompt"></a> Кдраглистбокс:: Итемфромпт

Вызовите эту функцию, чтобы получить Отсчитываемый от нуля индекс элемента списка, находящегося в *PT*.

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>Параметры

*пт*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты точки в списке.

*баутоскролл*<br/>
Ненулевое значение, если прокрутка разрешена; в противном случае 0.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента списка перетаскивания.

## <a name="see-also"></a>См. также раздел

[Пример ТСТКОН для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CListBox](../../mfc/reference/clistbox-class.md)
