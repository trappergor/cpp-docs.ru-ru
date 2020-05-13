---
title: CmFCImagePaintArea Класс
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
ms.openlocfilehash: cd74d2418bb874553fbbafa637f527a7b84b73bf
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754277"
---
# <a name="cmfcimagepaintarea-class"></a>CmFCImagePaintArea Класс

Предоставляет область изображения, используемую для изменения изображения в диалоговом окне редактора изображений.

## <a name="syntax"></a>Синтаксис

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|Формирует объект `CMFCImagePaintArea`.|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCImagePaintArea::GetMode](#getmode)|Извлекает текущий режим чертежа.|
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Устанавливает изображение биткарты для области изображения.|
|[CMFCImagePaintArea::SetColor](#setcolor)|Устанавливает текущий цвет рисунка.|
|[CMFCImagePaintArea::SetMode](#setmode)|Устанавливает текущий режим рисования.|

### <a name="remarks"></a>Remarks

Данный класс не предназначен для непосредственного использования в коде.

Платформа использует этот класс для отображения области изображения в диалоговом окне редактора изображений. Для получения дополнительной информации о диалоговом окне редактора изображений [см.](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCImagePaintArea` построить объект класса, установить текущий цвет рисунка, установить текущий режим рисования и установить изображение битовой карты для области изображения.

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afximagepaintarea.h

## <a name="cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a>CMFCImagePaintArea::CMFCImagePaintArea

Формирует объект `CMFCImagePaintArea`.

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pParentDlg*|(в) Указатель на диалоговое окно, которое является родителем редактора изображений.|

## <a name="cmfcimagepaintareagetmode"></a><a name="getmode"></a>CMFCImagePaintArea::GetMode

Извлекает текущий режим чертежа.

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [IMAGE_EDIT_MODE,](cmfcimagepaintarea-image-edit-mode-enumeration.md) опознававав режим текущего чертежа.

## <a name="cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a>CMFCImagePaintArea::SetBitmap

Устанавливает изображение биткарты для области изображения.

```cpp
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pBitmap*|(в) Новое изображение биткарты для отображения.|

### <a name="remarks"></a>Remarks

Если *pBitmap* является NULL, этот метод устанавливает размер изменяемой области краски до нуля. В противном случае он устанавливает размер изменяемой области краски в размере предоставленного изображения биткарты.

## <a name="cmfcimagepaintareasetcolor"></a><a name="setcolor"></a>CMFCImagePaintArea::SetColor

Устанавливает текущий цвет рисунка.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*Цвет*|(в) Новый цвет рисунка.|

### <a name="remarks"></a>Remarks

При выборе цвета из панели палитры редактора изображений или цветосборщика, фреймворк называет этот метод обновлением текущего цвета рисунка. Первоначальный цвет рисунка черный (значение COLORREF 0).

Цвет чертежа используется диалоговым ящиком редактора изображений для всех режимов рисования, за исключением IMAGE_EDIT_MODE_COLOR. Для получения дополнительной информации о режимах рисования, см [CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration](cmfcimagepaintarea-image-edit-mode-enumeration.md).

## <a name="cmfcimagepaintareasetmode"></a><a name="setmode"></a>CMFCImagePaintArea::SetMode

Устанавливает текущий режим рисования.

```cpp
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*Режим*|(в) Значение [IMAGE_EDIT_MODE,](cmfcimagepaintarea-image-edit-mode-enumeration.md) опознававав режим текущего чертежа.|

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorEditorДиоредакторКласс](../../mfc/reference/cmfcimageeditordialog-class.md)
