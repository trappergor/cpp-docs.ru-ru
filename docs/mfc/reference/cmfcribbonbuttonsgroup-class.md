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
ms.openlocfilehash: af5919ff2a72fc2aa1eeeb95fc93afbe9e743582
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375276"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>Класс CMFCRibbonButtonsGroup

Класс `CMFCRibbonButtonsGroup` позволяет организовать набор лентки кнопки в группу. Все кнопки в группе располагаются непосредственно рядом с друг с другом по горизонтали и заключены в границу.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Формирует объект `CMFCRibbonButtonsGroup`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::Добавить кнопку](#addbutton)|Добавляет кнопку в группу.|
|[CMFCRibbonButtonsGroup::Добавить кнопки](#addbuttons)|Добавляет список кнопок в группу.|
|[CMFCRibbonButtonsGroup:GetButton](#getbutton)|Возвращает указатель на кнопку, расположенную в указанном индексе.|
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Возвращает количество кнопок в группе.|
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Возвращает размер изображения нормальных изображений в группе лент (переопределяет [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Возвращает регулярный размер элемента ленты (переопределяет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Сообщает, `CMFCRibbonButtonsGroup` содержит ли объект изображения панели инструментов.|
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Рисует соответствующее изображение для указанной кнопки, в зависимости от того, является ли кнопка нормальной, выделенной или отключенной.|
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Удаляет все кнопки `CMFCRibbonButtonsGroup` с объекта.|
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Присваивает изображения группе.|
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Устанавливает родительский `CMFCRibbonCategory` `CMFCRibbonButtonsGroup` элемент объекта и все кнопки внутри него (переопределяет [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|

## <a name="remarks"></a>Remarks

Группа является производной от [CMFCBaseRibbonи](../../mfc/reference/cmfcribbonbaseelement-class.md) и может манипулировать как единое целое. Вы можете расположить группу на любой панели или всплывающем меню.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonButtonsGroup` . На примере показано, `CMFCRibbonButtonsGroup` как построить объект, назначить изображения группе лентки и добавить кнопку в группу ленточных кнопок. Этот фрагмент кода входит в состав [примера Draw Client](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonbuttonsgroup.h

## <a name="cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a>CMFCRibbonButtonsGroup::Добавить кнопку

Добавляет кнопку в группу.

```
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
(в) Указатель на кнопку для добавления.

## <a name="cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a>CMFCRibbonButtonsGroup::Добавить кнопки

Добавляет список кнопок в группу.

```
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>Параметры

*lstButtons*<br/>
(в) Список указателей на кнопки, которые вы хотите добавить.

## <a name="cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a>CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup

Формирует объект `CMFCRibbonButtonsGroup`.

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
(в) Уфиксируйте кнопку для `CMFCRibbonButtonsGroup` добавления к вновь созданному объекту.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a>CMFCRibbonButtonsGroup:GetButton

Возвращает указатель на кнопку, расположенную в указанном индексе.

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>Параметры

*Я*<br/>
(в) Нулевой индекс кнопки для возврата.

### <a name="return-value"></a>Возвращаемое значение

Указатель на кнопку, расположенную в указанном индексе. NULL, если указанный индекс находится вне диапазона.

### <a name="remarks"></a>Remarks

## <a name="cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a>CMFCRibbonButtonsGroup::GetCount

Возвращает количество кнопок в группе.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество кнопок в группе.

## <a name="cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a>CMFCRibbonButtonsGroup::GetImageSize

Извлекает размер исходного изображения `CMFCToolBarImages` `m_Images`защищенного члена.

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер исходного изображения изображений панели инструментов, `CSize` если таковые имеются, или нулевой, если нет.

### <a name="remarks"></a>Remarks

## <a name="cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonButtonsGroup::GetRegularSize

Извлекает максимально возможный размер элемента ленточной группы.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства ленточной группы.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

## <a name="cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a>CMFCRibbonButtonsGroup::HasImages

Сообщает, `CMFCRibbonButtonsGroup` содержит ли объект изображения панели инструментов.

```
BOOL HasImages() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, `CMFCToolBarImages` если `m_Images` защищенный член содержит какие-либо изображения, или FALSE, если нет.

### <a name="remarks"></a>Remarks

## <a name="cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a>CMFCRibbonButtonsGroup::OnDrawImage

Рисует соответствующее изображение для указанной кнопки, в зависимости от того, является ли кнопка нормальной, выделенной или отключенной.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства `CMFCRibbonButtonsGroup` объекта.

*rectImage*<br/>
(в) Прямоугольник, внутри которого можно нарисовать изображение.

*pButton*<br/>
(в) Кнопка, для которой можно нарисовать изображение.

*nImageIndex*<br/>
(в) Индекс изображения нарисовать на кнопке (в одном из трех массивов изображений для обычных, выделенных или отключенных кнопок).

### <a name="remarks"></a>Remarks

## <a name="cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a>CMFCRibbonButtonsGroup::RemoveAll

Удаляет все кнопки `CMFCRibbonButtonsGroup` с объекта.

```
void RemoveAll();
```

### <a name="remarks"></a>Remarks

## <a name="cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a>CMFCRibbonButtonsGroup::SetImages

Присваивает изображения группе лентовых кнопок.

```
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>Параметры

*pImages*<br/>
(в) Регулярные изображения.

*pHotImages*<br/>
(в) Горячие изображения.

*pDisabledImages*<br/>
(в) Изображения инвалидов.

### <a name="remarks"></a>Remarks

Позвоните `SetImages` перед добавлением кнопок в группу. Количество изображений должно быть больше или равно количеству кнопок, которые будут добавлены в группу.

> [!NOTE]
> Горячие изображения изображения, которые отображаются, когда пользователь парит над кнопкой. Изображения инвалидов — это изображения, отображаемые при отключении кнопки.

## <a name="cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a>CMFCRibbonButtonsGroup::SetParentCategory

Устанавливает родительский `CMFCRibbonCategory` `CMFCRibbonButtonsGroup` объект и все кнопки внутри него.

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>Параметры

*pКатегория*<br/>
(в) Указатель на родительскую категорию для установки (группы вкладок в элементаре управления лентой называются категориями).

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
