---
title: Класс CDrawingManager
ms.date: 11/04/2016
f1_keywords:
- CDrawingManager
- AFXDRAWMANAGER/CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CreateBitmap_32
- AFXDRAWMANAGER/CDrawingManager::DrawAlpha
- AFXDRAWMANAGER/CDrawingManager::DrawRotated
- AFXDRAWMANAGER/CDrawingManager::DrawEllipse
- AFXDRAWMANAGER/CDrawingManager::DrawGradientRing
- AFXDRAWMANAGER/CDrawingManager::DrawRect
- AFXDRAWMANAGER/CDrawingManager::DrawShadow
- AFXDRAWMANAGER/CDrawingManager::Fill4ColorsGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient2
- AFXDRAWMANAGER/CDrawingManager::GrayRect
- AFXDRAWMANAGER/CDrawingManager::HighlightRect
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_ONE
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_TWO
- AFXDRAWMANAGER/CDrawingManager::HSVtoRGB
- AFXDRAWMANAGER/CDrawingManager::HuetoRGB
- AFXDRAWMANAGER/CDrawingManager::MirrorRect
- AFXDRAWMANAGER/CDrawingManager::PixelAlpha
- AFXDRAWMANAGER/CDrawingManager::PrepareShadowMask
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSL
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSV
- AFXDRAWMANAGER/CDrawingManager::SetAlphaPixel
- AFXDRAWMANAGER/CDrawingManager::SetPixel
- AFXDRAWMANAGER/CDrawingManager::SmartMixColors
helpviewer_keywords:
- CDrawingManager [MFC], CDrawingManager
- CDrawingManager [MFC], CreateBitmap_32
- CDrawingManager [MFC], DrawAlpha
- CDrawingManager [MFC], DrawRotated
- CDrawingManager [MFC], DrawEllipse
- CDrawingManager [MFC], DrawGradientRing
- CDrawingManager [MFC], DrawRect
- CDrawingManager [MFC], DrawShadow
- CDrawingManager [MFC], Fill4ColorsGradient
- CDrawingManager [MFC], FillGradient
- CDrawingManager [MFC], FillGradient2
- CDrawingManager [MFC], GrayRect
- CDrawingManager [MFC], HighlightRect
- CDrawingManager [MFC], HLStoRGB_ONE
- CDrawingManager [MFC], HLStoRGB_TWO
- CDrawingManager [MFC], HSVtoRGB
- CDrawingManager [MFC], HuetoRGB
- CDrawingManager [MFC], MirrorRect
- CDrawingManager [MFC], PixelAlpha
- CDrawingManager [MFC], PrepareShadowMask
- CDrawingManager [MFC], RGBtoHSL
- CDrawingManager [MFC], RGBtoHSV
- CDrawingManager [MFC], SetAlphaPixel
- CDrawingManager [MFC], SetPixel
- CDrawingManager [MFC], SmartMixColors
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
ms.openlocfilehash: 59c34a69b96cc9986db99b5f34bc38cf76f4909a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374018"
---
# <a name="cdrawingmanager-class"></a>Класс CDrawingManager

Класс `CDrawingManager` реализует сложные алгоритмы рисования.

## <a name="syntax"></a>Синтаксис

