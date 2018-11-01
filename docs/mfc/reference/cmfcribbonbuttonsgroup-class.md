---
title: Класс CMFCRibbonButtonsGroup
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
ms.openlocfilehash: 0babda16ee29671a584599699b459062c22406e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592743"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>Класс CMFCRibbonButtonsGroup

`CMFCRibbonButtonsGroup` Класс позволяет организовать набор кнопок ленты в группе. Все кнопки в группе располагаются непосредственно рядом с друг с другом по горизонтали и заключены в границу.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Создает объект `CMFCRibbonButtonsGroup`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Добавляет кнопку в группу.|
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Добавляет список кнопок в группу.|
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Возвращает указатель на кнопку, расположенную по указанному индексу.|
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Возвращает число кнопок в группе.|
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Возвращает размер изображения, обычных изображений в группе ленты (переопределяет [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты (переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Отчеты ли `CMFCRibbonButtonsGroup` объект содержит изображениям значков панели инструментов.|
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Рисует соответствующий образ для указанной кнопки, в зависимости от кнопки, является ли normal, выделенные или отключено.|
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Удаляет все кнопки из `CMFCRibbonButtonsGroup` объекта.|
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Назначает образы в группу.|
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Задает родительский `CMFCRibbonCategory` из `CMFCRibbonButtonsGroup` объект и все кнопки в нем (переопределяет [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|

## <a name="remarks"></a>Примечания

Группы является производным от [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) и может обрабатываться как единая сущность. Группы можно разместить на любой панели или во всплывающее меню.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonButtonsGroup` . В примере показано `CMFCRibbonButtonsGroup` объекта, назначать изображения для группы кнопок ленты и добавьте кнопку в группу кнопок ленты. Этот фрагмент кода входит в состав [примера Draw Client](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonbuttonsgroup.h

##  <a name="addbutton"></a>  CMFCRibbonButtonsGroup::AddButton

Добавляет кнопку в группу.

```
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
[in] Указатель на кнопку для добавления.

##  <a name="addbuttons"></a>  CMFCRibbonButtonsGroup::AddButtons

Добавляет список кнопок в группу.

```
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>Параметры

*lstButtons*<br/>
[in] Список указателей на кнопок, которые вы хотите добавить.

##  <a name="cmfcribbonbuttonsgroup"></a>  CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup

Создает объект `CMFCRibbonButtonsGroup`.

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
[in] Указывает кнопку, чтобы добавить только что созданный `CMFCRibbonButtonsGroup` объекта.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getbutton"></a>  CMFCRibbonButtonsGroup::GetButton

Возвращает указатель на кнопку, расположенную по указанному индексу.

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>Параметры

*i*<br/>
[in] Отсчитываемый от нуля индекс кнопки для возврата.

### <a name="return-value"></a>Возвращаемое значение

Указатель на кнопку, расположенную по указанному индексу. Значение NULL, если указанный индекс находится вне диапазона.

### <a name="remarks"></a>Примечания

##  <a name="getcount"></a>  CMFCRibbonButtonsGroup::GetCount

Возвращает число кнопок в группе.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число кнопок в группе.

##  <a name="getimagesize"></a>  CMFCRibbonButtonsGroup::GetImageSize

Извлекает размер образа источника, из защищенных `CMFCToolBarImages` член `m_Images`.

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает исходный размер образа изображениям значков панели инструментов, если они присутствуют, или объект `CSize` нулевым, если это не так.

### <a name="remarks"></a>Примечания

##  <a name="getregularsize"></a>  CMFCRibbonButtonsGroup::GetRegularSize

Извлекает максимально возможный размер элемента группы ленты.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст устройства группы ленты.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="hasimages"></a>  CMFCRibbonButtonsGroup::HasImages

Отчеты ли `CMFCRibbonButtonsGroup` объект содержит изображениям значков панели инструментов.

```
BOOL HasImages() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если защищенный `CMFCToolBarImages` член `m_Images` содержит изображения, или значение FALSE, если не.

### <a name="remarks"></a>Примечания

##  <a name="ondrawimage"></a>  CMFCRibbonButtonsGroup::OnDrawImage

Рисует соответствующий образ для указанной кнопки, в зависимости от кнопки, является ли normal, выделенные или отключено.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Указатель на контекст `CMFCRibbonButtonsGroup` объекта.

*rectImage*<br/>
[in] Прямоугольник, в которой рисуется изображение.

*pButton*<br/>
[in] Кнопка, для которого должно быть нарисовано изображение.

*nImageIndex*<br/>
[in] Индекс изображения для рисования на кнопке (в один из массивов три изображения для кнопок normal, выделенные или отключено).

### <a name="remarks"></a>Примечания

##  <a name="removeall"></a>  CMFCRibbonButtonsGroup::RemoveAll

Удаляет все кнопки из `CMFCRibbonButtonsGroup` объекта.

```
void RemoveAll();
```

### <a name="remarks"></a>Примечания

##  <a name="setimages"></a>  CMFCRibbonButtonsGroup::SetImages

Назначает образы группы кнопок ленты.

```
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>Параметры

*pImages*<br/>
[in] Обычных образов.

*pHotImages*<br/>
[in] Наиболее часто используемыми изображениями.

*pDisabledImages*<br/>
[in] Отключенные изображения.

### <a name="remarks"></a>Примечания

Вызовите `SetImages` перед добавлением кнопок в группу. Число изображений должно быть больше или равно числу из кнопок, чтобы добавить в группу.

> [!NOTE]
>  Наиболее часто используемыми изображениями, изображений, отображаемых при наведении указателя мыши на кнопку. Отключенные это образы, отображается, если кнопка отключена.

##  <a name="setparentcategory"></a>  CMFCRibbonButtonsGroup::SetParentCategory

Задает родительский `CMFCRibbonCategory` из `CMFCRibbonButtonsGroup` объекта и всех кнопок в ней.

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>Параметры

*pCategory*<br/>
[in] Указатель на родительской категории, чтобы задать (групп с вкладками в элементы управления ленты, называются категорий).

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
