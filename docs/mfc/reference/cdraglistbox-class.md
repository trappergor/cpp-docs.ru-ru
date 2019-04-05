---
title: Класс CDragListBox
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
ms.openlocfilehash: d8afc5b14f5f52ca7a4d28a3d3c3c5440b7c819f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781592"
---
# <a name="cdraglistbox-class"></a>Класс CDragListBox

Помимо предоставления функциональных возможностей списка Windows, `CDragListBox` класс позволяет пользователю перемещать элементы списка, такие как имена файлов, в поле со списком.

## <a name="syntax"></a>Синтаксис

```
class CDragListBox : public CListBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CDragListBox::CDragListBox](#cdraglistbox)|Создает объект `CDragListBox`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CDragListBox::BeginDrag](#begindrag)|Вызывается платформой, когда начинается операция перетаскивания.|
|[CDragListBox::CancelDrag](#canceldrag)|Вызывается платформой, когда операция перетаскивания была отменена.|
|[CDragListBox::Dragging](#dragging)|Вызывается платформой при выполнении операции перетаскивания.|
|[CDragListBox::DrawInsert](#drawinsert)|Рисует направляющая окна списка перетаскивания.|
|[CDragListBox::Dropped](#dropped)|Вызвано структурой после элемента был удален.|
|[CDragListBox::ItemFromPt](#itemfrompt)|Возвращает координаты перетаскиваемый элемент.|

## <a name="remarks"></a>Примечания

Списки с множественным благодаря этой возможности позволяют упорядочить элементы в списке любым способом, наиболее полезным для них. По умолчанию поле со списком будет переместить элемент в новое расположение, в списке. Тем не менее `CDragListBox` объектов можно настроить для копирования элементов, а не их перемещения.

Окно списка связанных с `CDragListBox` класс не должен иметь LBS_SORT или LBS_MULTIPLESELECT стиль. Описание стили окна списка, см. в разделе [стили списков](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).

Чтобы использовать перетащите список в существующем диалоговом окне приложения, добавьте элемент управления списком для шаблона диалогового окна с помощью редактора диалоговых окон, а затем назначьте переменную-член (категории `Control` и тип переменной `CDragListBox`) соответствующее поле со списком Управление шаблона диалогового окна.

Дополнительные сведения о назначении элементы управления для переменных-членов см. в разделе [ярлык для определения переменных-членов для элементов управления диалоговых окон](../../windows/defining-member-variables-for-dialog-controls.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="begindrag"></a>  CDragListBox::BeginDrag

Вызывается структурой при возникновении события, может начать операцию перетаскивания, например нажатие левой кнопки мыши.

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты перетаскиваемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если перетаскивание может, в противном случае 0.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, если вы хотите контролировать, что происходит, когда начинается операция перетаскивания. Реализация по умолчанию захватывает мышь и остается в режиме перетаскивания, пока пользователь нажимает кнопку мыши влево или вправо или нажмет клавишу ESC, после чего отменяется операция перетаскивания.

##  <a name="canceldrag"></a>  CDragListBox::CancelDrag

Вызывается платформой, когда операция перетаскивания была отменена.

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты перетаскиваемый элемент.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для обработки всей специальной обработки для элемента управления поля списка.

##  <a name="cdraglistbox"></a>  CDragListBox::CDragListBox

Создает объект `CDragListBox`.

```
CDragListBox();
```

##  <a name="dragging"></a>  CDragListBox::Dragging

Вызывается платформой, когда перетаскиваемый элемент списка в `CDragListBox` объекта.

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий x и y экранные координаты курсора.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса курсора для отображения. Возможны следующие значения:

- DL_COPYCURSOR указывает, что элемент будет скопирован.

- DL_MOVECURSOR указывает, что элемент перемещается.

- DL_STOPCURSOR указывает, что текущего конечного места перетаскивания не допускается.

### <a name="remarks"></a>Примечания

Поведение по умолчанию возвращает DL_MOVECURSOR. Переопределите эту функцию, если вы хотите предоставлять дополнительные функциональные возможности.

##  <a name="drawinsert"></a>  CDragListBox::DrawInsert

Вызывается платформой для изображения направляющих перед элементом с указанным индексом.

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
Отсчитываемый от нуля индекс курсора.

### <a name="remarks"></a>Примечания

Значение - 1 очищает направляющая. Переопределите эту функцию для изменения внешнего вида и поведения направляющая.

##  <a name="dropped"></a>  CDragListBox::Dropped

Вызывается платформой при удалении элемента в пределах `CDragListBox` объекта.

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>Параметры

*nSrcIndex*<br/>
Указывает отсчитываемый от нуля индекс удаленной строки.

*pt*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) , содержащий координаты узла размещения.

### <a name="remarks"></a>Примечания

Поведение по умолчанию копирует элемента списка и его данных в новое расположение, а затем удаляет исходный элемент. Переопределите эту функцию для настройки поведения по умолчанию, таких как включение копии элементов списка для переноса в другие расположения в пределах списка.

##  <a name="itemfrompt"></a>  CDragListBox::ItemFromPt

Вызов этой функции для получения отсчитываемый от нуля индекс элемента списка, расположенный *pt*.

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Объект [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) объект, содержащий координаты точки в поле со списком.

*bAutoScroll*<br/>
Ненулевое значение, если разрешена прокрутка, в противном случае 0.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента списка перетаскивания.

## <a name="see-also"></a>См. также

[Пример MFC TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox-класс](../../mfc/reference/clistbox-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CListBox-класс](../../mfc/reference/clistbox-class.md)