```
class CDrawingManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|Формирует объект `CDrawingManager`.|
|`CDrawingManager::~CDrawingManager`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|Создает 32-битную независимую бик-карту (DIB), на которую приложения могут писать напрямую.|
|[CDrawingManager::DrawAlpha](#drawalpha)|Отображает бит-карты с прозрачными или полупрозрачными пикселями.|
|[CDrawingManager::DrawRotated](#drawrotated)|Вращает содержание исходного постоянного тока внутри данного прямоугольника на 90 градусов|
|[CDrawingManager::DrawEllipse](#drawellipse)|Рисует эллипс с поставляемой заливкой и пограничными цветами.|
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Рисует кольцо и заполняет его градиентом цвета.|
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Рисует линию.|
|[CDrawingManager::DrawRect](#drawrect)|Рисует прямоугольник с поставляемой заливкой и пограничными цветами.|
|[CDrawingManager::DrawShadow](#drawshadow)|Рисует тень для прямоугольной области.|
|[CDrawingManager:Fill4ColorsGradient](#fill4colorsgradient)|Заполняет прямоугольную область двумя цветовыми градиентами.|
|[CDrawingManager:FillGradient](#fillgradient)|Заполняет прямоугольную область с указанным градиентом цвета.|
|[CDrawingManager:FillGradient2](#fillgradient2)|Заполняет прямоугольную область с указанным градиентом цвета. Также указывается направление изменения цвета градиента.|
|[CDrawingManager::GrayRect](#grayrect)|Заполняет прямоугольник указанным серым цветом.|
|[CDrawingManager::HighlightRect](#highlightrect)|Выделение прямоугольной области.|
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Преобразует цвет из представления HLS в rGB.|
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Преобразует цвет из представления HLS в rGB.|
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Преобразует цвет из представления HSV в rGB., представление.|
|[CDrawingManager:HuetoRGB](#huetorgb)|Метод помощника, который преобразует значение оттенка в красный, зеленый или синий компонент.|
|[CDrawingManager::MirrorRect](#mirrorrect)|Переворачивает прямоугольную область.|
|[CDrawingManager::PixelAlpha](#pixelalpha)|Метод помощника, определяющий окончательный цвет полупрозрачного пикселя.|
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Создает битную карту, которая может быть использована в качестве тени.|
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Преобразует цвет из rGB-представления в представление HSL.|
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Преобразует цвет из RGB-представления в представление HSV.|
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Метод помощника, который окрашивает частично прозрачный пиксель в битную карту.|
|[CDrawingManager::SetPixel](#setpixel)|Метод помощника, который изменяет один пиксель в битной карте на указанный цвет.|
|[CDrawingManager::SmartMixColors](#smartmixcolors)|Сочетает в себе два цвета на основе взвешенного соотношения.|

## <a name="remarks"></a>Remarks

Класс `CDrawingManager` предоставляет функции для рисования теней, градиентов цвета и выделенных прямоугольников. Он также выполняет альфа-смешивание. Этот класс можно использовать для непосредственного изменения uii вашего приложения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)<br/>
`CDrawingManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxdrawmanager.h

## <a name="cdrawingmanagercdrawingmanager"></a><a name="cdrawingmanager"></a>CDrawingManager::CDrawingManager

Строит объект [CDrawingManager.](../../mfc/reference/cdrawingmanager-class.md)

```
CDrawingManager(CDC& dc);
```

### <a name="parameters"></a>Параметры

*Dc*<br/>
(в) Ссылка на контекст устройства. Используется `CDrawingManager` этот контекст для рисования.

## <a name="cdrawingmanagercreatebitmap_32"></a><a name="createbitmap_32"></a>CDrawingManager::CreateBitmap_32

Создает 32-битную независимую бик-карту (DIB), на которую приложения могут писать напрямую.

```
static HBITMAP __stdcall CreateBitmap_32(
    const CSize& size,
    void** pBits);

static HBITMAP __stdcall CreateBitmap_32(
    HBITMAP bitmap,
    COLORREF clrTransparent = -1);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*Размер*|(в) Параметр [CSize,](../../atl-mfc-shared/reference/csize-class.md) указывающий размер битовой карты.|
|*pBits*|(ваут) Указатель на указатель данных, который получает расположение битовых значений DIB.|
|*Растрового изображения*|Ручка к исходной битовой карте|
|*clrПрозрачный*|Значение RGB, определяющее прозрачный цвет исходной битовой карты.|

### <a name="return-value"></a>Возвращаемое значение

Ручка к недавно созданной бит-карте DIB, если этот метод является успешным; в противном случае NULL.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о том, как создать бит-карту DIB, [см.](/windows/win32/api/wingdi/nf-wingdi-createdibitmap)

## <a name="cdrawingmanagerdrawalpha"></a><a name="drawalpha"></a>CDrawingManager::DrawAlpha

Отображает бит-карты с прозрачными или полупрозрачными пикселями.

```
void DrawAlpha(
    CDC* pDstDC,
    const CRect& rectDst,
    CDC* pSrcDC,
    const CRect& rectSrc);
