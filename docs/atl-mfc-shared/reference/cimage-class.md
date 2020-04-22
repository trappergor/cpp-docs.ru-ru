---
title: Класс CImage
ms.date: 08/19/2019
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
ms.openlocfilehash: a6d20e1bf12f5fe7d1e9b41d88b088ca9fad35ed
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747178"
---
# <a name="cimage-class"></a>Класс CImage

`CImage`обеспечивает расширенную поддержку биткарты, включая возможность загрузки и сохранения изображений в форматах JPEG, GIF, BMP и Portable Network Graphics (PNG).

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CImage
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CImage::CImage](#cimage)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CImage::AlphaBlend](#alphablend)|Отображает бит-карты с прозрачными или полупрозрачными пикселями.|
|[CImage::Прикрепите](#attach)|Прикрепляет HBITMAP `CImage` к объекту. Может быть использован либо с не-DIB разделе bitmaps или DIB разделе bitmaps.|
|[CImage::BitBlt](#bitblt)|Копирует битную карту из контекста исходного устройства в текущем контексте устройства.|
|[CImage::Создание](#create)|Создает битную карту раздела DIB и прикрепляет ее к ранее построенному `CImage` объекту.|
|[CImage:CreateEx](#createex)|Создает битную карту раздела DIB (с дополнительными параметрами) и прикрепляет ее к ранее построенному `CImage` объекту.|
|[CImage::Destroy](#destroy)|Отсоединяет битную карту с `CImage` объекта и уничтожает битную карту.|
|[CImage::Detach](#detach)|Отсоединяет битную карту с `CImage` объекта.|
|[CImage::Draw](#draw)|Копирует битную карту из прямоугольника источника в прямоугольник назначения. `Draw`растягивает или сжимает бит-карту, чтобы соответствовать размерам прямоугольника назначения, если это необходимо, и обрабатывает альфа-смешивание и прозрачные цвета.|
|[CImage::GetBits](#getbits)|Извлекает указатель на фактические значения пикселей битной карты.|
|[CImage::GetBPP](#getbpp)|Извлекает биты на пиксель.|
|[CImage::GetColorTable](#getcolortable)|Получает красные, зеленые, синие (RGB) цветовые значения из диапазона записей в таблице цветов.|
|[CImage::GetDC](#getdc)|Извлекает контекст устройства, в который выбрана текущая битовая карта.|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Находит доступные форматы изображений и их описания.|
|[CImage::GetHeight](#getheight)|Извлекает высоту текущего изображения в пикселях.|
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Находит доступные форматы изображений и их описания.|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Извлекает максимальное количество записей в таблице цветов.|
|[CImage:GetPitch](#getpitch)|Извлекает шаг текущего изображения, в байтах.|
|[CImage:GetPixel](#getpixel)|Получает цвет пикселя, указанный *x* и *y*.|
|[CImage::GetPixelAddress](#getpixeladdress)|Извлекает адрес данного пикселя.|
|[CImage::GetTransparentColor](#gettransparentcolor)|Извлекает положение прозрачного цвета в цветовой таблице.|
|[CImage::GetWidth](#getwidth)|Извлекает ширину текущего изображения в пикселях.|
|[CImage::IsDIBSection](#isdibsection)|Определяет, является ли прилагаемый бит-карта разделом DIB.|
|[CImage::Индексирован](#isindexed)|Означает, что цвета биткарты отображаются в индексируемой палитре.|
|[CImage::IsNull](#isnull)|Указывает, загружается ли в настоящее время исходная битная карта.|
|[CImage::IsTransparencyПоддерживает](#istransparencysupported)|Указывает, поддерживает ли приложение прозрачные бит-карты.|
|[CImage::Load](#load)|Загружает изображение из указанного файла.|
|[CImage::LoadFromResource](#loadfromresource)|Загружает изображение с указанного ресурса.|
|[CImage::Маскблт](#maskblt)|Комбинирует исходные данные для исходных и клиративных карт назначения с помощью указанной маски и операции raster.|
|[CImage::PlgBlt](#plgblt)|Выполняет перенос бит-блока из прямоугольника в контексте исходного устройства в параллелограмму в контексте устройства назначения.|
|[CImage::ReleaseDC](#releasedc)|Выпускает контекст устройства, который был извлечен с [помощью CImage::GetDC](#getdc).|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|Выпускает ресурсы, используемые GDI. Необходимо вызвать свободные ресурсы, созданные глобальным `CImage` объектом.|
|[CImage::Save](#save)|Сохраняет изображение как указанный тип. `Save`не могут указать параметры изображения.|
|[CImage::SetColorTable](#setcolortable)|Устанавливает красные, зеленые, синие значения RGB в диапазоне записей в цветовой таблице раздела DIB.|
|[CImage::SetPixel](#setpixel)|Устанавливает пиксель в указанных координатах к указанному цвету.|
|[CImage::SetPixelIndexed](#setpixelindexed)|Устанавливает пиксель в указанных координатах к цвету при указанном индексе палитры.|
|[CImage::SetPixelRGB](#setpixelrgb)|Устанавливает пиксель в указанных координатах к указанному значению красного, зеленого, синего (RGB).|
|[CImage::SetTransparentColor](#settransparentcolor)|Устанавливает индекс цвета, который следует рассматривать как прозрачный. Только один цвет в палитре может быть прозрачным.|
|[CImage::StretchBlt](#stretchblt)|Копирует битную карту из прямоугольника источника в прямоугольник назначения, растягивая или сжимая битную карту, чтобы при необходимости соответствовать размерам прямоугольника назначения.|
|[CImage::TransparentBlt](#transparentblt)|Копирует битную карту с прозрачным цветом из контекста исходного устройства в текущем контексте устройства.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CImage:оператор HBITMAP](#operator_hbitmap)|Возвращает ручку Windows, `CImage` прикрепленную к объекту.|

## <a name="remarks"></a>Remarks

`CImage`принимает bitmaps, которые либо устройства-независимых bitmap (DIB) разделы или нет; однако, вы можете использовать [Create](#create) или [CImage:: Загрузка](#load) только с разделами DIB. Вы можете прикрепить битную карту `CImage` раздела, не относящегося `CImage` к DIB, к объекту с помощью [Attach,](#attach)но затем вы не можете использовать следующие методы, которые поддерживают только bitmaps раздела DIB:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableE записи](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelАдрес](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

Чтобы определить, является ли прилагаемый бит-карта разделом DIB, позвоните [в IsDibSection.](#isdibsection)

> [!NOTE]
> В Visual Studio .NET 2003 этот класс ведет `CImage` подсчет количества созданных объектов. Всякий раз, когда количество `GdiplusShutdown` идет до 0, функция автоматически вызывается для освобождения ресурсов, используемых GDI. Это гарантирует, `CImage` что любые объекты, созданные прямо или `GdiplusShutdown` косвенно DLL, всегда уничтожаются должным образом, и это не вызывается из `DllMain`.

> [!NOTE]
> Использование `CImage` глобальных объектов в DLL не рекомендуется. Если вам нужно использовать `CImage` глобальный объект в DLL, позвоните [CImage::ReleaseGDIPlus,](#releasegdiplus) чтобы явно выпустить ресурсы, используемые GDI.

`CImage`не могут быть выбраны в новый [CDC](../../mfc/reference/cdc-class.md). `CImage`создает свой собственный HDC для изображения. Поскольку HBITMAP может быть выбран только в один HDC одновременно, `CImage` HBITMAP, связанный с неможет быть выбран в другой HDC. Если вам нужен CDC, получить HDC из `CImage` и дать его [CDC::FromHandle](../../mfc/reference/cdc-class.md#fromhandle).

## <a name="example"></a>Пример

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

При использовании `CImage` в проекте MFC обратите внимание, какие функции участника в проекте ожидают указателя на объект [CBitmap.](../../mfc/reference/cbitmap-class.md) Если вы хотите `CImage` использовать с такой функцией, как [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), используйте `CImage` [CBitmap::FromHandle,](../../mfc/reference/cbitmap-class.md#fromhandle)передать его ваш HBITMAP, и использовать вернулся `CBitmap*`.

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

Через `CImage`, у вас есть доступ к фактическим битов раздела DIB. Вы можете `CImage` использовать объект в любом месте, где вы ранее использовали Win32 HBITMAP или DIB разделе.

Вы можете `CImage` использовать либо из MFC или ATL.

> [!NOTE]
> При создании проекта `CImage`с использованием `CString` необходимо определить, прежде чем включать *atlimage.h.* Если ваш проект использует ATL без MFC, включите *atlstr.h,* прежде чем включать *atlimage.h*. Если ваш проект использует MFC (или если это проект ATL с поддержкой MFC), включите *afxstr.h,* прежде чем включать *atlimage.h*.<br/>
> <br/>
> Кроме того, вы должны включить *atlimage.h,* прежде чем включить *atlimpl.cpp*. Чтобы сделать это легко, включите *atlimage.h* в вашем *pch.h* *(stdafx.h* в Visual Studio 2017 и ранее).

## <a name="requirements"></a>Требования

**Заголовок:** atlimage.h

## <a name="cimagealphablend"></a><a name="alphablend"></a>CImage::AlphaBlend

Отображает бит-карты с прозрачными или полупрозрачными пикселями.

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
Обработка к контексту устройства назначения.

*xDest*<br/>
X-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Y-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*bSrcАльфа*<br/>
Значение альфа-прозрачности, используемое на всей исходной карте. По умолчанию 0xff (255) предполагает, что ваше изображение является непрозрачным, и что вы хотите использовать только на пиксельальфа альфа-значения.

*bBlendOp*<br/>
Функция альфа-смешивания для исходных и назначенияных бит-карт, глобальное альфа-значение, применяемое ко всей исходной биткарте, и форматная информация для исходной биткарты. Функции смеси источника и назначения в настоящее время ограничены AC_SRC_OVER.

*pointDest*<br/>
Ссылка на структуру [POINT,](/windows/win32/api/windef/ns-windef-point) которая идентифицирует верхний левый угол прямоугольника назначения, в логических единицах.

*nDestWidth*<br/>
Ширина, в логических единицах, прямоугольника назначения.

*nDestHeight*<br/>
Высота, в логических единицах, прямоугольника назначения.

*xSrc*<br/>
Логическая х-координата верхнего левого угла прямоугольника источника.

*ySrc*<br/>
Логическая y-координата верхнего левого угла прямоугольника источника.

*nSrcWidth*<br/>
Ширина, в логических блоках, прямоугольника источника.

*nSrcHeight*<br/>
Высота, в логических блоках, прямоугольника источника.

*rectDest*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) определяющую пункт назначения.

*rectSrc*<br/>
Ссылка на `RECT` структуру, идентифицирующую источник.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Альфа-смешать bitmaps поддержки цветового смешивания на основе на пиксель.

Когда *bBlendOp* установлен по умолчанию AC_SRC_OVER, исходная битная карта размещается над битовой картой назначения на основе альфа-значений исходных пикселей.

## <a name="cimageattach"></a><a name="attach"></a>CImage::Прикрепите

Прикрепляет *hBitmap* к объекту. `CImage`

```cpp
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>Параметры

*hBitmap*<br/>
Ручка к HBITMAP.

*eОриентация*<br/>
Определяет ориентацию бит-карты. Может применяться один из перечисленных ниже типов.

- DIBOR_DEFAULT Ориентация бит-карты определяется операционной системой.

- DIBOR_BOTTOMUP Линии битной карты находятся в обратном порядке. Это приводит к [CImage:GetBits,](#getbits) чтобы вернуть указатель ближе к концу буфера биткарты и [CImage::GetPitch,](#getpitch) чтобы вернуть отрицательное число.

- DIBOR_TOPDOWN Линии битной карты находятся в верхнем нижнем порядке. Это приводит [к CImage:GetBits,](#getbits) чтобы вернуть указатель на первый байт буфера bitmap и [CImage::GetPitch,](#getpitch) чтобы вернуть положительное число.

### <a name="remarks"></a>Remarks

Биткарта может быть либо не-DIB разделе bitmap или DIB разделе bitmap. См [IsDIBSection](#isdibsection) для списка методов, которые можно использовать только с Bitmaps раздела DIB.

## <a name="cimagebitblt"></a><a name="bitblt"></a>CImage::BitBlt

Копирует битную карту из контекста исходного устройства в текущем контексте устройства.

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
Пункт назначения HDC.

*xDest*<br/>
Логическая х-координата верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Логическая y-координата верхнего левого угла прямоугольника назначения.

*dwROP*<br/>
Операция raster, которая будет выполнена. Коды Raster-operation точно определяют, как объединить биты источника, пункта назначения и шаблона (как определено выбранной в настоящее время кистью) для формирования пункта назначения. Смотрите [BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt) в Windows SDK для списка других raster-операционных кодов и их описания.

*pointDest*<br/>
Структура [POINT,](/windows/win32/api/windef/ns-windef-point) указывающая на верхний левый угол прямоугольника назначения.

*nDestWidth*<br/>
Ширина, в логических единицах, прямоугольника назначения.

*nDestHeight*<br/>
Высота, в логических единицах, прямоугольника назначения.

*xSrc*<br/>
Логическая х-координата верхнего левого угла прямоугольника источника.

*ySrc*<br/>
Логическая y-координата верхнего левого угла прямоугольника источника.

*rectDest*<br/>
Структура [RECT,](/windows/win32/api/windef/ns-windef-rect) указывающая прямоугольник назначения.

*pointSrc*<br/>
Структура, `POINT` указывающая на верхний левый угол прямоугольника источника.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации [см.](/windows/win32/api/wingdi/nf-wingdi-bitblt)

## <a name="cimagecimage"></a><a name="cimage"></a>CImage::CImage

Формирует объект `CImage`.

```
CImage() throw();
```

### <a name="remarks"></a>Remarks

После того как вы построили объект, вызов [Создать,](#create) [Загрузить,](#load) [LoadFromResource](#loadfromresource), или [прикрепить,](#attach) чтобы прикрепить бит-карту к объекту.

**Заметка** В Visual Studio этот класс ведет подсчет `CImage` количества созданных объектов. Всякий раз, когда количество `GdiplusShutdown` идет до 0, функция автоматически вызывается для освобождения ресурсов, используемых GDI. Это гарантирует, `CImage` что любые объекты, созданные прямо или `GdiplusShutdown` косвенно DLL, всегда уничтожаются должным образом, и это не вызывается из DllMain.

Использование `CImage` глобальных объектов в DLL не рекомендуется. Если вам нужно использовать `CImage` глобальный объект в DLL, позвоните [CImage::ReleaseGDIPlus,](#releasegdiplus) чтобы явно выпустить ресурсы, используемые GDI.

## <a name="cimagecreate"></a><a name="create"></a>CImage::Создание

Создает `CImage` битную карту и прикрепите `CImage` ее к ранее построенному объекту.

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*nWidth*<br/>
Ширина `CImage` бит-карты, в пикселях.

*nВысота*<br/>
Высота `CImage` бит-карты, в пикселях. Если *nHeight* является положительным, биткарта является снизу вверх DIB и его происхождение в нижнем левом углу. Если *nHeight* отрицательный, бит-карта является сверху вниз DIB и его происхождение в верхнем левом углу.

*nBPP*<br/>
Количество битов на пиксель в битной карте. Обычно 4, 8, 16, 24 или 32. Может быть 1 для монохромных бит-карт или масок.

*dwFlags*<br/>
Определяет, имеет ли объект биткарты альфа-канал. Может быть комбинация нуля или более из следующих значений:

- *createAlphaChannel* Может быть использован только если *nBPP* 32, и *eCompression* BI_RGB. Если указано, то созданное изображение имеет альфа-(прозрачность) значение для каждого пикселя, хранящееся в 4-ом байте каждого пикселя (не используется в неальфа 32-битном изображении). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).

> [!NOTE]
> В вызовах на [CImage::Draw](#draw), изображения с альфа-каналом автоматически альфа смешиваются с пунктом назначения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="cimagecreateex"></a><a name="createex"></a>CImage:CreateEx

Создает `CImage` битную карту и прикрепите `CImage` ее к ранее построенному объекту.

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
Ширина `CImage` бит-карты, в пикселях.

*nВысота*<br/>
Высота `CImage` бит-карты, в пикселях. Если *nHeight* является положительным, биткарта является снизу вверх DIB и его происхождение в нижнем левом углу. Если *nHeight* отрицательный, бит-карта является сверху вниз DIB и его происхождение в верхнем левом углу.

*nBPP*<br/>
Количество битов на пиксель в битной карте. Обычно 4, 8, 16, 24 или 32. Может быть 1 для монохромных бит-карт или масок.

*eCompression*<br/>
Определяет тип сжатия для сжатой битовой карты снизу вверх (DIB сверху вниз не могут быть сжаты). Может использоваться одно из следующих значений:

- BI_RGB Формат не сжался. Указать это значение `CImage::CreateEx` при вызове эквивалентно вызову. `CImage::Create`

- BI_BITFIELDS формат не сжимается, а цветовая таблица состоит из трех цветовых масок DWORD, которые определяют красный, зеленый и синий компоненты, соответственно, каждого пикселя. Это действительно при использовании с 16- и 32-bpp bitmaps.

*pdwBitfields*<br/>
Используется только в том случае, если *eCompression* установлен на BI_BITFIELDS, в противном случае он должен быть NULL. Указатель на массив из трех битмасок DWORD, указывающий, какие биты каждого пикселя используются для красных, зеленых и синих компонентов цвета, соответственно. Для получения информации об ограничениях для битфилдов [см.](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader)

*dwFlags*<br/>
Определяет, имеет ли объект биткарты альфа-канал. Может быть комбинация нуля или более из следующих значений:

- *createAlphaChannel* Может быть использован только если *nBPP* 32, и *eCompression* BI_RGB. Если указано, то созданное изображение имеет альфа-(прозрачность) значение для каждого пикселя, хранящееся в 4-ом байте каждого пикселя (не используется в неальфа 32-битном изображении). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).

   > [!NOTE]
   > В вызовах на [CImage::Draw](#draw), изображения с альфа-каналом автоматически альфа смешиваются с пунктом назначения.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если успешно. В противном случае FALSE.

### <a name="example"></a>Пример

Следующий пример создает битную карту 100x100 пикселей, используя 16 битов для кодирования каждого пикселя. В данном 16-битном пикселе бис 0-3 кодируют красный компонент, биты 4-7 кодируют зеленый, а биты 8-11 кодируют синий. Остальные 4 бита не используются.

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

## <a name="cimagedestroy"></a><a name="destroy"></a>CImage::Destroy

Отсоединяет битную карту с `CImage` объекта и уничтожает битную карту.

```cpp
void Destroy() throw();
```

## <a name="cimagedetach"></a><a name="detach"></a>CImage::Detach

Отсоединяет битную карту с `CImage` объекта.

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к отсоединённости биткарты или NULL, если нет битовой карты, не прилагается.

## <a name="cimagedraw"></a><a name="draw"></a>CImage::Draw

Копирует битную карту из контекста исходного устройства в текущий контекст устройства.

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
Ручка к контексту устройства назначения.

*xDest*<br/>
X-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Y-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина, в логических единицах, прямоугольника назначения.

*nDestHeight*<br/>
Высота, в логических единицах, прямоугольника назначения.

*xSrc*<br/>
X-координация, в логических единицах, верхнего левого угла прямоугольника источника.

*ySrc*<br/>
Y-координация, в логических единицах, верхнего левого угла прямоугольника источника.

*nSrcWidth*<br/>
Ширина, в логических блоках, прямоугольника источника.

*nSrcHeight*<br/>
Высота, в логических блоках, прямоугольника источника.

*rectDest*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) определяющую пункт назначения.

*rectSrc*<br/>
Ссылка на `RECT` структуру, идентифицирующую источник.

*pointDest*<br/>
Ссылка на структуру [POINT,](/windows/win32/api/windef/ns-windef-point) которая идентифицирует верхний левый угол прямоугольника назначения, в логических единицах.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

`Draw`выполняет ту же операцию, что и [StretchBlt,](#stretchblt)если только изображение не содержит прозрачного цвета или альфа-канала. В этом `Draw` случае выполняется та же операция, что и [TransparentBlt](#transparentblt) или [AlphaBlend](#alphablend) по мере необходимости.

Для версий, `Draw` которые не указывают прямоугольник источника, все исходное изображение является по умолчанию. Для версии, `Draw` которая не указывает размер прямоугольника назначения, размер исходного изображения является по умолчанию и не происходит растяжения или сжатия.

## <a name="cimagegetbits"></a><a name="getbits"></a>CImage:GetBits

Извлекает указатель на фактические значения бита данного пикселя в битной карте.

```cpp
void* GetBits() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на буфер биткарты. Если бит-карта является DIB снизу вверх, указатель указывает ближе к концу буфера. Если бит-карта является dIB сверху вниз, указатель указывает на первый байт буфера.

### <a name="remarks"></a>Remarks

Используя этот указатель, а также значение, возвращенное [GetPitch,](#getpitch)вы можете найти и изменить отдельные пиксели на изображении.

> [!NOTE]
> Этот метод поддерживает только bitmaps раздела DIB; следовательно, вы получаете доступ `CImage` к пикселям объекта так же, как и к пикселям раздела DIB. Возвращается указатель указывает на пиксель в месте (0, 0).

## <a name="cimagegetbpp"></a><a name="getbpp"></a>CImage:GetBPP

Извлекает значение бита за пиксель.

```
int GetBPP() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Количество битов на пиксель.

### <a name="remarks"></a>Remarks

Это значение определяет количество битов, определяющих каждый пиксель, и максимальное количество цветов в битной карте.

Бит на пиксель обычно 1, 4, 8, 16, 24 или 32. Подробнее `biBitCount` об этом значении можно получить у участника [BITMAPINFOHEADER](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader) в SDK для Windows.

## <a name="cimagegetcolortable"></a><a name="getcolortable"></a>CImage:GetColorTable

Получает красный, зеленый, синий (RGB) цветовые значения из диапазона записей в палитре раздела DIB.

```cpp
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>Параметры

*iFirstColor*<br/>
Индекс цветовой таблицы первой записи для извлечения.

*nЦвета*<br/>
Количество записей таблицы цвета для извлечения.

*prgbColors*<br/>
Указатель на массив структур [РГБЗУАД](/windows/win32/api/wingdi/ns-wingdi-rgbquad) для получения записей цветной таблицы.

## <a name="cimagegetdc"></a><a name="getdc"></a>CImage:GetDC

Извлекает контекст устройства, в который в настоящее время выбрано изображение.

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для контекста устройства.

### <a name="remarks"></a>Remarks

Для каждого `GetDC`звонка в , вы должны иметь последующий вызов [ReleaseDC](#releasedc).

## <a name="cimagegetexporterfilterstring"></a><a name="getexporterfilterstring"></a>CImage:GetExporterFilterString

Находит форматы изображений, доступные для сохранения изображений.

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
Ссылка на объект `CSimpleString`. Для получения дополнительной информации смотрите **замечания.**

*aguidFileTypes*<br/>
Массив GUID, каждый элемент соответствует одному из типов файлов в строке. В приведенном ниже *примере pszAllFilesDescription* *aguidFileTypes*является GUID_NULL а остальные значения массива — это форматы файлов изображений, поддерживаемые текущей операционной системой.

> [!NOTE]
> Полный список констант смотрите **константы формата файлов изображения** в SDK Windows.

*pszAllFilesОписание*<br/>
Если этот параметр не является NULL, строка фильтра будет иметь один дополнительный фильтр в начале списка. Этот фильтр будет иметь текущую стоимость *pszAllFilesDescription* для его описания, и принимает файлы любого расширения поддерживается любым другим экспортером в списке.

Пример:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Набор битовых флагов, указывающих, какие типы файлов исключить из списка. Допустимые флаги:

- `excludeGIF`0x01 Исключает файлы GIF.

- `excludeBMP`0x02 Исключает bMP (Windows Bitmap) файлы.

- `excludeEMF`0x04 Исключает файлы EMF (Расширенный метафил.

- `excludeWMF`0x08 Исключает файлы WMF (Windows Metafile).

- `excludeJPEG`0x10 Исключает файлы JPEG.

- `excludePNG`0x20 Исключает pNG файлы.

- `excludeTIFF`0x40 Исключает файлы TIFF.

- `excludeIcon`0x80 Исключает файлы ICO (Windows Icon).

- `excludeOther`0x80000000 исключает любой другой тип файла, не перечисленные выше.

- `excludeDefaultLoad`0 Для загрузки все типы файлов включены по умолчанию

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`Для сохранения эти файлы исключаются по умолчанию, поскольку они обычно имеют особые требования.

*chSeparator*<br/>
Сепаратор, используемый между форматами изображения. Для получения дополнительной информации смотрите **замечания.**

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Remarks

Вы можете передать полученную строку формата на объект MFC [CFileDialog,](../../mfc/reference/cfiledialog-class.md) чтобы разоблачить расширение файлов доступных форматов изображений в диалоговом поле File Save As.

Параметр *strExporter* имеет формат:

файл description0 \*&#124;.ext0&#124;\*filedescription1&#124;.ext1&#124;... описание *n* файла \*n&#124;.ext *n*&#124;&#124;

где "&#124;" является символом сепаратора, указанным `chSeparator`. Пример:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Используйте "&#124;" сепаратора по умолчанию, если `CFileDialog` вы передавили эту строку объекту MFC. Используйте null separator '0', если вы передавите эту строку в общий диалоговый ящик Сохранения файлов.

## <a name="cimagegetheight"></a><a name="getheight"></a>CImage::GetHeight

Получает высоту, в пикселях, изображения.

```
int GetHeight() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Высота изображения, в пикселях.

## <a name="cimagegetimporterfilterstring"></a><a name="getimporterfilterstring"></a>CImage::GetImporterFilterString

Находит форматы изображений, доступные для загрузки изображений.

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
Ссылка на объект `CSimpleString`. Для получения дополнительной информации смотрите **замечания.**

*aguidFileTypes*<br/>
Массив GUID, каждый элемент соответствует одному из типов файлов в строке. В приведенном ниже *примере pszAllFilesDescription* *aguidFileTypes*GUID_NULL с оставшимися значениями массива являются форматами файлов изображений, поддерживаемыми текущей операционной системой.

> [!NOTE]
> Полный список констант смотрите **константы формата файлов изображения** в SDK Windows.

*pszAllFilesОписание*<br/>
Если этот параметр не является NULL, строка фильтра будет иметь один дополнительный фильтр в начале списка. Этот фильтр будет иметь текущую стоимость *pszAllFilesDescription* для его описания, и принимает файлы любого расширения поддерживается любым другим экспортером в списке.

Пример:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
Набор битовых флагов, указывающих, какие типы файлов исключить из списка. Допустимые флаги:

- `excludeGIF`0x01 Исключает файлы GIF.

- `excludeBMP`0x02 Исключает bMP (Windows Bitmap) файлы.

- `excludeEMF`0x04 Исключает файлы EMF (Расширенный метафил.

- `excludeWMF`0x08 Исключает файлы WMF (Windows Metafile).

- `excludeJPEG`0x10 Исключает файлы JPEG.

- `excludePNG`0x20 Исключает pNG файлы.

- `excludeTIFF`0x40 Исключает файлы TIFF.

- `excludeIcon`0x80 Исключает файлы ICO (Windows Icon).

- `excludeOther`0x80000000 исключает любой другой тип файла, не перечисленные выше.

- `excludeDefaultLoad`0 Для загрузки все типы файлов включены по умолчанию

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`Для сохранения эти файлы исключаются по умолчанию, поскольку они обычно имеют особые требования.

*chSeparator*<br/>
Сепаратор, используемый между форматами изображения. Для получения дополнительной информации смотрите **замечания.**

### <a name="remarks"></a>Remarks

Полученные строки формата можно передать объекту MFC [CFileDialog,](../../mfc/reference/cfiledialog-class.md) чтобы разоблачить расширение файлов доступных форматов изображений в диалоговом окне **File Open.**

Параметр *strImporter* имеет формат:

файл description0 \*&#124;.ext0&#124;\*filedescription1&#124;.ext1&#124;... описание *n* файла \*n&#124;.ext *n*&#124;&#124;

где "&#124;" является сепаратором характер, указанный *chSeparator*. Пример:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

Используйте "&#124;" сепаратора по умолчанию, если `CFileDialog` вы передавили эту строку объекту MFC. Используйте null separator '0', если вы передавите эту строку в общий диалоговый ящик **File Open.**

## <a name="cimagegetmaxcolortableentries"></a><a name="getmaxcolortableentries"></a>CImage::GetMaxColorTableE записи

Извлекает максимальное количество записей в таблице цветов.

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Количество записей в таблице цветов.

### <a name="remarks"></a>Remarks

Этот метод поддерживает только bitmaps раздела DIB.

## <a name="cimagegetpitch"></a><a name="getpitch"></a>CImage:GetPitch

Извлекает высоту изображения.

```
int GetPitch() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Смола изображения. Если значение возврата отрицательное, бит-карта является DIB снизу вверх, а его происхождение – в левом нижнем углу. Если значение возврата положительное, бит-карта является нисотворцовым DIB, а его происхождение — верхним левым углом.

### <a name="remarks"></a>Remarks

Шаг — это расстояние в байтах между двумя адресами памяти, которые представляют собой начало одной линии биткарты и начало следующей линии битмейпа. Поскольку шаг измеряется байтами, шаг изображения помогает определить формат пикселя. Поле может также включать дополнительную память, зарезервированную для бит-карты.

Используйте `GetPitch` с [GetBits](#getbits) для поиска отдельных пикселей изображения.

> [!NOTE]
> Этот метод поддерживает только bitmaps раздела DIB.

## <a name="cimagegetpixel"></a><a name="getpixel"></a>CImage:GetPixel

Получает цвет пикселя в месте, указанном *x* и *y*.

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
X-координат пикселя.

*Y*<br/>
Y-координат пикселя.

### <a name="return-value"></a>Возвращаемое значение

Красное, зеленое, синее (RGB) значение пикселя. Если пиксель находится за пределами текущей области отсечения, значение возврата CLR_INVALID.

## <a name="cimagegetpixeladdress"></a><a name="getpixeladdress"></a>CImage::GetPixelАдрес

Извлекает точный адрес пикселя.

```cpp
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
X-координат пикселя.

*Y*<br/>
Y-координат пикселя.

### <a name="remarks"></a>Remarks

Адрес определяется в соответствии с координатами пикселя, шагом битной карты и битами на пиксель.

Для форматов, которые имеют менее 8 битов на пиксель, этот метод возвращает адрес байта, содержащего пиксель. Например, если формат изображения имеет 4 `GetPixelAddress` бита на пиксель, возвращает адрес первого пикселя в байте, и вы должны вычислить по 2 пикселя на байт.

> [!NOTE]
> Этот метод поддерживает только bitmaps раздела DIB.

## <a name="cimagegettransparentcolor"></a><a name="gettransparentcolor"></a>CImage::GetTransparentColor

Извлекает индексированное расположение прозрачного цвета в цветовой палитре.

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Индекс прозрачного цвета.

## <a name="cimagegetwidth"></a><a name="getwidth"></a>CImage::GetWidth

Извлекает ширину изображения в пикселях.

```
int GetWidth() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Ширина бит-карты, в пикселях.

## <a name="cimageisdibsection"></a><a name="isdibsection"></a>CImage::IsDIBSection

Определяет, является ли прилагаемый бит-карта разделом DIB.

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если прилагается bitmap является разделd DIB. В противном случае FALSE.

### <a name="remarks"></a>Remarks

Если биткарта не является разделом DIB, `CImage` вы не можете использовать следующие методы, которые поддерживают только bitmaps раздела DIB:

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableE записи](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelАдрес](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

## <a name="cimageisindexed"></a><a name="isindexed"></a>CImage::Индексирован

Определяет, отображаются ли пиксели битовой карты в цветовую палитру.

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE при индексации; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Этот метод возвращает TRUE только в том случае, если битная карта 8-битная (256 цветов) или меньше.

> [!NOTE]
> Этот метод поддерживает только bitmaps раздела DIB.

## <a name="cimageisnull"></a><a name="isnull"></a>CImage::Isnull

Определяет, загружается ли в настоящее время битная карта.

```
bool IsNull() const throw();
```

### <a name="remarks"></a>Remarks

Этот метод возвращает TRUE, если бит-карта в настоящее время не загружена; в противном случае FALSE.

## <a name="cimageistransparencysupported"></a><a name="istransparencysupported"></a>CImage::IsTransparencyПоддерживает

Указывает, поддерживает ли приложение прозрачные бит-карты.

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если текущая платформа поддерживает прозрачность. В противном случае 0.

### <a name="remarks"></a>Remarks

Если значение возврата ненулевое, а прозрачность поддерживается, вызов в [AlphaBlend,](#alphablend) [TransparentBlt](#transparentblt)или [Draw](#draw) будет обрабатывать прозрачные цвета.

## <a name="cimageload"></a><a name="load"></a>CImage::Нагрузка

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

### <a name="remarks"></a>Remarks

Загружает изображение, указанное *pszFileName* или *pStream.*

Действительные типы изображений: BMP, GIF, JPEG, PNG и TIFF.

## <a name="cimageloadfromresource"></a><a name="loadfromresource"></a>CImage::LoadFromResource

Загружает изображение с ресурса BITMAP.

```cpp
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Ручка к экземпляру модуля, содержащего загруженное изображение.

*PSzResourceName*<br/>
Указатель на строку, содержащую имя ресурса, содержащего изображение для загрузки.

*nIDResource*<br/>
Идентификатор загружаемого ресурса.

### <a name="remarks"></a>Remarks

Ресурс должен быть типа BITMAP.

## <a name="cimagemaskblt"></a><a name="maskblt"></a>CImage::Маскблт

Комбинирует исходные данные для исходных и клиративных карт назначения с помощью указанной маски и операции raster.

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
Ручка к модулю, исполняемая которой содержит ресурс.

*xDest*<br/>
X-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Y-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина, в логических единицах, прямоугольника назначения и исходной битной карты.

*nDestHeight*<br/>
Высота, в логических единицах, прямоугольника назначения и исходной биткарты.

*xSrc*<br/>
Логическая х-координация верхнего левого угла исходной биткарты.

*ySrc*<br/>
Логическая y-координация верхнего левого угла исходной биткарты.

*hbmМаск*<br/>
Обработка к монохромной маске bitmap в сочетании с цветовой битовой картой в контексте исходного устройства.

*xМаск*<br/>
Горизонтальный пиксель смещения для маски bitmap, указанной параметром *hbmMask.*

*yМаск*<br/>
Вертикальный пиксель смещения для маски bitmap, указанной параметром *hbmMask.*

*dwROP*<br/>
Определяет как коды операций на переднем плане, так и на фоне ternary raster, которые метод использует для управления комбинацией исходных данных и данных назначения. Код работы фонового raster хранится в байте высокого порядка этого значения; код операции raster переднего плана хранится в низкопорядке байта слова высокого порядка этого значения; слово низкого порядка этого значения игнорируется и должно быть нулевым. Для обсуждения переднего плана и фона в контексте этого метода, см. `MaskBlt` Список общих кодов операций `BitBlt` raster можно узнать в SDK Windows.

*rectDest*<br/>
Ссылка на `RECT` структуру, определяющую пункт назначения.

*pointSrc*<br/>
Структура, `POINT` указывающая на верхний левый угол прямоугольника источника.

*pointMask*<br/>
Структура, `POINT` указывающая на верхний левый угол бик-карты маски.

*pointDest*<br/>
Ссылка на `POINT` структуру, которая идентифицирует верхний левый угол прямоугольника назначения, в логических единицах.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно, в противном случае 0.

### <a name="remarks"></a>Remarks

Этот метод применяется к Windows NT, версии 4.0 и только позже.

## <a name="cimageoperator-hbitmap"></a><a name="operator_hbitmap"></a>CImage:оператор HBITMAP

Используйте этот оператор, чтобы получить прилагаемую ручку Windows GDI `CImage` объекта. Этот оператор является оператором литья, который поддерживает прямое использование объекта HBITMAP.

## <a name="cimageplgblt"></a><a name="plgblt"></a>CImage::PlgBlt

Выполняет перенос бит-блока из прямоугольника в контексте исходного устройства в параллелограмму в контексте устройства назначения.

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
Ручка к контексту устройства назначения.

*pPoints*<br/>
Указатель на массив из трех точек в логическом пространстве, которые определяют три угла назначения параллелограммы. Верхний левый угол прямоугольника источника отображается до первой точки в этом массиве, верхний правый угол до второй точки в этом массиве, а нижний левый угол до третьей точки. Нижний правый угол прямоугольника источника отображается на неявной четвертой точке параллелограммы.

*hbmМаск*<br/>
Ручка к дополнительной монохромной битовой карте, которая используется для маскировки цветов исходного прямоугольника.

*xSrc*<br/>
X-координация, в логических единицах, верхнего левого угла прямоугольника источника.

*ySrc*<br/>
Y-координация, в логических единицах, верхнего левого угла прямоугольника источника.

*nSrcWidth*<br/>
Ширина, в логических блоках, прямоугольника источника.

*nSrcHeight*<br/>
Высота, в логических блоках, прямоугольника источника.

*xМаск*<br/>
X-координат верхнего левого угла монохромной битовой карты.

*yМаск*<br/>
Y-координат верхнего левого угла монохромной бит-карты.

*rectSrc*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) определяющую координаты прямоугольника источника.

*pointMask*<br/>
Структура [POINT,](/windows/win32/api/windef/ns-windef-point) указывающая на верхний левый угол бик-карты маски.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно, в противном случае 0.

### <a name="remarks"></a>Remarks

Если *hbmMask* определяет действительную монохромную бит-карту, `PlgBit` использует эту битную карту, чтобы замаскировать биты цветовых данных из исходного прямоугольника.

Этот метод применяется к Windows NT, версии 4.0 и только позже. Более подробную информацию можно узнать в [SDK](/windows/win32/api/wingdi/nf-wingdi-plgblt) Windows.

## <a name="cimagereleasedc"></a><a name="releasedc"></a>CImage::ReleaseDC

Выпускает контекст устройства.

```cpp
void ReleaseDC() const throw();
```

### <a name="remarks"></a>Remarks

Поскольку в контекст устройства можно одновременно выбрать только одну бит-карту, необходимо вызвать `ReleaseDC` каждый вызов в [GetDC.](#getdc)

## <a name="cimagereleasegdiplus"></a><a name="releasegdiplus"></a>CImage::ReleaseGDIPlus

Выпускает ресурсы, используемые GDI.

```cpp
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>Remarks

Этот метод должен быть призван к `CImage` свободным ресурсам, выделенным глобальным объектом. Смотрите [CImage::CImage](#cimage).

## <a name="cimagesave"></a><a name="save"></a>CImage::Сохранить

Сохраняет изображение в указанном потоке или файле на диске.

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
Указатель на объект COM IStream, содержащий данные файлового изображения.

*pszFileName*<br/>
Указатель на имя файла для изображения.

*guidFileType*<br/>
Тип файла для сохранения изображения как. Может применяться один из перечисленных ниже типов.

- `ImageFormatBMP`Несжатое изображение биткарты.

- `ImageFormatPNG`Портативная сетевая графическая (PNG) сжатое изображение.

- `ImageFormatJPEG`Сжатое изображение JPEG.

- `ImageFormatGIF`Сжатое изображение GIF.

> [!NOTE]
> Полный список констант смотрите **константы формата файлов изображения** в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы сохранить изображение, используя указанное имя и тип. Если параметр *guidFileType* не включен, расширение файла будет использоваться для определения формата изображения. Если расширение не предусмотрено, изображение будет сохранено в формате BMP.

## <a name="cimagesetcolortable"></a><a name="setcolortable"></a>CImage::SetColorTable

Устанавливает красные, зеленые, синие (RGB) цветовые значения для целого ряда записей в палитре раздела DIB.

```cpp
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>Параметры

*iFirstColor*<br/>
Индекс цветовой таблицы первой записи для набора.

*nЦвета*<br/>
Количество входов в таблицу цветов для установки.

*prgbColors*<br/>
Указатель на массив структур [РГБЗУАД](/windows/win32/api/wingdi/ns-wingdi-rgbquad) для установки цветных таблиц.

### <a name="remarks"></a>Remarks

Этот метод поддерживает только bitmaps раздела DIB.

## <a name="cimagesetpixel"></a><a name="setpixel"></a>CImage::SetPixel

Устанавливает цвет пикселя в заданном месте в битной карте.

```cpp
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Горизонтальное расположение пикселя для установки.

*Y*<br/>
Вертикальное расположение пикселя для установки.

*Цвет*<br/>
Цвет, которому вы устанавливаете пиксель.

### <a name="remarks"></a>Remarks

Этот метод завершается неудачей, если координаты пикселей находятся за пределами выбранной области отсечения.

## <a name="cimagesetpixelindexed"></a><a name="setpixelindexed"></a>CImage::SetPixelИндексирован

Устанавливает цвет пикселей к цвету, расположенному в *iIndex* в цветовой палитре.

```cpp
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Горизонтальное расположение пикселя для установки.

*Y*<br/>
Вертикальное расположение пикселя для установки.

*iIndex*<br/>
Индекс цвета в цветовой палитре.

## <a name="cimagesetpixelrgb"></a><a name="setpixelrgb"></a>CImage::SetPixelRGB

Устанавливает пиксель в местах, указанных *x* и *y,* цветам, указанным *r,* *g*и *b,* в красном, зеленом, синем (RGB) изображении.

```cpp
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>Параметры

*x*<br/>
Горизонтальное расположение пикселя для установки.

*Y*<br/>
Вертикальное расположение пикселя для установки.

*r*<br/>
Интенсивность красного цвета.

*Г*<br/>
Интенсивность зеленого цвета.

*B*<br/>
Интенсивность синего цвета.

### <a name="remarks"></a>Remarks

Параметры красного, зеленого и синего цветов представлены числом от 0 до 255. Если вы установите все три параметра до нуля, комбинированный полученный цвет будет черным. Если вы установите все три параметра до 255, комбинированный полученный цвет будет белым.

## <a name="cimagesettransparentcolor"></a><a name="settransparentcolor"></a>CImage::SetTransparentColor

Устанавливает цвет в данном проиндексированном месте как прозрачный.

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>Параметры

*iTransparentColor*<br/>
Индекс, в цветовой палитре, цвета, чтобы установить на прозрачный. Если -1, цвет не установлен на прозрачный.

### <a name="return-value"></a>Возвращаемое значение

Индекс цвета, ранее установленный как прозрачный.

## <a name="cimagestretchblt"></a><a name="stretchblt"></a>CImage::StretchBlt

Копирует битную карту из контекста исходного устройства в текущем контексте устройства.

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
Ручка к контексту устройства назначения.

*xDest*<br/>
X-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Y-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина, в логических единицах, прямоугольника назначения.

*nDestHeight*<br/>
Высота, в логических единицах, прямоугольника назначения.

*dwROP*<br/>
Операция raster, которая будет выполнена. Коды Raster-operation точно определяют, как объединить биты источника, пункта назначения и шаблона (как определено выбранной в настоящее время кистью) для формирования пункта назначения. Смотрите [BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt) в Windows SDK для списка других raster-операционных кодов и их описания.

*rectDest*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) определяющую пункт назначения.

*xSrc*<br/>
X-координация, в логических единицах, верхнего левого угла прямоугольника источника.

*ySrc*<br/>
Y-координация, в логических единицах, верхнего левого угла прямоугольника источника.

*nSrcWidth*<br/>
Ширина, в логических блоках, прямоугольника источника.

*nSrcHeight*<br/>
Высота, в логических блоках, прямоугольника источника.

*rectSrc*<br/>
Ссылка на `RECT` структуру, идентифицирующую источник.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно, в противном случае 0.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации [см.](/windows/win32/api/wingdi/nf-wingdi-stretchblt)

## <a name="cimagetransparentblt"></a><a name="transparentblt"></a>CImage::TransparentBlt

Копирует битную карту из контекста исходного устройства в текущем контексте устройства.

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
Ручка к контексту устройства назначения.

*xDest*<br/>
X-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*yDest*<br/>
Y-координация, в логических единицах, верхнего левого угла прямоугольника назначения.

*nDestWidth*<br/>
Ширина, в логических единицах, прямоугольника назначения.

*nDestHeight*<br/>
Высота, в логических единицах, прямоугольника назначения.

*crПрозрачный*<br/>
Цвет в исходной биткарте для обработки как прозрачный. По умолчанию CLR_INVALID, указывая, что цвет, установленный в настоящее время в качестве прозрачного цвета изображения, должен использоваться.

*rectDest*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) определяющую пункт назначения.

*xSrc*<br/>
X-координация, в логических единицах, верхнего левого угла прямоугольника источника.

*ySrc*<br/>
Y-координация, в логических единицах, верхнего левого угла прямоугольника источника.

*nSrcWidth*<br/>
Ширина, в логических блоках, прямоугольника источника.

*nSrcHeight*<br/>
Высота, в логических блоках, прямоугольника источника.

*rectSrc*<br/>
Ссылка на `RECT` структуру, идентифицирующую источник.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА в случае успеха, в противном случае FALSE.

### <a name="remarks"></a>Remarks

`TransparentBlt`поддерживается для исходных бит-карт 4 битов на пиксель и 8 бит овна пикселей. Используйте [CImage::AlphaBlend,](#alphablend) чтобы указать 32 бита на пиксельные бит-карты с прозрачностью.

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

## <a name="see-also"></a>См. также раздел

[Образец MMXSwarm](../../overview/visual-cpp-samples.md)<br/>
[Пример SimpleImage](../../overview/visual-cpp-samples.md)<br/>
[Устройства-независимые bitmaps](/windows/win32/gdi/device-independent-bitmaps)<br/>
[СоздатьDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)<br/>
[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)<br/>
[Устройства-независимые bitmaps](/windows/win32/gdi/device-independent-bitmaps)<br/>
[СоздатьDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibsection)
