---
title: Класс CImage
ms.date: 02/01/2018
f1_keywords:
- CImage
- ATLIMAGE/ATL::CImage
- ATLIMAGE/ATL::CImage::CImage
- ATLIMAGE/ATL::CImage::AlphaBlend
- ATLIMAGE/ATL::CImage::Attach
- ATLIMAGE/ATL::CImage::BitBlt
- ATLIMAGE/ATL::CImage::Create
- ATLIMAGE/ATL::CImage::CreateEx
- ATLIMAGE/ATL::CImage::Destroy
- ATLIMAGE/ATL::CImage::Detach
- ATLIMAGE/ATL::CImage::Draw
- ATLIMAGE/ATL::CImage::GetBits
- ATLIMAGE/ATL::CImage::GetBPP
- ATLIMAGE/ATL::CImage::GetColorTable
- ATLIMAGE/ATL::CImage::GetDC
- ATLIMAGE/ATL::CImage::GetExporterFilterString
- ATLIMAGE/ATL::CImage::GetHeight
- ATLIMAGE/ATL::CImage::GetImporterFilterString
- ATLIMAGE/ATL::CImage::GetMaxColorTableEntries
- ATLIMAGE/ATL::CImage::GetPitch
- ATLIMAGE/ATL::CImage::GetPixel
- ATLIMAGE/ATL::CImage::GetPixelAddress
- ATLIMAGE/ATL::CImage::GetTransparentColor
- ATLIMAGE/ATL::CImage::GetWidth
- ATLIMAGE/ATL::CImage::IsDIBSection
- ATLIMAGE/ATL::CImage::IsIndexed
- ATLIMAGE/ATL::CImage::IsNull
- ATLIMAGE/ATL::CImage::IsTransparencySupported
- ATLIMAGE/ATL::CImage::Load
- ATLIMAGE/ATL::CImage::LoadFromResource
- ATLIMAGE/ATL::CImage::MaskBlt
- ATLIMAGE/ATL::CImage::PlgBlt
- ATLIMAGE/ATL::CImage::ReleaseDC
- ATLIMAGE/ATL::CImage::ReleaseGDIPlus
- ATLIMAGE/ATL::CImage::Save
- ATLIMAGE/ATL::CImage::SetColorTable
- ATLIMAGE/ATL::CImage::SetPixel
- ATLIMAGE/ATL::CImage::SetPixelIndexed
- ATLIMAGE/ATL::CImage::SetPixelRGB
- ATLIMAGE/ATL::CImage::SetTransparentColor
- ATLIMAGE/ATL::CImage::StretchBlt
- ATLIMAGE/ATL::CImage::TransparentBlt
helpviewer_keywords:
- jpeg files
- bitmaps [C++], ATL and MFC support for
- images [C++], ATL and MFC support for
- gif files, ATL and MFC support
- .gif files, ATL and MFC support
- PNG files, ATL and MFC support
- CImage class
- transparent color
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
ms.openlocfilehash: 14a4691e0c1f25a8f9e8b2b652c6e582f51c954a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775950"
---
# <a name="cimage-class"></a>Класс CImage

`CImage` Предоставляет улучшенную поддержку растровых изображений, включая возможность загрузки и сохранения изображений в формате JPEG, GIF, BMP и Portable Network Graphics (PNG).