```

### <a name="parameters"></a>Параметры

*pDstDC*<br/>
(в) Указатель на контекст устройства для назначения.

*rectDst*<br/>
(в) Прямоугольник назначения.

*pSrcDC*<br/>
(в) Указатель на контекст устройства для источника.

*rectSrc*<br/>
(в) Прямоугольник источника.

### <a name="remarks"></a>Remarks

Этот метод выполняет альфа-смешивание для двух бит-карт. Для получения дополнительной информации о альфа-смешивания, [см.](/windows/win32/api/wingdi/nf-wingdi-alphablend)

## <a name="cdrawingmanagerdrawellipse"></a><a name="drawellipse"></a>CDrawingManager::DrawEllipse

Рисует эллипс с поставляемой заливкой и пограничными цветами.

```
void DrawEllipse(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Ограничивающий прямоугольник для эллипса.

*clrFill*<br/>
(в) Цвет, используемый этим методом для заполнения эллипса.

*clrLine*<br/>
(в) Цвет, который этот метод использует в качестве границы эллипса.

### <a name="remarks"></a>Remarks

Этот метод возвращается без рисования эллипса, если любой цвет установлен до -1. Он также возвращается, не рисуя эллипс, если любое измерение связующего прямоугольника составляет 0.

## <a name="cdrawingmanagerdrawgradientring"></a><a name="drawgradientring"></a>CDrawingManager::DrawGradientRing

Рисует кольцо и заполняет его градиентом цвета.

```
BOOL DrawGradientRing(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    COLORREF colorBorder,
    int nAngle,
    int nWidth,
    COLORREF clrFace = (COLORREF)-1);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Параметр [CRect,](../../atl-mfc-shared/reference/crect-class.md) который определяет границу для кольца градиента.

*colorStart*<br/>
(в) Первый цвет для градиента.

*colorFinish*<br/>
(в) Последний цвет для градиента.

*цветГраницы*<br/>
(в) Цвет границы.

*nУгол*<br/>
(в) Параметр, описающий начальный угол рисунка градиента. Это значение должно быть между 0 и 360.

*nWidth*<br/>
(в) Ширина границы для кольца.

*clrFace*<br/>
(в) Цвет интерьера кольца.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Прямоугольник, определяемый *прямой,* должен быть не менее 5 пикселей в ширину и 5 пикселей.

## <a name="cdrawingmanagerdrawline-cdrawingmanagerdrawlinea"></a><a name="drawline_cdrawingmanager__drawlinea"></a>CDrawingManager::DrawLine, CDrawingManager::DrawLineA

Рисует линию.

```
void DrawLine(
    int x1,
    int y1,
    int x2,
    int y2,
    COLORREF clrLine);

void DrawLineA(
    double x1,
    double y1,
    double x2,
    double y2,
    COLORREF clrLine);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*x1*|(в) Х координат, где начинается линия.|
|*y1*|(в) Y координирует, где начинается линия.|
|*x2*|(в) Х координат, где заканчивается линия.|
|*y2*|(в) Y координирует, где заканчивается линия.|
|*clrLine*|(в) Цвет линии.|

### <a name="remarks"></a>Remarks

Этот метод не удается, если *clrLine* равен -1.

## <a name="cdrawingmanagerdrawrect"></a><a name="drawrect"></a>CDrawingManager::DrawRect

Рисует прямоугольник с поставляемой заливкой и пограничными цветами.

```
void DrawRect(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Границы прямоугольника.

*clrFill*<br/>
(в) Цвет, используемый этим методом для заполнения прямоугольника.

*clrLine*<br/>
(в) Цвет, который этот метод использует для границы прямоугольника.

### <a name="remarks"></a>Remarks

Этот метод возвращается без рисования прямоугольника, если любой цвет установлен до -1. Он также возвращается, если любое измерение прямоугольника составляет 0.

## <a name="cdrawingmanagerdrawshadow"></a><a name="drawshadow"></a>CDrawingManager::DrawShadow

Рисует тень для прямоугольной области.

```
BOOL DrawShadow(
    CRect rect,
    int nDepth,
    int iMinBrightness = 100,
    int iMaxBrightness = 50,
    CBitmap* pBmpSaveBottom = NULL,
    CBitmap* pBmpSaveRight = NULL,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bRightShadow = TRUE);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Прямоугольная область в приложении. Менеджер чертежа нарисует тень под этой областью.

*nГлубина*<br/>
(в) Ширина и высота тени.

*iMinBrightness*<br/>
(в) Минимальная яркость тени.

*iMaxЯркость*<br/>
(в) Максимальная яркость тени.

*pBmpSaveBottom*<br/>
(в) Указатель на битную карту, содержащую изображение для нижней части тени.

*pBmpSaveRight*<br/>
(в) Указатель на битную карту, содержащую изображение для тени, нарисованной на правой стороне прямоугольника.

*clrBase*<br/>
(в) Цвет тени.

*bRightShadow*<br/>
(в) Параметр Boolean, указывающий на то, как нарисована тень. Если *bRightShadow* `DrawShadow` является, `TRUE`рисует тень на правой стороне прямоугольника.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Вы можете предоставить две действительные бит-карты для нижних и правых теней, используя параметры *pBmpSaveBottom* и *pBmpSaveRight.* Если эти объекты [CBitmap](../../mfc/reference/cbitmap-class.md) имеют присоединенный объект GDI, `DrawShadow` будут использовать эти бит-карты в качестве теней. Если `CBitmap` параметры не имеют прилагаемого объекта `DrawShadow` GDI, рисует тень и прикрепляет биткарты к параметрам. В будущем `DrawShadow`вызовы, вы можете предоставить эти bitmaps, чтобы ускорить процесс рисования. Для получения дополнительной `CBitmap` информации об объектах класса и GDI см. [Graphic Objects](../../mfc/graphic-objects.md)

Если любой из `NULL`этих `DrawShadow` параметров, будет автоматически рисовать тень.

Если вы установите *bRightShadow* на FALSE, тень будет нарисована под и слева от прямоугольной области.

### <a name="example"></a>Пример

В следующем примере показано, `DrawShadow` как `CDrawingManager` использовать метод класса. Этот фрагмент кода является частью [образца Prop Sheet Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]

## <a name="cdrawingmanagerfill4colorsgradient"></a><a name="fill4colorsgradient"></a>CDrawingManager:Fill4ColorsGradient

Заполняет прямоугольную область двумя цветовыми градиентами.

```
void Fill4ColorsGradient(
    CRect rect,
    COLORREF colorStart1,
    COLORREF colorFinish1,
    COLORREF colorStart2,
    COLORREF colorFinish2,
    BOOL bHorz = TRUE,
    int nPercentage = 50);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Прямоугольник для заполнения.

*colorStart1*<br/>
(в) Первоначальный цвет для градиента первого цвета.

*colorFinish1*<br/>
(в) Окончательный цвет для градиента первого цвета.

*colorStart2*<br/>
(в) Первоначальный цвет для второго градиента цвета.

*colorFinish2*<br/>
(в) Окончательный цвет для второго градиента цвета.

*bHorz*<br/>
(в) Параметр Boolean, `Fill4ColorsGradient` указывающий, цвета ли горизонтального или вертикального градиента. TRUE указывает на горизонтальный градиент.

*nПроцент*<br/>
(в) С тосхом от 0-100. Это значение указывает процент прямоугольника для заполнения первого градиента цвета.

### <a name="remarks"></a>Remarks

Когда прямоугольник заполнен двумя цветовыми градиентами, они либо расположены друг над другом, либо рядом друг с другом, в зависимости от значения *bHorz.* Каждый градиент цвета рассчитывается независимо методом [CDrawingManager::FillGradient](#fillgradient).

Этот метод генерирует сбой утверждения, если *nPercentage* меньше 0 или более 100.

## <a name="cdrawingmanagerfillgradient"></a><a name="fillgradient"></a>CDrawingManager:FillGradient

Заполняет прямоугольную область с указанным градиентом цвета.

```
void FillGradient(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    BOOL bHorz = TRUE,
    int nStartFlatPercentage = 0,
    int nEndFlatPercentage = 0);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Прямоугольная область для заполнения.

*colorStart*<br/>
(в) Первый цвет для градиента.

*colorFinish*<br/>
(в) Окончательный цвет для градиента.

*bHorz*<br/>
(в) Параметр Boolean, который определяет, следует ли `FillGradient` рисовать горизонтальный или вертикальный градиент.

*nStartFlatPercentage*<br/>
(в) Процент прямоугольника, который `FillGradient` заполняется *colorStart* до того, как он начнет градиент.

*nEndFlatПроцент*<br/>
(в) Процент прямоугольника, который `FillGradient` заполняется *colorFinish* после его завершения градиента.

### <a name="example"></a>Пример

В следующем примере показано, `FillGradient` как `CDrawingManager` использовать метод класса. Этот фрагмент кода является частью [образца MS Office 2007 Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]

## <a name="cdrawingmanagerfillgradient2"></a><a name="fillgradient2"></a>CDrawingManager:FillGradient2

Заполняет прямоугольную область с указанным градиентом цвета.

```
void FillGradient2 (
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    int nAngle = 0);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Прямоугольная область для заполнения.

*colorStart*<br/>
(в) Первый цвет градиента.

*colorFinish*<br/>
(в) Последний цвет градиента.

*nУгол*<br/>
(в) Все между 0 и 360. Этот параметр определяет направление градиента цвета.

### <a name="remarks"></a>Remarks

Используйте *nAngle,* чтобы указать направление градиента цвета. Когда вы указываете направление градиента цвета, вы также указываете, где начинается градиент цвета. Значение 0 для *nAngle* указывает на то, что градиент начинается с верхней части прямоугольника. По мере увеличения *nAngle* исходное место для градиента перемещается в направлении против часовой стрелки в зависимости от угла.

### <a name="example"></a>Пример

В следующем примере показано, `FillGradient2` как `CDrawingManager` использовать метод класса. Этот фрагмент кода является частью [образца new Controls.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]

## <a name="cdrawingmanagergrayrect"></a><a name="grayrect"></a>CDrawingManager::GrayRect

Заполняет прямоугольник указанным серым цветом.

```
BOOL GrayRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    COLORREF clrDisabled = (COLORREF)-1);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Прямоугольная область для заполнения.

