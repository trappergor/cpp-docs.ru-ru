---
title: Класс CMFCRibbonComboBox
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
ms.openlocfilehash: 89007ea3eb7fd0aef28caadf439195b4090a05d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237342"
---
# <a name="cmfcribboncombobox-class"></a>Класс CMFCRibbonComboBox

`CMFCRibbonComboBox` Класс реализует поле со списком, можно добавить на панель ленты, панель ленты или во всплывающее меню ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|Создает объект CMFCRibbonComboBox.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonComboBox::AddItem](#additem)|Добавляет уникальный элемент в поле со списком.|
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Удаляет указанный элемент из списка.|
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Указывает ли поле со списком можно изменить размер, он станет.|
|[CMFCRibbonComboBox::FindItem](#finditem)|Возвращает индекс первого элемента в списке, которая совпадает с указанной строкой.|
|[CMFCRibbonComboBox::GetCount](#getcount)|Возвращает число элементов в поле со списком.|
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Получает индекс выбранного элемента в поле со списком.|
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Получает высоту окна списка, когда раскрыл поле со списком.|
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Возвращает размер поля со списком, показанной в промежуточный режим.|
|[CMFCRibbonComboBox::GetItem](#getitem)|Возвращает строку, связанную с элементом с указанным индексом в списке.|
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Возвращает данные, связанные с элемента с указанным индексом в списке.|
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Указывает, содержит ли элемент управления поля редактирования.|
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Указывает, можно ли изменять поле со списком.|
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Вызывается платформой, когда пользователь выбирает элемент в списке.|
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Удаляет все элементы из списка и очищает поля ввода.|
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Выбирает элемент в поле со списком.|
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Задает высоту элемента поле со списком при его удалении.|

## <a name="remarks"></a>Примечания

Поле со списком на ленте на состоит из поле со списком, в сочетании со статической метки или метку, которая может быть изменено пользователем. Требуется указать тип при создании поле со списком на ленте.

## <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCRibbonComboBox` класса, добавьте элемент поля со списком, выберите элемент в поле со списком и добавьте поле со списком на панель.

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribboncombobox.h

##  <a name="additem"></a>  CMFCRibbonComboBox::AddItem

Добавляет уникальный элемент в поле со списком.

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Параметры

*lpszItem*<br/>
[in] Строка, добавляемого элемента.

*dwData*<br/>
[in] Данные, связанные с добавляемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс добавленный элемент.

##  <a name="cmfcribboncombobox"></a>  CMFCRibbonComboBox::CMFCRibbonComboBox

Создает объект `CMFCRibbonComboBox`.

```
public:
CMFCRibbonComboBox(
    UINT nID,
    BOOL bHasEditBox=TRUE,
    Int nWidth=-1,
    LPCTSTR lpszLabel=NULL,
    Int nImage=-1);

protected:
CMFCRibbonComboBox();
```

### <a name="parameters"></a>Параметры

*nID*<br/>
[in] Идентификатор поля со списком.

*bHasEditBox*<br/>
[in] Значение TRUE, если поле ввода элемента управления; Значение FALSE в противном случае.

*nWidth*<br/>
[in] Ширина поля со списком в пикселях; или -1 для ширину по умолчанию.

*lpszLabel*<br/>
[in] Метки поля со списком.

*Изображение*<br/>
[in] В поле со списком индекс небольшое изображение.

### <a name="remarks"></a>Примечания

Ширина по умолчанию — 108 пикселей.

##  <a name="deleteitem"></a>  CMFCRibbonComboBox::DeleteItem

Удаляет указанный элемент из списка.

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс удаляемого элемента.

*dwData*<br/>
[in] Данные, связанные с элементом для удаления.

*lpszText*<br/>
[in] Строка удаляемого элемента. При наличии нескольких элементов с этой же строкой, удаляется первый элемент.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанный элемент был удален; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="enabledropdownlistresize"></a>  CMFCRibbonComboBox::EnableDropDownListResize

Указывает ли поле со списком можно изменить размер, он станет.

```
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Значение true, чтобы включить изменение размера; Значение FALSE, чтобы запретить изменение размера.

### <a name="remarks"></a>Примечания

При изменении размера включен, поле со списком изменит размер в соответствии с элементами, которые в нем отображаются.

##  <a name="finditem"></a>  CMFCRibbonComboBox::FindItem

Возвращает индекс первого элемента в списке, которая совпадает с указанной строкой.

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
[in] Строка элемента в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс элемента; или -1, если элемент не найден.

### <a name="remarks"></a>Примечания

##  <a name="getcount"></a>  CMFCRibbonComboBox::GetCount

Возвращает число элементов в поле со списком.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в поле со списком, или 0, если поле со списком не содержит элементов.

### <a name="remarks"></a>Примечания

##  <a name="getcursel"></a>  CMFCRibbonComboBox::GetCurSel

Получает индекс выбранного элемента в поле со списком.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Возвращаемое значение

Отсчитываемый от нуля индекс выбранного элемента в списке; или -1, если элемент не выбран.

##  <a name="getdropdownheight"></a>  CMFCRibbonComboBox::GetDropDownHeight

Получает высоту окна списка, когда раскрыл поле со списком.

```
int GetDropDownHeight();
```

### <a name="return-value"></a>Возвращаемое значение

Высота в пикселях поле со списком.

### <a name="remarks"></a>Примечания

##  <a name="getintermediatesize"></a>  CMFCRibbonComboBox::GetIntermediateSize

Возвращает размер поля со списком, показанной в промежуточный режим.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства для поля со списком.

### <a name="return-value"></a>Возвращаемое значение

Размер поля со списком.

### <a name="remarks"></a>Примечания

Возвращаемый размер зависит от размера поля со списком при его отображении изображений небольшого размера.

##  <a name="getitem"></a>  CMFCRibbonComboBox::GetItem

Возвращает строку, связанную с элементом с указанным индексом в списке.

```
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку, которая связана с элементом; в противном случае — значение NULL, если параметр индекса недопустим, или параметр индекса равно -1 и отсутствует элемент, выбранный в поле со списком.

### <a name="remarks"></a>Примечания

##  <a name="getitemdata"></a>  CMFCRibbonComboBox::GetItemData

Возвращает данные, связанные с элемента с указанным индексом в списке.

```
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

Данные, связанные с элементом; или 0, если элемент не существует или если параметр индекса равно -1, и отсутствует элемент, выбранный в поле со списком.

##  <a name="haseditbox"></a>  CMFCRibbonComboBox::HasEditBox

Указывает, содержит ли элемент управления поля редактирования.

```
BOOL HasEditBox() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если элемент управления содержит поле ввода; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="isresizedropdownlist"></a>  CMFCRibbonComboBox::IsResizeDropDownList

Указывает, можно ли изменять поле со списком.

```
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если поле со списком может быть изменен; в противном случае — значение FALSE. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)

### <a name="remarks"></a>Примечания

Вы можете включить изменение размера поля списка с помощью [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) метод.

##  <a name="onselectitem"></a>  CMFCRibbonComboBox::OnSelectItem

Вызывается платформой, когда пользователь выбирает элемент в списке.

```
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
[in] Индекс выбранного элемента.

### <a name="remarks"></a>Примечания

Переопределите этот метод, если необходимо обработать Выбор ввода пользователя.

##  <a name="removeallitems"></a>  CMFCRibbonComboBox::RemoveAllItems

Удаляет все элементы из списка и очищает поля ввода.

```
void RemoveAllItems();
```

### <a name="remarks"></a>Примечания

##  <a name="selectitem"></a>  CMFCRibbonComboBox::SelectItem

Выбирает элемент в поле со списком.

```
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
[in] Отсчитываемый от нуля индекс элемента в поле со списком.

*dwData*<br/>
[in] Данные, связанные с элементом в поле со списком.

*lpszText*<br/>
[in] Строка элемента в поле со списком.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="setdropdownheight"></a>  CMFCRibbonComboBox::SetDropDownHeight

Задает высоту элемента поле со списком при его удалении.

```
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Параметры

*nHeight*<br/>
[in] Высота в пикселях поле со списком.

### <a name="remarks"></a>Примечания

Высота по умолчанию — 150 пикселей.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)
