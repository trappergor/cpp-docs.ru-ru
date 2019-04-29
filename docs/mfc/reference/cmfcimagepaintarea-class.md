---
title: Класс CMFCImagePaintArea
ms.date: 11/04/2016
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
ms.openlocfilehash: 37d975ace4d144cc6274b49a3406382f0fb300ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374185"
---
# <a name="cmfcimagepaintarea-class"></a>Класс CMFCImagePaintArea

Предоставляет область картинки, которая позволяет изменять образ в диалоговом окне редактора изображений.

## <a name="syntax"></a>Синтаксис

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|name|Описание|
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|Создает объект `CMFCImagePaintArea`.|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|name|Описание|
|[CMFCImagePaintArea::GetMode](#getmode)|Извлекает текущий режим рисования.|
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Задает растровое изображение для области рисунка.|
|[CMFCImagePaintArea::SetColor](#setcolor)|Задает текущий цвет рисования.|
|[CMFCImagePaintArea::SetMode](#setmode)|Задает текущий режим рисования.|

### <a name="remarks"></a>Примечания

Этот класс не предназначен для использования непосредственно из программного кода.

Инфраструктура использует этот класс для отображения области рисунка в диалоговом окне редактора изображений. Дополнительные сведения о диалоговом окне редактора изображений, см. в разделе [класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md).

## <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCImagePaintArea` класса, задайте текущего рисования цвета, задавать текущий режим рисования и задавать растрового изображения для области рисунка.

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afximagepaintarea.h

##  <a name="cmfcimagepaintarea"></a>  CMFCImagePaintArea::CMFCImagePaintArea

Создает объект `CMFCImagePaintArea`.

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pParentDlg*|[in] Указатель на диалоговое окно, которое является родительским для редактора изображений.|

##  <a name="getmode"></a>  CMFCImagePaintArea::GetMode

Извлекает текущий режим рисования.

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

[IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) значение, указывающее текущий режим рисования.

##  <a name="setbitmap"></a>  CMFCImagePaintArea::SetBitmap

Задает растровое изображение для области рисунка.

```
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pBitmap*|[in] Новый растрового изображения для отображения.|

### <a name="remarks"></a>Примечания

Если *pBitmap* имеет значение NULL, этот метод задает размер области рисования, изменяемые в ноль. В противном случае он устанавливает размер области рисования, изменяемые размер предоставленного растрового изображения.

##  <a name="setcolor"></a>  CMFCImagePaintArea::SetColor

Задает текущий цвет рисования.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*color*|[in] Новый цвет рисования.|

### <a name="remarks"></a>Примечания

При выборе цвета в строке палитры изображения редактора или палитра цветов, платформа вызывает этот метод, чтобы обновить текущий цвет рисования. Черный цвет рисования (COLORREF значение 0).

Цвета для всех режимов отображения, за исключением IMAGE_EDIT_MODE_COLOR используется диалоговое окно редактора изображений. Дополнительные сведения о режимы, см. в разделе [перечисление CMFCImagePaintArea::IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md).

##  <a name="setmode"></a>  CMFCImagePaintArea::SetMode

Задает текущий режим рисования.

```
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*mode*|[in] [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) значение, указывающее текущий режим рисования.|

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)