*nПроцент*<br/>
(в) Процент серого вы хотите в прямоугольнике.

*clrПрозрачный*<br/>
(в) Прозрачный цвет.

*clrDisabled*<br/>
(в) Цвет, который этот метод использует для де-насыщения, если *nPercentage* установлен до -1.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Для параметра *nPercentage*- более низкое значение указывает на более темный цвет.

Максимальное значение для *nPercentage* составляет 200. Значение больше 200 не меняет внешний вид прямоугольника. Если значение -1, этот метод использует *clrDisabled* для ограничения насыщения прямоугольника.

## <a name="cdrawingmanagerhighlightrect"></a><a name="highlightrect"></a>CDrawingManager::HighlightRect

Выделение прямоугольной области.

```
BOOL HighlightRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    int nTolerance = 0,
    COLORREF clrBlend = (COLORREF)-1);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Прямоугольная область для выделения.

*nПроцент*<br/>
(в) Процент, указывающий на то, насколько прозрачной должна быть изюминка.

*clrПрозрачный*<br/>
(в) Прозрачный цвет.

*nТолерантность*<br/>
(в) Цель между 0 и 255, что указывает на допуск цвета.

*clrBlend*<br/>
(в) Базовый цвет для смешивания.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод успешен; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Если *nPercentage* находится между 0 `HighlightRect` и 99, использует алгоритм альфа-смешивания. Для получения дополнительной информации о альфа-смешивания, см [Альфа Смешивание линий и заполняет](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills). Если *nPercentage* -1, этот метод использует уровень выделения по умолчанию. Если *nPercentage* 100, этот метод ничего не делает и возвращает TRUE.

Метод использует параметр *nTolerance,* чтобы определить, следует ли выделить прямоугольную область. Чтобы подчеркнуть прямоугольник, разница между цветом фона вашего приложения и *clrTransparent* должна быть меньше, чем *nTolerance* в каждом цветном компоненте (красный, зеленый и синий).

## <a name="cdrawingmanagerhlstorgb_one"></a><a name="hlstorgb_one"></a>CDrawingManager::HLStoRGB_ONE

Преобразует цвет из представления HLS в rGB.

```
static COLORREF __stdcall HLStoRGB_ONE(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>Параметры

*H*<br/>
(в) Число между 0 и 1, что представляет оттенок для цвета.

*L*<br/>
(в) Число между 0 и 1, что указывает на светимость для цвета.

*S*<br/>
(в) Число между 0 и 1, что указывает на насыщенность для цвета.

### <a name="return-value"></a>Возвращаемое значение

RGB представление цвета HLS при условии.

### <a name="remarks"></a>Remarks

Цвет может быть представлен как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и светимость), или RGB (красный, зеленый и синий). Для получения дополнительной информации о различных представлениях цвета, [см.](/windows/win32/uxguide/vis-color)

