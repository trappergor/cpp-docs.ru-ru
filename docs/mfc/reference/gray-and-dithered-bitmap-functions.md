---
title: Функции серого цвета и сглаживания точечного рисунка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
dev_langs:
- C++
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 01bd722dad7e09e52990d46d1c7666cdb939118c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064132"
---
# <a name="gray-and-dithered-bitmap-functions"></a>функции серого цвета и сглаживания точечного рисунка

**Функции серого растрового изображения**

MFC предоставляет две функции для придания растровому изображению вида отключенного элемента управления.

![Сравнение версий серых и оригинальных значков](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")

|||
|-|-|
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Рисует серую версию растрового изображения.|
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Копирует серую версию растрового изображения.|

**Функции сглаживания растрового изображения**

MFC также предоставляет две функции для замены фона растрового изображения сглаженным шаблоном.

![Сравнение версий сглаженных и оригинальных значков](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")

|||
|-|-|
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Рисует растровое изображение со сглаженным фоном.|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Копирует растровое изображение со сглаженным фоном.|

##  <a name="afxdrawgraybitmap"></a>  AfxDrawGrayBitmap

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

*y*<br/>
Целевая координата по оси y.

*rSrc*<br/>
Исходное растровое изображение.

*crBackground*<br/>
Новый цвет фона (обычно серый, например в случае с COLOR_MENU).

### <a name="remarks"></a>Примечания

Растровое изображение, рисуемое с использованием `AfxDrawGrayBitmap` , будет выглядеть как отключенный элемент управления.

![Сравнение версий серых и оригинальных значков](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="afxgetgraybitmap"></a>  AfxGetGrayBitmap

Копирует серую версию растрового изображения.

```
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>Параметры

*rSrc*<br/>
Исходное растровое изображение.

*pDest*<br/>
Растровое изображение назначения.

*crBackground*<br/>
Новый цвет фона (обычно серый, например в случае с COLOR_MENU).

### <a name="remarks"></a>Примечания

Растровое изображение, копируемое с использованием `AfxGetGrayBitmap` , будет выглядеть как отключенный элемент управления.

![Сравнение версий серых и оригинальных значков](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="afxdrawditheredbitmap"></a>  AfxDrawDitheredBitmap

Рисует растровое изображение, заменив ее фона с шаблоном сглаживания (проверка).

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

*y*<br/>
Целевая координата по оси y.

*rSrc*<br/>
Исходное растровое изображение.

*cr1*<br/>
Одним из цветов, два сглаживания, обычно белых.

*CR2*<br/>
Другие сглаживания цвет, обычно светло-серый цвет (случае с COLOR_MENU).

### <a name="remarks"></a>Примечания

Исходное растровое изображение рисуется на контроллер домена назначения с помощью двух цветов (*cr1* и *cr2*) клетчатого шаблона замены фона растрового изображения. Фон исходного растрового изображения представляет собой его белым точек и всех точек, соответствующих цвет пикселя в левом верхнем углу точечного рисунка.

![Сравнение версий сглаженных и оригинальных значков](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="afxgetditheredbitmap"></a>  AfxGetDitheredBitmap

Копирует растровое изображение, заменив ее фона с шаблоном сглаживания (проверка).

```
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Параметры

*rSrc*<br/>
Исходное растровое изображение.

*pDest*<br/>
Растровое изображение назначения.

*cr1*<br/>
Одним из цветов, два сглаживания, обычно белых.

*CR2*<br/>
Другие сглаживания цвет, обычно светло-серый цвет (случае с COLOR_MENU).

### <a name="remarks"></a>Примечания

Исходное растровое изображение копируется в точечный рисунок назначения с помощью двух цветов (*cr1* и *cr2*) клетчатого шаблона, заменив исходное растровое изображение фона. Фон исходного растрового изображения представляет собой его белым точек и всех точек, соответствующих цвет пикселя в левом верхнем углу точечного рисунка.

![Сравнение версий сглаженных и оригинальных значков](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