> [!IMPORTANT]
> Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CImage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CImage::CImage](#cimage)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CImage::AlphaBlend](#alphablend)|Отображает точечным рисункам, имеющим прозрачным или полупрозрачным пикселей.|
|[CImage::Attach](#attach)|Присоединяет объект HBITMAP для `CImage` объекта. Можно использовать с точечные рисунки не DIB раздел или растровые изображения DIB раздела.|
|[CImage::BitBlt](#bitblt)|Копирует точечный рисунок из исходного контекста устройства этот текущий контекст устройства.|
|[CImage::Create](#create)|Создает раздел растровое изображение DIB и присоединяет его к ранее сконструированный `CImage` объекта.|
|[CImage::CreateEx](#createex)|Создает раздел растровое изображение DIB (с дополнительными параметрами) и присоединяет его к ранее сконструированный `CImage` объекта.|
|[CImage::Destroy](#destroy)|Отсоединяет точечного рисунка из `CImage` объекта и уничтожает растрового изображения.|
|[CImage::Detach](#detach)|Отсоединяет точечного рисунка из `CImage` объекта.|
|[CImage::Draw](#draw)|Копирует точечный рисунок из исходного прямоугольника в прямоугольник назначения. `Draw` растягивает или сжимает растрового изображения в соответствии с размерами прямоугольника назначения, при необходимости и обрабатывает альфа-смешение и прозрачного цвета.|
|[CImage::GetBits](#getbits)|Извлекает указатель на фактическое пикселов точечного рисунка.|
|[CImage::GetBPP](#getbpp)|Получает количество бит на пиксель.|
|[CImage::GetColorTable](#getcolortable)|Извлекает цветовых значений красного, зеленого и синего (RGB) из диапазона записей в таблице цветов.|
|[CImage::GetDC](#getdc)|Извлекает контекст устройства, в котором выбран текущую битовую карту.|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Находит форматов изображения доступны и их описания.|
|[CImage::GetHeight](#getheight)|Получает высоту текущего изображения в пикселях.|
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Находит форматов изображения доступны и их описания.|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Возвращает максимальное число записей в таблице цветов.|
|[CImage::GetPitch](#getpitch)|Получает высоту текущего изображения, в байтах.|
|[CImage::GetPixel](#getpixel)|Получает цвет пикселя определяется *x* и *y*.|
|[CImage::GetPixelAddress](#getpixeladdress)|Получает адрес заданной точки.|
|[CImage::GetTransparentColor](#gettransparentcolor)|Получает положение прозрачный цвет в таблице цветов.|
|[CImage::GetWidth](#getwidth)|Получает ширину текущего изображения в пикселях.|
|[CImage::IsDIBSection](#isdibsection)|Определяет, является ли вложенное растрового изображения DIB раздела.|
|[CImage::IsIndexed](#isindexed)|Указывает, что сопоставляются индексированную палитру цветов точечного рисунка.|
|[CImage::IsNull](#isnull)|Указывает, если в данный момент загружается исходное растровое изображение.|
|[CImage::IsTransparencySupported](#istransparencysupported)|Указывает, поддерживает ли приложение прозрачными точечными рисунками.|
|[CImage::Load](#load)|Загружает изображение из указанного файла.|
|[CImage::LoadFromResource](#loadfromresource)|Загружает изображение из указанного ресурса.|
|[CImage::MaskBlt](#maskblt)|Объединяет данные о цвете для исходного и конечного точечных рисунков, используя заданную маску и выполнению растровую операцию.|
|[CImage::PlgBlt](#plgblt)|Выполняет перемещение из прямоугольник в контексте устройства источника в параллелограмм, в контексте устройства назначения.|
|[CImage::ReleaseDC](#releasedc)|Освобождает контекст устройства, которое было получено с [CImage::GetDC](#getdc).|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|Освобождает ресурсы, используемые в GDI +. Необходимо вызвать для освобождения ресурсов, созданных глобальный `CImage` объекта.|
|[CImage::Save](#save)|Сохраняет изображение в указанный тип. `Save` Нельзя указать параметры изображения.|
|[CImage::SetColorTable](#setcolortable)|Задает RGB красного, зеленого и синего) значения в диапазоне записей в таблице цветов раздела DIB цветов.|
|[CImage::SetPixel](#setpixel)|Задает пикселя по указанным координатам для указанного цвета.|
|[CImage::SetPixelIndexed](#setpixelindexed)|Задает пикселя по указанным координатам на цвет по указанному индексу из палитры.|
|[CImage::SetPixelRGB](#setpixelrgb)|Задает пикселя по указанным координатам значение указанного красный, зеленый, синего (RGB).|
|[CImage::SetTransparentColor](#settransparentcolor)|Задает индекс цвет, который должен рассматриваться как прозрачный. Может быть только один цвет в палитре.|
|[CImage::StretchBlt](#stretchblt)|Копирует точечный рисунок из исходного прямоугольника в прямоугольник назначения, растягивая или сжимая точечный рисунок в соответствии с размерами прямоугольника назначения, при необходимости.|
|[CImage::TransparentBlt](#transparentblt)|Копирует растровое изображение со прозрачный цвет из контекста исходного устройства этот текущий контекст устройства.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CImage::operator HBITMAP](#operator_hbitmap)|Возвращает дескриптор Windows, подключенный к `CImage` объекта.|

## <a name="remarks"></a>Примечания

`CImage` принимает точечные рисунки, которые либо аппаратно независимый точечный рисунок (DIB) разделы или нет; Тем не менее, можно использовать [создать](#create) или [CImage::Load](#load) с использованием только DIB разделов. Можно присоединить раздел не DIB растровое изображение, чтобы `CImage` с помощью [Attach](#attach), но невозможно использовать следующие `CImage` методы, которые поддерживают только растровые изображения DIB раздел:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

Чтобы определить, является ли вложенное растрового изображения DIB раздел, вызовите [IsDibSection](#isdibsection).

> [!NOTE]
> В Visual Studio .NET 2003, этот класс поддерживает счетчик числа `CImage` объекты, созданные. Каждый раз, когда число становится равным 0, функция `GdiplusShutdown` автоматически вызывается для освобождения ресурсов, используемых в GDI +. Это гарантирует, что любой `CImage` уничтожения объектов, созданных библиотек DLL прямо или косвенно всегда правильно и что `GdiplusShutdown` не вызывается из `DllMain`.

> [!NOTE]
> С помощью глобального `CImage` объектов в библиотеке DLL не рекомендуется. Если необходимо использовать глобальную `CImage` объекта в библиотеке DLL, вызов [CImage::ReleaseGDIPlus](#releasegdiplus) явно освободить ресурсы, используемые GDI +.

`CImage` не могут быть выбраны в новую [CDC](../../mfc/reference/cdc-class.md). `CImage` создает свой собственный HDC для образа. Поскольку HBITMAP можно выбрать только в один HDC одновременно, сопоставленный HBITMAP `CImage` не могут быть выбраны в другой HDC. Если вам нужна CDC, получить HDC из `CImage` и передать его [CDC::FromHandle] (.. /.. /MFC/Reference/CDC-Class.md#cdc__fromhandle.

## <a name="example"></a>Пример

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

При использовании `CImage` в проект MFC, обратите внимание на то, какие функции-члены в вашем проекте требуется указатель на [CBitmap](../../mfc/reference/cbitmap-class.md) объекта. Если вы хотите использовать `CImage` с такие функции, как [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), использовать [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), передайте его в `CImage` HBITMAP и использовать возвращенный `CBitmap*`.

## <a name="example"></a>Пример

```cpp
void CMyDlg::OnRButtonDown(UINT nFlags, CPoint point)
{
    UNREFERENCED_PARAMETER(nFlags);

    CBitmap* pBitmap = CBitmap::FromHandle(m_myImage);
    m_pmenuPop->AppendMenu(0, ID_BMPCOMMAND, pBitmap);
    ClientToScreen(&point);
    m_pmenuPop->TrackPopupMenu(TPM_RIGHTBUTTON | TPM_LEFTALIGN, point.x,
    point.y, this);
}
```

Через `CImage`, у вас есть доступ к реальные биты раздела DIB. Можно использовать `CImage` объекта вы ранее использовали раздел Win32 HBITMAP или DIB.

Можно использовать `CImage` из MFC или ATL.

> [!NOTE]
> При создании проекта с помощью `CImage`, необходимо определить `CString` перед включением `atlimage.h`. Если в проекте используется ATL без использования MFC, включают `atlstr.h` перед включением `atlimage.h`. Если в проекте используется MFC (или если это проект ATL с поддержкой MFC), включают `afxstr.h` перед включением `atlimage.h`.<br/>
> <br/>
> Аналогичным образом, необходимо включить `atlimage.h` перед включением `atlimpl.cpp`. В этой ситуации легко включать `atlimage.h` в вашей `stdafx.h`.

## <a name="requirements"></a>Требования

**Заголовок:** atlimage.h

##  <a name="alphablend"></a>  CImage::AlphaBlend

Отображает точечным рисункам, имеющим прозрачным или полупрозрачным пикселей.

```
BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    const POINT& pointDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);

BOOL AlphaBlend(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Дескриптор контекста устройства назначения.

*xDest*<br/>
Координата x, в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y, в логических единицах верхнего левого угла прямоугольника назначения.

*bSrcAlpha*<br/>
Значение альфа-прозрачность, который будет использоваться для всего исходного растрового изображения. По умолчанию 0xff (255) предполагается, что образ является непрозрачным, и что вы хотите использовать только альфа-значения на пиксель.

*bBlendOp*<br/>
Функция альфа смешения источника и конечного точечных рисунков, глобальное альфа-значение для применения к весь исходный точечный рисунок, а также сведения о формате для исходного растрового изображения. Функции blend источника и назначения, в настоящее время ограничены AC_SRC_OVER.

*pointDest*<br/>
Ссылку на [ТОЧКИ](/previous-versions/dd162805\(v=vs.85\)) структура, определяющая в верхнем левом углу целевого прямоугольника, в логических единицах.

*nDestWidth*<br/>
Ширина в логических единицах прямоугольника назначения.

*nDestHeight*<br/>
Высота в логических единицах прямоугольника назначения.

*xSrc*<br/>
Логические Координата x верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Логические Координата y верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина в логических единицах исходного прямоугольника.

*nSrcHeight*<br/>
Высота в логических единицах исходного прямоугольника.

*rectDest*<br/>
Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, определение назначения.

*rectSrc*<br/>
Ссылку на `RECT` структура, определение источника.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Точечные рисунки с альфа смешение поддерживает наложение цвета на основе каждого пикселя.

Когда *bBlendOp* имеет значение по умолчанию AC_SRC_OVER, исходное растровое изображение наводится на основе альфа-значений точек исходный точечный рисунок назначения.

##  <a name="attach"></a>  CImage::Attach

Присоединяет *hBitmap* для `CImage` объекта.

```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
Дескриптор HBITMAP.

*eOrientation*<br/>
Задает ориентацию растрового изображения. Ниже указаны доступные значения.

- DIBOR_DEFAULT ориентацию точечного рисунка, определяется операционной системой.

- DIBOR_BOTTOMUP строки точечного рисунка не в обратном порядке. В результате [CImage::GetBits](#getbits) для возврата указателя в конце буфера растрового изображения и [CImage::GetPitch](#getpitch) для возврата отрицательное число.

- DIBOR_TOPDOWN строки точечного рисунка не в порядке сверху вниз. В результате [CImage::GetBits](#getbits) для возврата указателя на первый байт буфера растрового изображения и [CImage::GetPitch](#getpitch) для возврата положительное число.

### <a name="remarks"></a>Примечания

Растровое изображение может быть раздел точечный рисунок не DIB или разделе растрового изображения DIB. См. в разделе [IsDIBSection](#isdibsection) список методов, которые можно использовать только с DIB разделе точечных рисунков.

##  <a name="bitblt"></a>  CImage::BitBlt

Копирует точечный рисунок из исходного контекста устройства этот текущий контекст устройства.

```
BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const POINT& pointDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Назначение HDC.

*xDest*<br/>
Логические Координата x верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Логические Координата y верхнего левого угла прямоугольника назначения.

*dwROP*<br/>
Выполняемая операция растровые. Коды растровых операций определяют, как объединяются в биты источника, назначения и шаблон (в соответствии с выбранной кисти) в место назначения. См. в разделе [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) в пакете SDK для Windows, список другие коды растровых операций и их описания.

*pointDest*<br/>
Объект [ТОЧКИ](/previous-versions/dd162805\(v=vs.85\)) структура, указывающая в верхнем левом углу целевого прямоугольника.

*nDestWidth*<br/>
Ширина в логических единицах прямоугольника назначения.

*nDestHeight*<br/>
Высота в логических единицах прямоугольника назначения.

*xSrc*<br/>
Логические Координата x верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Логические Координата y верхнего левого угла исходного прямоугольника.

*rectDest*<br/>
Объект [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, указывающая целевого прямоугольника.

*pointSrc*<br/>
Объект `POINT` структура, указывающая в верхнем левом углу исходного прямоугольника.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) в пакете Windows SDK.

##  <a name="cimage"></a>  CImage::CImage

Создает объект `CImage`.

```
CImage() throw();
```

### <a name="remarks"></a>Примечания

После создания объекта вызов [создать](#create), [нагрузки](#load), [LoadFromResource](#loadfromresource), или [Attach](#attach) для прикрепления к объекту растрового изображения.

**Примечание** в Visual Studio этот класс поддерживает счетчик числа `CImage` объекты, созданные. Каждый раз, когда число становится равным 0, функция `GdiplusShutdown` автоматически вызывается для освобождения ресурсов, используемых в GDI +. Это гарантирует, что любой `CImage` уничтожения объектов, созданных библиотек DLL прямо или косвенно всегда правильно и что `GdiplusShutdown` не вызывается из DllMain.

С помощью глобального `CImage` объектов в библиотеке DLL не рекомендуется. Если необходимо использовать глобальную `CImage` объекта в библиотеке DLL, вызов [CImage::ReleaseGDIPlus](#releasegdiplus) явно освободить ресурсы, используемые GDI +.

##  <a name="create"></a>  CImage::Create

Создает `CImage` растрового изображения и присоединить ее к ранее сконструированный `CImage` объекта.

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Ширина `CImage` растрового изображения в пикселях.

*nHeight*<br/>
Высота `CImage` растрового изображения в пикселях. Если *nHeight* положительно, точечный рисунок бывает DIB снизу вверх, и его расположена в левом нижнем углу. Если *nHeight* является отрицательным, — это растровое изображение DIB сверху вниз и его расположена в левом верхнем углу.

*nBPP*<br/>
Число бит на пиксель в точечном рисунке. Обычно 4, 8, 16, 24 или 32. Может быть 1 для монохромный растровые изображения или маски.

*dwFlags*<br/>
Указывает, если объект растровое изображение содержит альфа-канал. Может представлять собой сочетание нуля или более из следующих значений:

- *createAlphaChannel* можно использовать, только если *nBPP* 32 разрядов, и *eCompression* является BI_RGB. Если указано, создаваемого образа имеет значение альфа (прозрачность) для каждого пикселя, хранящихся в четвертый байт каждый пиксель (не используются в 32-разрядного количество неалфавитно-образа). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).

> [!NOTE]
> В вызовах [CImage::Draw](#draw), рисунки с альфа-каналом выполняется автоматически альфа-смешение в место назначения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="createex"></a>  CImage::CreateEx

Создает `CImage` растрового изображения и присоединить ее к ранее сконструированный `CImage` объекта.

```
BOOL CreateEx(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD eCompression,
    const DWORD* pdwBitmasks = NULL,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Ширина `CImage` растрового изображения в пикселях.

*nHeight*<br/>
Высота `CImage` растрового изображения в пикселях. Если *nHeight* положительно, точечный рисунок бывает DIB снизу вверх, и его расположена в левом нижнем углу. Если *nHeight* является отрицательным, — это растровое изображение DIB сверху вниз и его расположена в левом верхнем углу.

*nBPP*<br/>
Число бит на пиксель в точечном рисунке. Обычно 4, 8, 16, 24 или 32. Может быть 1 для монохромный растровые изображения или маски.

*eCompression*<br/>
Указывает тип сжатия для сжатых точечный рисунок снизу вверх (не может быть сжата изображения DIB сверху вниз). Может принимать одно из следующих значений:

- BI_RGB формат без сжатия. Указание этого значения при вызове `CImage::CreateEx` эквивалентно вызову `CImage::Create`.

- BI_BITFIELDS формат без сжатия и таблицы цветов состоит из трех маски цвет DWORD, определяющие красного, зеленого и синего компонентов, соответственно, каждого пикселя. Это допустимо, при использовании с 16 и 32 bpp точечных рисунков.

*pdwBitfields*<br/>
Используется, только если *eCompression* задается для BI_BITFIELDS, в противном случае он должен иметь значение NULL. Указатель на массив из трех DWORD битовой маски, указав, какие биты каждого пикселя, используются для красного, зеленого и синего компонентов цвета, соответственно. Сведения об ограничениях для битовые поля, см. в разделе [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) в пакете Windows SDK.

*dwFlags*<br/>
Указывает, если объект растровое изображение содержит альфа-канал. Может представлять собой сочетание нуля или более из следующих значений:

- *createAlphaChannel* можно использовать, только если *nBPP* 32 разрядов, и *eCompression* является BI_RGB. Если указано, создаваемого образа имеет значение альфа (прозрачность) для каждого пикселя, хранящихся в четвертый байт каждый пиксель (не используются в 32-разрядного количество неалфавитно-образа). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).

   > [!NOTE]
   > В вызовах [CImage::Draw](#draw), рисунки с альфа-каналом выполняется автоматически альфа-смешение в место назначения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, при успешном выполнении. В противном случае — значение FALSE.

### <a name="example"></a>Пример

В следующем примере создается 100 x 100 пикселей растрового изображения, с помощью 16 бит для кодирования каждого пикселя. В необходимом 16-разрядное биты 0-3 кодирование красного компонента, бит 4 – 7 кодируют зеленого и 8 11 бит кодируют синий. Оставшиеся 4 биты не используются.

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

##  <a name="destroy"></a>  CImage::Destroy

Отсоединяет точечного рисунка из `CImage` объекта и уничтожает растрового изображения.

```
void Destroy() throw();
```

##  <a name="detach"></a>  CImage::Detach

Отсоединяет точечный рисунок из `CImage` объекта.

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор к растровому изображению отсоединена или значение NULL, если точечный рисунок отсутствует подключен.

##  <a name="draw"></a>  CImage::Draw

Копирует точечный рисунок из контекста исходного устройства в контексте текущего устройства.

```
BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest) const throw();

BOOL Draw(
    HDC hDestDC,
    const POINT& pointDest) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Дескриптор контекста устройства назначения.

*xDest*<br/>
Координата x, в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y, в логических единицах верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина в логических единицах прямоугольника назначения.

*nDestHeight*<br/>
Высота в логических единицах прямоугольника назначения.

*xSrc*<br/>
Координата x, в логических единицах верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Координата y, в логических единицах верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина в логических единицах исходного прямоугольника.

*nSrcHeight*<br/>
Высота в логических единицах исходного прямоугольника.

*rectDest*<br/>
Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, определение назначения.

*rectSrc*<br/>
Ссылку на `RECT` структура, определение источника.

*pointDest*<br/>
Ссылку на [ТОЧКИ](/previous-versions/dd162805\(v=vs.85\)) структура, определяющая в верхнем левом углу целевого прямоугольника, в логических единицах.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

`Draw` выполняет те же функции, как [StretchBlt](#stretchblt), если изображение содержит прозрачный цвет и альфа-канала. В этом случае `Draw` выполняет те же функции, как [TransparentBlt](#transparentblt) или [AlphaBlend](#alphablend) при необходимости.

Для версий `Draw` , не указывайте исходного прямоугольника, всего исходного изображения по умолчанию. Для версии `Draw` , не указать размер целевого прямоугольника, размер исходного изображения по умолчанию используется без растягивания или сжатие.

##  <a name="getbits"></a>  CImage::GetBits

Извлекает указатель на фактическое битовых значений заданного пикселя в точечном рисунке.

```
void* GetBits() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер растрового изображения. Если растровое изображение DIB снизу вверх, указывающим практически конец буфера. Если растровое изображение DIB сверху вниз, указатель указывает на первый байт буфера.

### <a name="remarks"></a>Примечания

С помощью этого указателя, а также значение, возвращенное [GetPitch](#getpitch), можно найти и изменить отдельные точки изображения.

> [!NOTE]
> Этот метод поддерживает только DIB разделе растровых изображений; Следовательно, доступ к пикселы `CImage` объект так же, как пиксели раздела DIB. Возвращаемый указатель указывает на пиксель в расположении (0, 0).

##  <a name="getbpp"></a>  CImage::GetBPP

Получает значение бита на пиксель.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Количество битов на пиксель.

### <a name="remarks"></a>Примечания

Это значение определяет количество битов, которые определяют каждый пиксель и максимальное число цветов в точечном рисунке.

Бит на пиксель, обычно является 1, 4, 8, 16, 24 или 32. См. в разделе `biBitCount` членом [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) в пакете SDK для Windows, Дополнительные сведения об этом значении.

##  <a name="getcolortable"></a>  CImage::GetColorTable

Извлекает цветовых значений красного, зеленого и синего (RGB) из диапазона записей в палитре в разделе DIB.

```
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>Параметры

*iFirstColor*<br/>
Таблица цветовой индекс первой записи для получения.

*nColors*<br/>
Число извлекаемых записей цвет таблицы.

*prgbColors*<br/>
Указатель на массив [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) структур для получения цвет таблицы записей.

##  <a name="getdc"></a>  CImage::GetDC

Извлекает контекст устройства, в котором в данный момент образ, выбранный в него.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для контекста устройства.

### <a name="remarks"></a>Примечания

Для каждого вызова `GetDC`, необходимо иметь следующий вызов [ReleaseDC](#releasedc).

##  <a name="getexporterfilterstring"></a>  CImage::GetExporterFilterString

Поиск доступных форматов изображений для сохранения изображений.

```
static HRESULT GetExporterFilterString(
    CSimpleString& strExporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultSave,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>Параметры

*strExporters*<br/>
Ссылка на объект `CSimpleString`. См. в разделе **"Примечания"** Дополнительные сведения.

*aguidFileTypes*<br/>
Массив идентификаторов GUID, при этом каждый элемент, соответствующий одному из типов файлов в строке. В примере в *pszAllFilesDescription* ниже *aguidFileTypes*[0]-GUID_NULL, а остальные значения массива — форматы файлов изображений, поддерживаемых текущей операционной системы.

> [!NOTE]
> Полный список констант, см. в разделе **константы формат файлов образа** в пакете Windows SDK.

*pszAllFilesDescription*<br/>
Если этот параметр не является NULL, строка фильтра будет иметь один дополнительный фильтр в начале списка. Этот фильтр будет иметь текущее значение *pszAllFilesDescription* его описание и принимает файлы из любого расширения, поддерживаемый другие программы экспорта в списке.

Пример:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Набор битовые флаги, определяющие, какие типы файлов для исключения из списка. Разрешены такие флаги:

- `excludeGIF` = 0x01 исключает GIF-файлы.

- `excludeBMP` = 0x02 исключает BMP (Битовая карта Windows)-файлы.

- `excludeEMF` = 0x04 исключает EMF (Enhanced Metafile) файлы.

- `excludeWMF` = 0x08 исключает WMF (Windows Metafile) файлы.

- `excludeJPEG` = 0x10 исключает JPEG-файлы.

- `excludePNG` = 0x20 исключает PNG-файлы.

- `excludeTIFF` = 0x40 исключает TIFF файлы.

- `excludeIcon` — файлы 0x80 исключает ICO (значка Windows).

- `excludeOther` = 0x80000000 исключает любые другие типы файлов, не перечисленные выше.

- `excludeDefaultLoad` = 0 для нагрузки, все типы включаются по умолчанию файл

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Для сохранения, эти файлы по умолчанию исключаются, так как они обычно имеют особые требования.

*chSeparator*<br/>
Разделитель, используемый между форматами изображения. См. в разделе **"Примечания"** Дополнительные сведения.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Результирующая строка формата можно передать в MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) форматирует объект для предоставления расширений файлов изображения, доступные в диалоговом окне Сохранение файла.

Параметр *strExporter* имеет следующий формат:

файл description0&#124;\*.ext0&#124;filedescription1&#124;\*.расш1&#124;.. описание .file *n*&#124;\*.ext *n*&#124;&#124;

где "&#124;" знак разделителя задается `chSeparator`. Пример:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Использовать разделитель по умолчанию "&#124;" Если передать эту строку для MFC `CFileDialog` объекта. Используйте null '\0' разделитель, если передать эту строку в общее диалоговое окно сохранения файла.

##  <a name="getheight"></a>  CImage::GetHeight

Получает высоту в пикселях изображения.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Высота в пикселях изображения.

##  <a name="getimporterfilterstring"></a>  CImage::GetImporterFilterString

Находит форматы изображения, доступные для загрузки изображений.

```
static HRESULT GetImporterFilterString(
    CSimpleString& strImporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultLoad,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>Параметры

*strImporters*<br/>
Ссылка на объект `CSimpleString`. См. в разделе **"Примечания"** Дополнительные сведения.

*aguidFileTypes*<br/>
Массив идентификаторов GUID, при этом каждый элемент, соответствующий одному из типов файлов в строке. В примере в *pszAllFilesDescription* ниже *aguidFileTypes*[0] является GUID_NULL оставшимися значениями массива являются форматы файлов изображений, поддерживаемых текущей операционной системы.

> [!NOTE]
> Полный список констант, см. в разделе **константы формат файлов образа** в пакете Windows SDK.

*pszAllFilesDescription*<br/>
Если этот параметр не является NULL, строка фильтра будет иметь один дополнительный фильтр в начале списка. Этот фильтр будет иметь текущее значение *pszAllFilesDescription* его описание и принимает файлы из любого расширения, поддерживаемый другие программы экспорта в списке.

Пример:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Набор битовые флаги, определяющие, какие типы файлов для исключения из списка. Разрешены такие флаги:

- `excludeGIF` = 0x01 исключает GIF-файлы.

- `excludeBMP` = 0x02 исключает BMP (Битовая карта Windows)-файлы.

- `excludeEMF` = 0x04 исключает EMF (Enhanced Metafile) файлы.

- `excludeWMF` = 0x08 исключает WMF (Windows Metafile) файлы.

- `excludeJPEG` = 0x10 исключает JPEG-файлы.

- `excludePNG` = 0x20 исключает PNG-файлы.

- `excludeTIFF` = 0x40 исключает TIFF файлы.

- `excludeIcon` — файлы 0x80 исключает ICO (значка Windows).

- `excludeOther` = 0x80000000 исключает любые другие типы файлов, не перечисленные выше.

- `excludeDefaultLoad` = 0 для нагрузки, все типы включаются по умолчанию файл

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` Для сохранения, эти файлы по умолчанию исключаются, так как они обычно имеют особые требования.

*chSeparator*<br/>
Разделитель, используемый между форматами изображения. См. в разделе **"Примечания"** Дополнительные сведения.

### <a name="remarks"></a>Примечания

Результирующая строка формата можно передать в MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) форматирует объект для предоставления расширений файлов изображения, доступные в **Открытие файла** диалоговое окно.

Параметр *strImporter* имеет следующий формат:

файл description0&#124;\*.ext0&#124;filedescription1&#124;\*.расш1&#124;.. описание .file *n*&#124;\*.ext *n*&#124;&#124;

где "&#124;" — это символ разделителя, определяемый *chSeparator*. Пример:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Использовать разделитель по умолчанию "&#124;" Если передать эту строку для MFC `CFileDialog` объекта. Используйте null '\0' разделитель, если передать эту строку в общий **Открытие файла** диалоговое окно.

##  <a name="getmaxcolortableentries"></a>  CImage::GetMaxColorTableEntries

Возвращает максимальное число записей в таблице цветов.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Число записей в таблице цветов.

### <a name="remarks"></a>Примечания

Этот метод поддерживает только растровые изображения DIB раздела.

##  <a name="getpitch"></a>  CImage::GetPitch

Получает высоту изображения.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Высота изображения. Если возвращаемое значение отрицательное, точечный рисунок бывает DIB снизу вверх, и его расположена в левом нижнем углу. Если возвращаемое значение является положительным, точечный рисунок бывает DIB сверху вниз, и его расположена в левом верхнем углу.

### <a name="remarks"></a>Примечания

Зацепка – расстояние в байтах между два адреса памяти, которые представляют в начало строки одного точечного рисунка и начало следующей строки точечного рисунка. Так как шаг измеряется в байтах, высоты тона изображения поможет вам определить формат пикселей. Шаг может также включать дополнительной памяти, зарезервированный для растрового изображения.

Используйте `GetPitch` с [GetBits](#getbits) для поиска отдельных пикселей изображения.

> [!NOTE]
> Этот метод поддерживает только растровые изображения DIB раздела.

##  <a name="getpixel"></a>  CImage::GetPixel

Получает цвет пикселя в расположении, указанном по *x* и *y*.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Координата пикселя по оси x.

*y*<br/>
Координата по оси y пикселя.

### <a name="return-value"></a>Возвращаемое значение

Красного, зеленого и синего (RGB) значение пикселя. Если пикселя находится за пределами текущей области обрезки, возвращаемое значение является CLR_INVALID.

##  <a name="getpixeladdress"></a>  CImage::GetPixelAddress

Извлекает адрес точки.

```
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Координата пикселя по оси x.

*y*<br/>
Координата по оси y пикселя.

### <a name="remarks"></a>Примечания

Адрес определяется в соответствии с координаты пикселя, голос растрового изображения и бит на пиксель.

Для форматов с менее чем 8 битами на пиксель этот метод возвращает адрес байт, содержащий пикселя. Например, если формат изображения содержит 4 бита на пиксель `GetPixelAddress` возвращает адрес первого пикселя в байт и необходимо вычислить для 2 пикселя в байте.

> [!NOTE]
> Этот метод поддерживает только растровые изображения DIB раздела.

##  <a name="gettransparentcolor"></a>  CImage::GetTransparentColor

Возвращает значение, заданное индексом местоположение объекта прозрачный цвет в палитре цветов.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Индекс прозрачный цвет.

##  <a name="getwidth"></a>  CImage::GetWidth

Получает ширину в пикселях изображения.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ширина растрового изображения в пикселях.

##  <a name="isdibsection"></a>  CImage::IsDIBSection

Определяет, является ли вложенное растрового изображения DIB раздела.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если вложенные растрового изображения DIB раздела. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если растровое изображение не раздел DIB, нельзя использовать следующие `CImage` методы, которые поддерживают только растровые изображения DIB раздел:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

##  <a name="isindexed"></a>  CImage::IsIndexed

Определяет, является ли пикселов точечного рисунка сопоставляются цветовую палитру.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если индексированные; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение TRUE только в том случае, если точечный рисунок 8-разрядное (256 цветов) или меньше.

> [!NOTE]
> Этот метод поддерживает только растровые изображения DIB раздела.

##  <a name="isnull"></a>  CImage::IsNull

Определяет, загружен ли данный момент растрового изображения.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>Примечания

Этот метод возвращает значение TRUE, если точечный рисунок еще не загружен; в противном случае — значение FALSE.

##  <a name="istransparencysupported"></a>  CImage::IsTransparencySupported

Указывает, поддерживает ли приложение прозрачными точечными рисунками.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если текущая платформа поддерживает прозрачность. В противном случае 0.

### <a name="remarks"></a>Примечания

Если возвращаемое значение не равно нулю, а также поддерживается прозрачности, вызов [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt), или [рисования](#draw) обрабатывающий прозрачные цвета.

##  <a name="load"></a>  CImage::Load

Загружает изображение.

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>Параметры

*pszFileName*<br/>
Указатель на строку, содержащую имя файла изображения для загрузки.

*pStream*<br/>
Указатель на поток, содержащий имя файла изображения для загрузки.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Загружает изображение, указанное *pszFileName* или *pStream*.

Типы допустимых изображений: BMP, GIF, JPEG, PNG и TIFF.

##  <a name="loadfromresource"></a>  CImage::LoadFromResource

Загружает изображение из ресурса точечного РИСУНКА.

```
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Дескриптор экземпляра модуля, содержащего изображение для загрузки.

*pszResourceName*<br/>
Указатель на строку, содержащую имя ресурса, содержащего изображение для загрузки.

*nIDResource*<br/>
Идентификатор ресурса для загрузки.

### <a name="remarks"></a>Примечания

Ресурс должен быть типа растрового ИЗОБРАЖЕНИЯ.

##  <a name="maskblt"></a>  CImage::MaskBlt

Объединяет данные о цвете для исходного и конечного точечных рисунков, используя заданную маску и выполнению растровую операцию.

```
BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    HBITMAP hbmMask,
    int xMask,
    int yMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    HBITMAP hbmMask,
    const POINT& pointMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const POINT& pointDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Дескриптор модуля, исполняемый файл содержит ресурс.

*xDest*<br/>
Координата x, в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y, в логических единицах верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина в логических единицах прямоугольник и исходный точечный рисунок назначения.

*nDestHeight*<br/>
Высота в логических единицах прямоугольник и исходный точечный рисунок назначения.

*xSrc*<br/>
Логические Координата x верхнего левого угла исходного растрового изображения.

*ySrc*<br/>
Логические Координата y верхнего левого угла исходного растрового изображения.

*hbmMask*<br/>
Дескриптор точечного рисунка монохромную маску, в сочетании с цветовом в контекст исходного устройства.

*xMask*<br/>
Смещение по горизонтали пикселей маска растровое изображение, указанное с *hbmMask* параметра.

*yMask*<br/>
Смещение пикселей по вертикали для битовой карты маски, определяемое *hbmMask* параметра.

*dwROP*<br/>
Указывает переднего плана и фона коды троичный растровых операций, которые данный метод использует для управления комбинации источника и назначения. Код операции растрового фона хранится в на старший байт старшее слово этого значения; Код операции растровых переднего плана хранится в младший байт из старшее слово этого значения; младшее слово этого значения учитывается и должно быть равно нулю. Описание переднего плана и фона в контексте этого метода, см. в разделе `MaskBlt` в пакете Windows SDK. Список распространенных коды растровых операций, см. в разделе `BitBlt` в пакете Windows SDK.

*rectDest*<br/>
Ссылку на `RECT` структура, определение назначения.

*pointSrc*<br/>
Объект `POINT` структура, указывающая в верхнем левом углу исходного прямоугольника.

*pointMask*<br/>
Объект `POINT` структура, указывающая в верхнем левом углу точечного рисунка маски.

*pointDest*<br/>
Ссылку на `POINT` структура, определяющая в верхнем левом углу целевого прямоугольника, в логических единицах.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если успешно, иначе — 0.

### <a name="remarks"></a>Примечания

Этот метод применим к Windows NT версии 4.0 и более поздних версий.

##  <a name="operator_hbitmap"></a>  CImage::operator HBITMAP

Этот оператор используется для получения присоединенного дескриптор Windows GDI `CImage` объекта. Этот оператор — оператор приведения, который поддерживает непосредственное использование объекта HBITMAP.

##  <a name="plgblt"></a>  CImage::PlgBlt

Выполняет перемещение из прямоугольник в контексте устройства источника в параллелограмм, в контексте устройства назначения.

```
BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    HBITMAP hbmMask = NULL) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    HBITMAP hbmMask = NULL,
    int xMask = 0,
    int yMask = 0) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    const RECT& rectSrc,
    HBITMAP hbmMask = NULL,
    const POINT& pointMask = CPoint(0, 0)) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Дескриптор контекста устройства назначения.

*pPoints*<br/>
Указатель на массив из трех точек в место на логическом, которые идентифицируют трех углов конечного параллелограмма. Первая точка в этот массив, правом верхнем углу, чтобы второй точки в этом массиве и левом нижнем углу в третью точку сопоставляется верхнем левом углу исходного прямоугольника. Правом нижнем углу исходного прямоугольника сопоставляется неявное четвертой точки в параллелограмм.

*hbmMask*<br/>
Дескриптор Дополнительно монохромный точечный рисунок, используемый для маскировки цвета исходного прямоугольника.

*xSrc*<br/>
Координата x, в логических единицах верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Координата y, в логических единицах верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина в логических единицах исходного прямоугольника.

*nSrcHeight*<br/>
Высота в логических единицах исходного прямоугольника.

*xMask*<br/>
Координата по оси x верхнего левого угла монохромный растрового изображения.

*yMask*<br/>
Координата по оси y верхнего левого угла монохромный растрового изображения.

*rectSrc*<br/>
Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структуры, указывающий координаты исходного прямоугольника.

*pointMask*<br/>
Объект [ТОЧКИ](/previous-versions/dd162805\(v=vs.85\)) структура, указывающая в верхнем левом углу точечного рисунка маски.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если успешно, иначе — 0.

### <a name="remarks"></a>Примечания

Если *hbmMask* определяет недопустимый монохромный точечный рисунок, `PlgBit` использует это растровое изображение, чтобы маскировать биты данных о цвете из исходного прямоугольника.

Этот метод применим к Windows NT версии 4.0 и более поздних версий. См. в разделе [PlgBlt](/windows/desktop/api/wingdi/nf-wingdi-plgblt) в пакете SDK Windows для получения дополнительных сведений.

##  <a name="releasedc"></a>  CImage::ReleaseDC

Освобождает контекст устройства.

```
void ReleaseDC() const throw();
```

### <a name="remarks"></a>Примечания

Так как одновременно можно выбрать только одного точечного рисунка в контексте устройства, необходимо вызвать `ReleaseDC` для каждого вызова [GetDC](#getdc).

##  <a name="releasegdiplus"></a>  CImage::ReleaseGDIPlus

Освобождает ресурсы, используемые в GDI +.

```
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>Примечания

Этот метод должен вызываться для освобождения ресурсов, выделенной с помощью глобального `CImage` объекта. См. в разделе [CImage::CImage](#cimage).

##  <a name="save"></a>  CImage::Save

Сохраняет изображение в указанный поток или файл на диске.

```
HRESULT Save(
    IStream* pStream,
    REFGUID guidFileType) const throw();

HRESULT Save(
    LPCTSTR pszFileName,
    REFGUID guidFileType = GUID_NULL) const throw();
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
Указатель на объект COM IStream, который содержит данные файла изображения.

*pszFileName*<br/>
Указатель на имя файла для изображения.

*guidFileType*<br/>
Тип файла для сохранения образа. Ниже указаны доступные значения.

- `ImageFormatBMP` Несжатый растрового изображения.

- `ImageFormatPNG` Сжатого образа графики PNG (Portable Network).

- `ImageFormatJPEG` Сжатые изображения в формате JPEG.

- `ImageFormatGIF` Сжатые изображения в формате GIF.

> [!NOTE]
> Полный список констант, см. в разделе **константы формат файлов образа** в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы сохранить изображение, используя указанные имя и тип. Если *guidFileType* параметр не указан, расширение имени файла будет использоваться для определения формата изображения. Если расширение не указан, изображение будет сохраняться в формате BMP.

##  <a name="setcolortable"></a>  CImage::SetColorTable

Задает значения цвета красного, зеленого и синего (RGB) для диапазона записей в палитре в разделе DIB.

```
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>Параметры

*iFirstColor*<br/>
Таблица цветовой индекс первой записи для задания.

*nColors*<br/>
Количество записей таблицы цветов для задания.

*prgbColors*<br/>
Указатель на массив [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) структуры, чтобы задать цвет таблицы записей.

### <a name="remarks"></a>Примечания

Этот метод поддерживает только растровые изображения DIB раздела.

##  <a name="setpixel"></a>  CImage::SetPixel

Задает цвет пикселя в заданную позицию в точечном рисунке.

```
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Горизонтальное расположение элемента пикселя, который необходимо задать.

*y*<br/>
Вертикальное расположение элемента пикселя, который необходимо задать.

*color*<br/>
Набор цветов, к которому вы пикселя.

### <a name="remarks"></a>Примечания

Этот метод завершается ошибкой, если пикселя координирует лежит за пределами выбранного отсеченную область.

##  <a name="setpixelindexed"></a>  CImage::SetPixelIndexed

Задает цвет пикселя, расположенный цвет *iIndex* в цветовой палитре.

```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Горизонтальное расположение элемента пикселя, который необходимо задать.

*y*<br/>
Вертикальное расположение элемента пикселя, который необходимо задать.

*iIndex*<br/>
Индекс цвета в цветовой палитре.

##  <a name="setpixelrgb"></a>  CImage::SetPixelRGB

Задает пикселя в расположениях, указанных *x* и *y* цветами, обозначается *r*, *g*, и *b*, в красный, зеленый, синий изображение (RGB).

```
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Горизонтальное расположение элемента пикселя, который необходимо задать.

*y*<br/>
Вертикальное расположение элемента пикселя, который необходимо задать.

*r*<br/>
Интенсивность красного цвета.

*g*<br/>
Интенсивность зеленого цвета.

*b*<br/>
Интенсивность синего цвета.

### <a name="remarks"></a>Примечания

Параметры красного, зеленого и синего выражается числом от 0 до 255. Если все три параметра равным нулю, объединенный полученный цвет будет черным. Если все три параметра равным 255, объединенный полученный цвет белый.

##  <a name="settransparentcolor"></a>  CImage::SetTransparentColor

Задает цвет в заданную позицию индексированных как прозрачный.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>Параметры

*iTransparentColor*<br/>
Индекс в цветовой палитре, чтобы задать для прозрачного цвета. Если значение-1, нет цвета присваивается прозрачным.

### <a name="return-value"></a>Возвращаемое значение

Индекс цвета предварительно заданы как прозрачный.

##  <a name="stretchblt"></a>  CImage::StretchBlt

Копирует точечный рисунок из исходного контекста устройства этот текущий контекст устройства.

```
BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Дескриптор контекста устройства назначения.

*xDest*<br/>
Координата x, в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y, в логических единицах верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина в логических единицах прямоугольника назначения.

*nDestHeight*<br/>
Высота в логических единицах прямоугольника назначения.

*dwROP*<br/>
Выполняемая операция растровые. Коды растровых операций определяют, как объединяются в биты источника, назначения и шаблон (в соответствии с выбранной кисти) в место назначения. См. в разделе [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) в пакете SDK для Windows, список другие коды растровых операций и их описания.

*rectDest*<br/>
Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, определение назначения.

*xSrc*<br/>
Координата x, в логических единицах верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Координата y, в логических единицах верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина в логических единицах исходного прямоугольника.

*nSrcHeight*<br/>
Высота в логических единицах исходного прямоугольника.

*rectSrc*<br/>
Ссылку на `RECT` структура, определение источника.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если успешно, иначе — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [StretchBlt](/windows/desktop/api/wingdi/nf-wingdi-stretchblt) в пакете Windows SDK.

##  <a name="transparentblt"></a>  CImage::TransparentBlt

Копирует точечный рисунок из исходного контекста устройства этот текущий контекст устройства.

```
BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    UINT crTransparent = CLR_INVALID) const throw();
```

### <a name="parameters"></a>Параметры

*hDestDC*<br/>
Дескриптор контекста устройства назначения.

*xDest*<br/>
Координата x, в логических единицах верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Координата y, в логических единицах верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина в логических единицах прямоугольника назначения.

*nDestHeight*<br/>
Высота в логических единицах прямоугольника назначения.

*crTransparent*<br/>
В исходный точечный рисунок должен рассматриваться как прозрачный цвет. По умолчанию CLR_INVALID, указывает, что следует использовать цвета, в настоящее время установлено как прозрачный цвет изображения.

*rectDest*<br/>
Ссылку на [RECT](/previous-versions/dd162897\(v=vs.85\)) структура, определение назначения.

*xSrc*<br/>
Координата x, в логических единицах верхнего левого угла исходного прямоугольника.

*ySrc*<br/>
Координата y, в логических единицах верхнего левого угла исходного прямоугольника.

*nSrcWidth*<br/>
Ширина в логических единицах исходного прямоугольника.

*nSrcHeight*<br/>
Высота в логических единицах исходного прямоугольника.

*rectSrc*<br/>
Ссылку на `RECT` структура, определение источника.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно, в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

`TransparentBlt` поддерживается для растровых изображений источника 4 битов на пиксель и 8 бит на пиксель. Используйте [CImage::AlphaBlend](#alphablend) для указания 32 бита на пиксель точечные рисунки с прозрачностью.

### <a name="example"></a>Пример

```cpp
// Performs a transparent blit from the source image to the destination
// image using the images' current transparency settings
BOOL TransparentBlt(CImage* pSrcImage, CImage* pDstImage,
       int xDest, int yDest, int nDestWidth, int nDestHeight)
{
    HDC hDstDC = NULL;
    BOOL bResult;

    if(pSrcImage == NULL || pDstImage == NULL)
    {
        // Invalid parameter
        return FALSE;
    }

    // Obtain a DC to the destination image
    hDstDC = pDstImage->GetDC();
    // Perform the blit
    bResult = pSrcImage->TransparentBlt(hDstDC, xDest, yDest, nDestWidth, nDestHeight);

    // Release the destination DC
    pDstImage->ReleaseDC();

    return bResult;
}
```

## <a name="see-also"></a>См. также

[Пример MMXSwarm](../../overview/visual-cpp-samples.md)<br/>
[Образце SimpleImage](../../overview/visual-cpp-samples.md)<br/>
[Аппаратно независимых точечных рисунков](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)<br/>
[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)<br/>
[Аппаратно независимых точечных рисунков](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)