Этот метод `CDrawingManager::HLStoRGB_TWO` и метод выполняют одну и ту же операцию, но требуют различных значений для параметра *H.* В этом методе *H* представляет собой процент от круга. В `CDrawingManager::HLStoRGB_TWO` методе *H* значение степени между 0 и 360, которые оба представляют красный цвет. Например, `HLStoRGB_ONE`с значением 0.25 для *H* эквивалентно значению `HLStoRGB_TWO`90 с .

## <a name="cdrawingmanagerhlstorgb_two"></a><a name="hlstorgb_two"></a>CDrawingManager::HLStoRGB_TWO

Преобразует цвет из представления HLS в rGB.

```
static COLORREF __stdcall HLStoRGB_TWO(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>Параметры

*H*<br/>
(в) Число между 0 и 360, что представляет оттенок для цвета.

*L*<br/>
(в) Число между 0 и 1, что указывает на светимость для цвета.

*S*<br/>
(в) Число между 0 и 1, что указывает на насыщенность для цвета.

### <a name="return-value"></a>Возвращаемое значение

RGB представление цвета HLS при условии.

### <a name="remarks"></a>Remarks

Цвет может быть представлен как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и светимость), или RGB (красный, зеленый и синий). Для получения дополнительной информации о различных представлениях цвета, [см.](/windows/win32/uxguide/vis-color)

Этот метод и [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) метод выполнения одной и той же операции, но требуют различных значений для параметра *H.* В этом методе *H* является значением степени между 0 и 360, которые оба представляют собой красный цвет. В [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) метод, *H* является процентом от круга. Например, `HLStoRGB_ONE`с значением 0.25 для *H* эквивалентно значению `HLStoRGB_TWO`90 с .

## <a name="cdrawingmanagerhsvtorgb"></a><a name="hsvtorgb"></a>CDrawingManager::HSVtoRGB

Преобразует цвет из представления HSV в rGB., представление.

```
static COLORREF __stdcall HSVtoRGB(
    double H,
    double S,
    double V);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*H*|(в) Число между 0 и 360, что указывает на оттенок цвета.|
