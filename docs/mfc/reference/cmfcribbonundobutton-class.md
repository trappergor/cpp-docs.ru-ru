---
title: Класс CMFCRibbonUndoButton
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
helpviewer_keywords:
- CMFCRibbonUndoButton [MFC], CMFCRibbonUndoButton
- CMFCRibbonUndoButton [MFC], AddUndoAction
- CMFCRibbonUndoButton [MFC], CleanUpUndoList
- CMFCRibbonUndoButton [MFC], GetActionNumber
- CMFCRibbonUndoButton [MFC], HasMenu
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
ms.openlocfilehash: cd657ac035c004e7aa9bfcd2f6dbd2f3c90da80c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410097"
---
# <a name="cmfcribbonundobutton-class"></a>Класс CMFCRibbonUndoButton

`CMFCRibbonUndoButton` Класс реализует кнопку раскрывающегося списка, содержащего последние команды пользователя. Пользователи могут выбрать один или несколько последних команд из раскрывающегося списка, чтобы повторить или отменить их.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonUndoButton : public CMFCRibbonGallery
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|Создает новый `CMFCRibbonUndoButton` объекта, используя идентификатор команды, указанной вами, текстовую метку и изображений из списка изображений родительского объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|Добавляет новое действие в список действий.|
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|Очищает список действий, представляющий стрелку раскрывающегося списка.|
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|Определяет количество элементов, которые пользователь выбрал в раскрывающемся списке.|
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|Указывает, содержит ли объект меню.|

## <a name="remarks"></a>Примечания

`CMFCRibbonUndoButton` Класс использует стек для представления раскрывающегося списка.

## <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCRibbonUndoButton` класса и добавьте новое действие в список действий. Этот фрагмент кода является частью [пример мини-приложения ленты](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonundobutton.h

##  <a name="addundoaction"></a>  CMFCRibbonUndoButton::AddUndoAction

Добавляет новое действие в список действий.

```
void AddUndoAction(LPCTSTR lpszLabel);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
[in] Метка действия, которое будет отображаться в раскрывающемся списке.

##  <a name="cleanupundolist"></a>  CMFCRibbonUndoButton::CleanUpUndoList

Очищает список действий, представляющий стрелку раскрывающегося списка.

```
void CleanUpUndoList();
```

##  <a name="cmfcribbonundobutton"></a>  CMFCRibbonUndoButton::CMFCRibbonUndoButton

Создает новый `CMFCRibbonUndoButton` объекта, используя идентификатор команды, указанной вами, текстовую метку и изображений из списка изображений родительского объекта.

```
CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex=-1,
    int nLargeImageIndex=-1);

CMFCRibbonUndoButton(
    UINT nID,
    LPCTSTR lpszText,
    HICON hIcon);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
[in] Указывает идентификатор команды.

*lpszText*<br/>
[in] Задает текстовую подпись кнопки.

*nSmallImageIndex*<br/>
[in] Отсчитываемый от нуля индекс в списке изображений родительского объекта для небольшое изображение кнопки.

*nLargeImageIndex*<br/>
[in] Отсчитываемый от нуля индекс в списке изображений родительского объекта для большого изображения кнопки.

*hIcon*<br/>
[in] Дескриптор значка, который можно использовать в качестве изображения кнопки.

##  <a name="getactionnumber"></a>  CMFCRibbonUndoButton::GetActionNumber

Определяет количество элементов, которые пользователь выбрал в раскрывающемся списке.

```
int GetActionNumber() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, которые пользователь выбрал.

##  <a name="hasmenu"></a>  CMFCRibbonUndoButton::HasMenu

Указывает, содержит ли объект меню.

```
virtual BOOL HasMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
