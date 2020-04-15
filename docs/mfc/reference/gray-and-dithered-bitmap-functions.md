---
title: функции серого цвета и сглаживания точечного рисунка
ms.date: 11/19/2018
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
ms.openlocfilehash: bbc64aad0d65c0430ad23b96f635be8fe2b396e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357043"
---
# <a name="gray-and-dithered-bitmap-functions"></a>функции серого цвета и сглаживания точечного рисунка

**Функции серого растрового изображения**

MFC предоставляет две функции для придания растровому изображению вида отключенного элемента управления.

![Сравнение серых и оригинальных версий значков](../../mfc/reference/media/vcgraybitmap.gif "Сравнение серых и оригинальных версий значков")

|||
|-|-|
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Рисует серую версию растрового изображения.|
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Копирует серую версию растрового изображения.|

**Функции сглаживания растрового изображения**

MFC также предоставляет две функции для замены фона растрового изображения сглаженным шаблоном.

![Сравнение сглаженных и оригинальных версий значков](../../mfc/reference/media/vcditheredbitmap.gif "Сравнение сглаженных и оригинальных версий значков")

|||
|-|-|
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Рисует растровое изображение со сглаженным фоном.|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Копирует растровое изображение со сглаженным фоном.|

## <a name="afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a>AfxDrawGrayBitmap

Рисует серую версию растрового изображения.

```
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF crBackground);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указывает на целевой контекст устройства.

*x*<br/>
Целевая координата по оси x.

*Y*<br/>
Целевая координата по оси y.

*Rsrc*<br/>
Исходное растровое изображение.

*crBackground*<br/>
Новый цвет фона (обычно серый, например в случае с COLOR_MENU).

### <a name="remarks"></a>Remarks

Растровое изображение, рисуемое с использованием `AfxDrawGrayBitmap` , будет выглядеть как отключенный элемент управления.

![Сравнение серых и оригинальных версий значков](../../mfc/reference/media/vcgraybitmap.gif "Сравнение серых и оригинальных версий значков")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a>AfxGetGrayBitmap

Копирует серую версию растрового изображения.

```
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>Параметры

*Rsrc*<br/>
Исходное растровое изображение.

*pDest*<br/>
Растровое изображение назначения.

*crBackground*<br/>
Новый цвет фона (обычно серый, например в случае с COLOR_MENU).

### <a name="remarks"></a>Remarks

Растровое изображение, копируемое с использованием `AfxGetGrayBitmap` , будет выглядеть как отключенный элемент управления.

![Сравнение серых и оригинальных версий значков](../../mfc/reference/media/vcgraybitmap.gif "Сравнение серых и оригинальных версий значков")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a>AfxDrawDitheredBitmap

Рисует битную карту, заменяя ее фон с смягчаемым (чековым) узором.

```
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указывает на целевой контекст устройства.

*x*<br/>
Целевая координата по оси x.

*Y*<br/>
Целевая координата по оси y.

*Rsrc*<br/>
Исходное растровое изображение.

*cr1*<br/>
Один из двух цветов смяит, как правило, белый.

*cr2*<br/>
Другой цвет смещен, как правило, светло-серый (COLOR_MENU).

### <a name="remarks"></a>Remarks

Исходная биткарта нарисована на пункте назначения DC с двухцветным *(cr1* и *cr2)* клетчатым рисунком, заменяя фон биткарты. Фон исходной битной карты определяется как ее белые пиксели и все пиксели, соответствующие цвету пикселей в верхнем левом углу битной карты.

![Сравнение сглаженных и оригинальных версий значков](../../mfc/reference/media/vcditheredbitmap.gif "Сравнение сглаженных и оригинальных версий значков")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a>AfxGetDitheredBitmap

Копирует битную карту, заменяя ее фон с смягчаемым (чековым) узором.

```
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Параметры

*Rsrc*<br/>
Исходное растровое изображение.

*pDest*<br/>
Растровое изображение назначения.

*cr1*<br/>
Один из двух цветов смяит, как правило, белый.

*cr2*<br/>
Другой цвет смещен, как правило, светло-серый (COLOR_MENU).

### <a name="remarks"></a>Remarks

Исходная биткарта скопирована в локоте к месту назначения с двухцветным *(cr1* и *cr2)* клетчатым рисунком, заменяя фон исходной биткарты. Фон исходной битной карты определяется как ее белые пиксели и все пиксели, соответствующие цвету пикселей в верхнем левом углу битной карты.

![Сравнение сглаженных и оригинальных версий значков](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