|*S*|(в) Число между 0 и 1, что указывает на насыщенность для цвета.|
|*V*|(в) Число между 0 и 1, которое указывает значение для цвета.|

### <a name="return-value"></a>Возвращаемое значение

RGB представление цвета HSV при условии.

### <a name="remarks"></a>Remarks

Цвет может быть представлен как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и светимость), или RGB (красный, зеленый и синий). Для получения дополнительной информации о различных представлениях цвета, [см.](/windows/win32/uxguide/vis-color)

## <a name="cdrawingmanagerhuetorgb"></a><a name="huetorgb"></a>CDrawingManager:HuetoRGB

Преобразует значение оттенка в красный, зеленый или синий компонент.

```
static double __stdcall HuetoRGB(
    double m1,
    double m2,
    double h);

static BYTE __stdcall HueToRGB(
    float rm1,
    float rm2,
    float rh);
```

### <a name="parameters"></a>Параметры

*m1*<br/>
(в) Смотрите замечания.

*м2*<br/>
(в) Смотрите замечания.

*H*<br/>
(в) Смотрите замечания.

*rm1*<br/>
(в) Смотрите замечания.

*rm2*<br/>
(в) Смотрите замечания.

*Rh*<br/>
(в) Смотрите замечания.

### <a name="return-value"></a>Возвращаемое значение

Индивидуальный красный, зеленый или синий компонент для при условии оттенка.

### <a name="remarks"></a>Remarks

Этот метод является методом `CDrawingManager` помощника, который класс использует для вычисления отдельных красных, зеленых и синих компонентов цвета в представлении HSV или HSL. Этот метод не предназначен для вызова непосредственно программистом. Параметры ввода являются значениями, зависят от алгоритма преобразования.

Чтобы преобразовать цвет HSV или HSL в представление RGB, позвоните в один из следующих методов:

- [CDrawingManager::HSVtoRGB](#hsvtorgb)

- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)

- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)

## <a name="cdrawingmanagermirrorrect"></a><a name="mirrorrect"></a>CDrawingManager::MirrorRect

Переворачивает прямоугольную область.

```
void MirrorRect(
    CRect rect,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
(в) Ограничивающий прямоугольник области, чтобы перевернуть.

*bHorz*<br/>
(в) Параметр Boolean, указывающий на то, переворачивается ли прямоугольник горизонтально или вертикально.

### <a name="remarks"></a>Remarks

Этот метод может переворачивать любую область `CDrawingManager` контекста устройства, принадлежащего классу. Если *bHorz* настроен на истину, этот метод переворачивает область горизонтально. В противном случае, он переворачивает область вертикально.

## <a name="cdrawingmanagerpixelalpha"></a><a name="pixelalpha"></a>CDrawingManager::PixelAlpha

Вычисляет окончательный цвет для полупрозрачного пикселя.

```
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    int percent);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    double percentR,
    double percentG,
    double percentB);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    COLORREF dstPixel,
    int percent);
