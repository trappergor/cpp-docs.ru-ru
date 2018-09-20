---
title: Класс CMFCToolBarFontSizeComboBox | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9942f0d9ca4f890965aaf7d05383beae6fa24af9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429452"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>Класс CMFCToolBarFontSizeComboBox

Кнопка панели инструментов, которая содержит поле со списком, позволяющий пользователю выбрать размер шрифта.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Создает объект `CMFCToolBarFontSizeComboBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Возвращает размер шрифта, выбранного в твипах.|
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Заполняет поле со списком всех размеров шрифта, поддерживаемых параметров выбранного шрифта.|
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Задает размер шрифта в твипах.|

## <a name="remarks"></a>Примечания

Можно использовать `CMFCToolBarFontSizeComboBox` объекта вместе с [класс CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) объект, позволяющий пользователю выбрать шрифт и размер шрифта.

Кнопки поля со списком размер шрифта можно добавить на панель инструментов, так же, как добавить кнопку поле со списком шрифта. Дополнительные сведения см. в разделе [класс CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

Когда пользователь выбирает новый шрифт в `CMFCToolBarFontComboBox` объекта, можно заполнить поле со списком размер шрифта поддерживаемых размеров для данного шрифта с помощью [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) метод.

## <a name="example"></a>Пример

Следующий пример демонстрирует использование различных методов `CMFCToolBarFontSizeComboBox` класс для настройки `CMFCToolBarFontSizeComboBox` объекта. В примере показано получение размера шрифта, в твипах между из текстового поля и заполнить все допустимые размеры шрифта, заданного в поле со списком размер шрифта, определяющая размер шрифта в твипах. Этот фрагмент кода входит в состав [примера Word Pad](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbarfontcombobox.h

##  <a name="cmfctoolbarfontsizecombobox"></a>  CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox

Создает объект `CMFCToolBarFontSizeComboBox`.

```
CMFCToolBarFontSizeComboBox();
```

##  <a name="gettwipsize"></a>  CMFCToolBarFontSizeComboBox::GetTwipSize

Получает размер шрифта, в твипах между из текстового поля со списком размер шрифта.

```
int GetTwipSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение является положительным, это размер шрифта в твипах. Он имеет значение 1, если текстовое поле в поле со списком будет пустым. Это -2, если произошла ошибка.

##  <a name="rebuildfontsizes"></a>  CMFCToolBarFontSizeComboBox::RebuildFontSizes

Заполняет поле со списком размер шрифта все допустимые размеры заданного шрифта.

```
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>Параметры

*strFontName*<br/>
[in] Задает имя шрифта.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, если вы хотите синхронизировать между выделение в поле со списком шрифтов и поле со списком размер шрифта, такие как [класс CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

##  <a name="settwipsize"></a>  CMFCToolBarFontSizeComboBox::SetTwipSize

Округляет указанный размер (в твипах) до ближайшего размера в точках и затем задает выбранный размер в поле со списком по этому значению.

```
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>Параметры

*nSize*<br/>
[in] Указывает размер шрифта (в твипах) для задания.

### <a name="remarks"></a>Примечания

Предыдущий размер шрифтов можно получить позже, вызвав [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) метод.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Класс CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[Класс CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)