```

### <a name="parameters"></a>Параметры

*srcPixel*<br/>
(в) Первоначальный цвет для пикселя.

*Процентов*<br/>
(в) Число от 0 до 100, что представляет собой процент прозрачности. Значение 100 указывает на то, что первоначальный цвет полностью прозрачный.

*percentR*<br/>
(в) Число от 0 до 100, что представляет собой процент прозрачности для красного компонента.

*percentG*<br/>
(в) Число от 0 до 100, что представляет собой процент прозрачности для зеленого компонента.

*percentB*<br/>
(в) Число от 0 до 100, что представляет собой процент прозрачности для синего компонента.

*dstPixel*<br/>
(в) Базовый цвет для пикселя.

### <a name="return-value"></a>Возвращаемое значение

Окончательный цвет для полупрозрачного пикселя.

### <a name="remarks"></a>Remarks

Это класс помощников для окраски полупрозрачных бит-карт и не предназначен для вызова непосредственно программистом.

При использовании версии метода *dstPixel,* окончательный цвет представляет собой сочетание *dstPixel* и *srcPixel.* Цвет *srcPixel* частично прозрачный цвет над базовым цветом *dstPixel.*

## <a name="cdrawingmanagerprepareshadowmask"></a><a name="prepareshadowmask"></a>CDrawingManager::PrepareShadowMask

Создает битную карту, которая может быть использована в качестве тени.

```
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,
    COLORREF clrBase,
    int iMinBrightness = 0,
    int iMaxBrightness = 100);
```

### <a name="parameters"></a>Параметры

*nГлубина*<br/>
(в) Ширина и высота тени.

*clrBase*<br/>
(в) Цвет тени.

*iMinBrightness*<br/>
(в) Минимальная яркость тени.

*iMaxЯркость*<br/>
(в) Максимальная яркость тени.

### <a name="return-value"></a>Возвращаемое значение

Ручка к созданной биткарте, если этот метод успешен; в противном случае NULL.

### <a name="remarks"></a>Remarks

Если *nDepth* настроен на 0, этот метод выходит и возвращает NULL. Если *nDepth* меньше 3, ширина и высота тени установлены до 3 пикселей.

## <a name="cdrawingmanagerrgbtohsl"></a><a name="rgbtohsl"></a>CDrawingManager::RGBtoHSL

Преобразует цвет из красного, зеленого и синего (RGB) представления в оттенок, насыщенность и легкость (HSL) представление.

```
static void __stdcall RGBtoHSL(
    COLORREF rgb,
    double* H,
    double* S,
    double* L);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*Rgb*|(в) Цвет в значениях RGB.|
|*H*|(ваут) Указатель на двойной, где метод сохраняет оттенок для цвета.|
|*S*|(ваут) Указатель на двойной, где метод сохраняет насыщенность для цвета.|
|*L*|(ваут) Указатель на двойной, где метод сохраняет легкость для цвета.|

### <a name="remarks"></a>Remarks

Цвет может быть представлен как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и светимость), или RGB (красный, зеленый и синий). Для получения дополнительной информации о различных представлениях цвета, [см.](/windows/win32/uxguide/vis-color)

Возвратное значение для *H* представлено как фракция между 0 и 1, где оба 0 и 1 представляют красный цвет. Возвращающиеся значения для *S* и *L* являются числами между 0 и 1.

## <a name="cdrawingmanagerrgbtohsv"></a><a name="rgbtohsv"></a>CDrawingManager::RGBtoHSV

Преобразует цвет из RGB-представления в представление HSV.

```
static void __stdcall RGBtoHSV(
    COLORREF rgb,
    double* H,
    double* S,
    double* V);
```

### <a name="parameters"></a>Параметры

*Rgb*<br/>
(в) Цвет для преобразования в rGB представления.

*H*<br/>
(ваут) Указатель на двойной, где этот метод сохраняет результирующее оттенок для цвета.

*S*<br/>
(ваут) Указатель на двойной, где этот метод хранит результирующее насыщение цвета.

*V*<br/>
(ваут) Указатель на двойной, где этот метод хранит результирующее значение для цвета.

### <a name="remarks"></a>Remarks

Цвет может быть представлен как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и светимость), или RGB (красный, зеленый и синий). Для получения дополнительной информации о различных представлениях цвета, [см.](/windows/win32/uxguide/vis-color)

Возвратное значение для *H* — это число между 0 и 360, где оба 0 и 360 указывают на красный цвет. Значения возврата для *S* и *V* являются числами между 0 и 1.

## <a name="cdrawingmanagersetalphapixel"></a><a name="setalphapixel"></a>CDrawingManager::SetAlphaPixel

Цвета прозрачного пикселя в битной карте.

```
static void __stdcall SetAlphaPixel(
    COLORREF* pBits,
    CRect rect,
    int x,
    int y,
    int percent,
    int iShadowSize,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bIsRight = TRUE);
```

### <a name="parameters"></a>Параметры

*pBits*<br/>
(в) Указатель на значения бита для битовой карты.

*rect*<br/>
(в) Прямоугольная область в приложении. Менеджер чертежа рисует тень внизу и справа от этой области.

*x*<br/>
(в) Горизонтальные координаты пикселя к цвету.

*Y*<br/>
(в) Вертикальная координатпик к цвету.

*Процентов*<br/>
(в) Процент прозрачности.

*iShadowSize*<br/>
(в) Ширина и высота тени.

*clrBase*<br/>
(в) Цвет тени.

*bIsRight*<br/>
(в) Параметр Boolean, указывающий, какой пиксель цвету. Дополнительные сведения см. в разделе «Примечания».

### <a name="remarks"></a>Remarks

Этот метод является помощником метода, который используется [методом CDrawingManager: :DrawShadow.](#drawshadow) Мы рекомендуем, если вы хотите нарисовать тень, позвоните `CDrawingManager::DrawShadow` вместо этого.

Если *bIsRight* установлен на ИСТИНу, пиксель к цвету измеряется *x* пикселей от правого края *прямой кишки*. Если это FALSE, пиксель к цвету измеряется *x* пикселей от левого края *прямой кишки.*

## <a name="cdrawingmanagersetpixel"></a><a name="setpixel"></a>CDrawingManager::SetPixel

Изменяет один пиксель в битной карте на указанный цвет.

```
static void __stdcall SetPixel(
    COLORREF* pBits,
    int cx,
    int cy,
    int x,
    int y,
    COLORREF color);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pBits*|(в) Указатель на значения битовой карты.|
|*Cx*|(в) Общая ширина бит-карты.|
|*Cy*|(в) Общая высота бит-карты.|
|*x*|(в) X-координат пикселя в битной карте для изменения.|
|*Y*|(в) Y-координат пикселя в битной карте для изменения.|
|*Цвет*|(в) Новый цвет для пикселя, идентифицированный по обоюдным координатам.|

## <a name="cdrawingmanagersmartmixcolors"></a><a name="smartmixcolors"></a>CDrawingManager::SmartMixColors

Сочетает в себе два цвета на основе взвешенного соотношения.

```
static COLORREF __stdcall SmartMixColors(
    COLORREF color1,
    COLORREF color2,
    double dblLumRatio = 1.,
    int k1 = 1,
    int k2 = 1);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*color1*|(в) Первый цвет для смешивания.|
|*цвет2*|(в) Второй цвет для смешивания.|
|*dblLumRatio*|(в) Соотношение светимости нового цвета. `SmartMixColors`умножает светимость смешанного цвета на это соотношение, прежде чем определить окончательный цвет.|
|*k1*|(в) Средневзвешенное соотношение для первого цвета.|
|*k2*|(в) Средневзвешенное соотношение для второго цвета.|

### <a name="return-value"></a>Возвращаемое значение

Цвет, представляющий взвешенную смесь поставляемых цветов.

### <a name="remarks"></a>Remarks

Этот метод не справляется с ошибкой, если *k1* или *k2* меньше нуля. Если оба этих параметра установлены до `RGB(0, 0, 0)`0, метод возвращается.

Взвешенное соотношение рассчитывается по следующей \* формуле: (цвет1 k1 и цвет2 \* k2)/(k1 и k2). После определения взвешенного соотношения метод вычисляет светимость для смешанного цвета. Затем он умножает светимость *dblLumRatio*. Если значение больше 1,0, метод устанавливает светимость смешанного цвета к новому значению. В противном случае светимость установлена на 1,0.

## <a name="cdrawingmanagerdrawrotated"></a><a name="drawrotated"></a>CDrawingManager::DrawRotated

Вращает содержание исходного постоянного тока внутри данного прямоугольника на 90 градусов.

```
void DrawRotated(
    CRect rectDest,
    CDC& dcSrc,
    BOOL bClockWise);
```

### <a name="parameters"></a>Параметры

*rectDest*<br/>
Прямоугольник назначения.

*dcSrc*<br/>
Контекст исходного устройства.

*bClockWise*<br/>
TRUE указывает на поворот на 90 градусов; FALSE указывает на поворот -90 градусов.

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
