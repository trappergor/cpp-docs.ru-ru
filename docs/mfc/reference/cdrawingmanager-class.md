---
title: Класс CDrawingManager | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52ded6eb4b6b757934bcdb62c280c6d57e1b171e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196064"
---
# <a name="cdrawingmanager-class"></a>Класс CDrawingManager
`CDrawingManager` Класс реализует сложные алгоритмы рисования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDrawingManager : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|Создает объект `CDrawingManager`.|  
|`CDrawingManager::~CDrawingManager`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|Создает 32-разрядных аппаратно независимых точечный рисунок (DIB), приложения могут записывать данные в напрямую.|  
|[CDrawingManager::DrawAlpha](#drawalpha)|Отображает точечным рисункам, имеющим прозрачным или полупрозрачным пикселей.|  
|[CDrawingManager::DrawRotated](#drawrotated)|Поворачивает источник содержимого DC внутри данного прямоугольника с +/-90 градусов|  
|[CDrawingManager::DrawEllipse](#drawellipse)|Рисование эллипса с предоставленным цвета заливки и границы.|  
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Рисует кольцо и заполняет его с цветным градиентом.|  
|[CDrawingManager::DrawLine CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Рисует линию.|  
|[CDrawingManager::DrawRect](#drawrect)|Рисует прямоугольник с предоставленным цвета заливки и границы.|  
|[CDrawingManager::DrawShadow](#drawshadow)|Рисует тень для прямоугольной области.|  
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|Заполняет прямоугольной области два цвета градиента.|  
|[CDrawingManager::FillGradient](#fillgradient)|Заполняет прямоугольную область градиентом указанного цвета.|  
|[CDrawingManager::FillGradient2](#fillgradient2)|Заполняет прямоугольную область градиентом указанного цвета. Также указывается направление изменение цвета градиента.|  
|[CDrawingManager::GrayRect](#grayrect)|Заполняет прямоугольник заданным цветом серого.|  
|[CDrawingManager::HighlightRect](#highlightrect)|Выделяет прямоугольной области.|  
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Преобразует цвет из представления HLS в RGB.|  
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Преобразует цвет из представления HLS в RGB.|  
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Преобразует цвет из представления HSV в RGB.|  
|[CDrawingManager::HuetoRGB](#huetorgb)|Вспомогательный метод, который преобразует значение оттенка красного, зеленого или синего компонента.|  
|[CDrawingManager::MirrorRect](#mirrorrect)|Зеркальное отражение прямоугольной области.|  
|[CDrawingManager::PixelAlpha](#pixelalpha)|Вспомогательный метод, который определяет конечный цвет для полупрозрачные компоненты пикселя.|  
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Создает точечный рисунок, который можно использовать в качестве тень.|  
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Преобразует цвета из RGB представления в представление HSL.|  
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Преобразует цвета из RGB представления в HSV.|  
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Вспомогательный метод, который цветов частично прозрачный пикселя в точечном рисунке.|  
|[CDrawingManager::SetPixel](#setpixel)|Вспомогательный метод, который примет указанный цвет одного пикселя в точечном рисунке.|  
|[CDrawingManager::SmartMixColors](#smartmixcolors)|Объединяет два цвета на основе взвешенных коэффициента.|  
  
## <a name="remarks"></a>Примечания  
 `CDrawingManager` Класс предоставляет функции для отрисовки тени, цветовые градиенты и выделенные прямоугольники. Он также выполняет альфа смешения. Этот класс можно использовать для непосредственного изменения пользовательского интерфейса приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
 `CDrawingManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdrawmanager.h  
  
##  <a name="cdrawingmanager"></a>  CDrawingManager::CDrawingManager  
 Создает [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) объекта.  
  
```  
CDrawingManager(CDC& dc);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *контроллера домена*  
 Ссылка на контекст устройства. `CDrawingManager` Использует этот контекст для рисования.  
  
##  <a name="createbitmap_32"></a>  CDrawingManager::CreateBitmap_32  
 Создает 32-разрядных аппаратно независимых точечный рисунок (DIB), приложения могут записывать данные в напрямую.  
  
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
|Параметр|Описание:|  
|[in] *размер*|Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) параметр, указывающий размер растрового изображения.|  
|[out] *pBits*|Значения битов в указатель на указатель на данные, получающий расположение DIB.|  
|*Точечный рисунок*|Дескриптор для исходного растрового изображения|  
|*clrTransparent*|Значение RGB, указав прозрачный цвет исходного растрового изображения.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор вновь созданного точечного DIB, если этот метод выполнен успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о способах создания растрового изображения DIB см. в разделе [CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibitmap).  
  
##  <a name="drawalpha"></a>  CDrawingManager::DrawAlpha  
 Отображает точечным рисункам, имеющим прозрачным или полупрозрачным пикселей.  
  
```  
void DrawAlpha(
    CDC* pDstDC,  
    const CRect& rectDst,  
    CDC* pSrcDC,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pDstDC*  
 Указатель на контекст устройства для назначения.  
  
 [in] *rectDst*  
 Прямоугольник назначения.  
  
 [in] *pSrcDC*  
 Указатель на контекст устройства для источника.  
  
 [in] *rectSrc*  
 Исходного прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет альфа смешения для двух растровых изображений. Дополнительные сведения об альфа смешения, см. в разделе [AlphaBlend](/windows/desktop/api/wingdi/nf-wingdi-alphablend) в пакете Windows SDK.  
  
##  <a name="drawellipse"></a>  CDrawingManager::DrawEllipse  
 Рисование эллипса с предоставленным цвета заливки и границы.  
  
```  
void DrawEllipse(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rect*  
 Прямоугольник, ограничивающий эллипс.  
  
 [in] *clrFill*  
 Цвет, который этот метод используется для рисования эллипса.  
  
 [in] *clrLine*  
 Цвет, этот метод использует в качестве границы эллипса.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращается без Рисование эллипса в том случае, если любой цвет имеет значение -1. Он также возвращает без Рисование эллипса в том случае, если либо измерения прямоугольника, ограничивающего равно 0.  
  
##  <a name="drawgradientring"></a>  CDrawingManager::DrawGradientRing  
 Рисует кольцо и заполняет его с цветным градиентом.  
  
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
 [in] *rect*  
 Объект [CRect](../../atl-mfc-shared/reference/crect-class.md) параметр, который задает границу для градиента кольца.  
  
 [in] *colorStart*  
 Первый цвет градиента.  
  
 [in] *colorFinish*  
 Последний цвет для градиента.  
  
 [in] *colorBorder*  
 Цвет границы.  
  
 [in] *nAngle*  
 Параметр, который задает начальный угол градиента рисования. Это значение должно быть в диапазоне от 0 до 360.  
  
 [in] *nWidth*  
 Ширина границы для кольца.  
  
 [in] *clrFace*  
 Цвет внутренней кольца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник, определяемый *rect* должен быть по крайней мере 5 пикселов шириной и 5 пикселов в высоту.  
  
##  <a name="drawline_cdrawingmanager__drawlinea"></a>  CDrawingManager::DrawLine CDrawingManager::DrawLineA  
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
|Параметр|Описание:|  
|[in] *x1*|Координата x, в которой начинается строка.|  
|[in] *y1*|Координата y, в которой начинается строка.|  
|[in] *x2*|Координата x, которой заканчивается строке.|  
|[in] *y2*|Координата y, в которой заканчивается строке.|  
|[in] *clrLine*|Цвет линии.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если *clrLine* равно -1.  
  
##  <a name="drawrect"></a>  CDrawingManager::DrawRect  
 Рисует прямоугольник с предоставленным цвета заливки и границы.  
  
```  
void DrawRect(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rect*  
 Границы для прямоугольника.  
  
 [in] *clrFill*  
 Цвет, который использует этот метод для заполнения прямоугольника.  
  
 [in] *clrLine*  
 Цвет, этот метод использует для границы прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращается без Рисование прямоугольника, если любой цвет имеет значение -1. Он также возвращает, если либо измерения прямоугольника равен 0.  
  
##  <a name="drawshadow"></a>  CDrawingManager::DrawShadow  
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
 [in] *rect*  
 Прямоугольная область в приложении. Рисования manager будет нарисовать тень под этой области.  
  
 [in] *nDepth*  
 Ширина и высота тени.  
  
 [in] *iMinBrightness*  
 Минимальное яркость тени.  
  
 [in] *iMaxBrightness*  
 Максимальное яркость тени.  
  
 [in] *pBmpSaveBottom*  
 Указатель на точечный рисунок, который содержит изображение, чтобы в нижней части окна тени.  
  
 [in] *pBmpSaveRight*  
 Указатель на точечный рисунок, который содержит изображение для его тени, рисуется правой стороны прямоугольника.  
  
 [in] *clrBase*  
 Цвет тени.  
  
 [in] *bRightShadow*  
 Логический параметр, который указывает, каким образом тень рисуется. Если *bRightShadow* — `TRUE`, `DrawShadow` рисует тень правой стороны прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Можно указать два допустимых точечные рисунки нижней и правой теней, используя параметры *pBmpSaveBottom* и *pBmpSaveRight*. Если эти [CBitmap](../../mfc/reference/cbitmap-class.md) объекты имеют присвоения объекту GDI, `DrawShadow` этих маленьких точечных изображений будет использовать в качестве теней. Если `CBitmap` параметров нет присвоения объекту GDI, `DrawShadow` рисует тень и присоединяет точечные рисунки с параметрами. В будущих вызовах `DrawShadow`, вы можете предоставить эти точечные рисунки, чтобы ускорить процесс рисования. Дополнительные сведения о `CBitmap` класс и объекты GDI, см. в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
 Если выполняется любое из этих параметров `NULL`, `DrawShadow` будет автоматически рисовании тени.  
  
 Если задать *bRightShadow* значение false, тени рисуется снизу и слева от прямоугольной области.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует, как использовать `DrawShadow` метод `CDrawingManager` класса. Этот фрагмент кода является частью [Prop лист демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]  
  
##  <a name="fill4colorsgradient"></a>  CDrawingManager::Fill4ColorsGradient  
 Заполняет прямоугольной области два цвета градиента.  
  
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
 [in] *rect*  
 Прямоугольника для заливки.  
  
 [in] *colorStart1*  
 Цвет для цветового градиента первого.  
  
 [in] *colorFinish1*  
 Конечный цвет для цветового градиента первого.  
  
 [in] *colorStart2*  
 Цвет для цветового градиента второй.  
  
 [in] *colorFinish2*  
 Конечный цвет для цветового градиента второй.  
  
 [in] *bHorz*  
 Логический параметр, указывает ли `Fill4ColorsGradient` цвета градиента горизонтальную или вертикальную. Значение TRUE указывает горизонтальный градиент.  
  
 [in] *nPercentage*  
 Целое число от 0 до 100. Это значение указывает процент прямоугольника для заливки с первого цвета градиента.  
  
### <a name="remarks"></a>Примечания  
 Если прямоугольник заполняется двумя цветовые градиенты, они расположены выше друг с другом либо рядом друг с другом, в зависимости от значения *bHorz*. Каждый цвет градиента вычисляется независимо друг от друга с помощью метода [CDrawingManager::FillGradient](#fillgradient).  
  
 Этот метод создает ошибку подтверждения, если *nPercentage* меньше 0 или больше 100.  
  
##  <a name="fillgradient"></a>  CDrawingManager::FillGradient  
 Заполняет указанный цвет градиента прямоугольной области.  
  
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
 [in] *rect*  
 Прямоугольная область для заливки.  
  
 [in] *colorStart*  
 Первый цвет градиента.  
  
 [in] *colorFinish*  
 Конечный цвет градиента.  
  
 [in] *bHorz*  
 Логический параметр, указывает ли `FillGradient` следует рисования градиента горизонтальную или вертикальную.  
  
 [in] *nStartFlatPercentage*  
 Процент прямоугольника, `FillGradient` заполняет *colorStart* перед началом градиента.  
  
 [in] *nEndFlatPercentage*  
 Процент прямоугольника, `FillGradient` заполняет *colorFinish* после его завершения градиента.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует, как использовать `FillGradient` метод `CDrawingManager` класса. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]  
  
##  <a name="fillgradient2"></a>  CDrawingManager::FillGradient2  
 Заполняет прямоугольную область градиентом указанного цвета.  
  
```  
void FillGradient2 (
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    int nAngle = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rect*  
 Прямоугольная область для заливки.  
  
 [in] *colorStart*  
 Первый цвет градиента.  
  
 [in] *colorFinish*  
 Последний цвет градиента.  
  
 [in] *nAngle*  
 Целое число в диапазоне от 0 до 360. Этот параметр задает направление градиента.  
  
### <a name="remarks"></a>Примечания  
 Используйте *nAngle* для указания направления градиента. При указании направление градиента, можно также указать начала градиента. Значение 0 для *nAngle* указывает градиента начинается от верхней стороны прямоугольника. Как *nAngle* увеличивается, начальное положение для градиента перемещается в направлении против часовой стрелки на основе углов.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует, как использовать `FillGradient2` метод `CDrawingManager` класса. Этот фрагмент кода является частью [пример новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]  
  
##  <a name="grayrect"></a>  CDrawingManager::GrayRect  
 Заполняет прямоугольник заданным цветом серого.  
  
```  
BOOL GrayRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    COLORREF clrDisabled = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rect*  
 Прямоугольная область для заливки.  
  
 [in] *nPercentage*  
 Процент серого в прямоугольник.  
  
 [in] *clrTransparent*  
 Прозрачный цвет.  
  
 [in] *clrDisabled*  
 Цвет, который использует этот метод для удаления насыщенность, если *nPercentage* устанавливается равным -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Для параметра *nPercentage*, более низкое значение указывает более темным цветом.  
  
 Максимальное значение для *nPercentage* — 200. Значение, размер которых превышает 200 изменяется внешний вид прямоугольника. Если значение равно -1, этот метод использует *clrDisabled* для ограничения насыщенность прямоугольника.  
  
##  <a name="highlightrect"></a>  CDrawingManager::HighlightRect  
 Выделяет прямоугольной области.  
  
```  
BOOL HighlightRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    int nTolerance = 0,  
    COLORREF clrBlend = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rect*  
 Прямоугольная область, чтобы выделить.  
  
 [in] *nPercentage*  
 Процент, которое указывает как Прозрачное выделение.  
  
 [in] *clrTransparent*  
 Прозрачный цвет.  
  
 [in] *nTolerance*  
 Целое число от 0 до 255, указывает допустимое значение цвета.  
  
 [in] *clrBlend*  
 Базовый цвет для наложения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Если *nPercentage* — от 0 до 99, `HighlightRect` альфа-каналом алгоритма смешивания. Дополнительные сведения об альфа-смешением, см. в разделе [альфа-канала для наложения линий и заливок](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills). Если *nPercentage* равно -1, этот метод использует уровень выделения по умолчанию. Если *nPercentage* — 100, этот метод не выполняет никаких действий и возвращает значение TRUE.  
  
 Данный метод использует параметр *nTolerance* для определения необходимости выделите прямоугольной области. Чтобы выделить прямоугольник, разница между цвет фона, приложения и *clrTransparent* должно быть меньше, чем *nTolerance* в каждом компоненте цвет (красный, зеленый и синий).  
  
##  <a name="hlstorgb_one"></a>  CDrawingManager::HLStoRGB_ONE  
 Преобразует цвет из представления HLS в RGB.  
  
```  
static COLORREF __stdcall HLStoRGB_ONE(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *H*  
 Число от 0 до 1, представляющее оттенок цвета.  
  
 [in] *L*  
 Число от 0 до 1, обозначающее яркость цвета.  
  
 [in] *S*  
 Число от 0 до 1, указывающее насыщенность цвета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представление RGB, предоставленные цвета HLS.  
  
### <a name="remarks"></a>Примечания  
 Цвет можно представить как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и яркость) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета, см. в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Этот метод и `CDrawingManager::HLStoRGB_TWO` метод выполнить те же операции, но требуется указывать другие значения для *H* параметра. В этом методе *H* в процентах от круга. В `CDrawingManager::HLStoRGB_TWO` метод, *H* — это значение в градусах от 0 до 360 градусов, представляющие обоих red. Например, с помощью `HLStoRGB_ONE`, значение 0,25 для *H* эквивалентен значение 90, с помощью `HLStoRGB_TWO`.  
  
##  <a name="hlstorgb_two"></a>  CDrawingManager::HLStoRGB_TWO  
 Преобразует цвет из представления HLS в RGB.  
  
```  
static COLORREF __stdcall HLStoRGB_TWO(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *H*  
 Число от 0 до 360, представляющее оттенок цвета.  
  
 [in] *L*  
 Число от 0 до 1, обозначающее яркость цвета.  
  
 [in] *S*  
 Число от 0 до 1, указывающее насыщенность цвета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представление RGB, предоставленные цвета HLS.  
  
### <a name="remarks"></a>Примечания  
 Цвет можно представить как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и яркость) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета, см. в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Этот метод и [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) метод выполнить те же операции, но требуется указывать другие значения для *H* параметра. В этом методе *H* — это значение в градусах от 0 до 360 градусов, представляющие обоих red. В [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) метод, *H* в процентах от круга. Например, с помощью `HLStoRGB_ONE`, значение 0,25 для *H* эквивалентен значение 90, с помощью `HLStoRGB_TWO`.  
  
##  <a name="hsvtorgb"></a>  CDrawingManager::HSVtoRGB  
 Преобразует цвет из представления HSV в RGB.  
  
```  
static COLORREF __stdcall HSVtoRGB(
    double H,  
    double S,  
    double V);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] *H*|Число от 0 до 360, указывающее оттенок цвета.|  
|[in] *S*|Число от 0 до 1, указывающее насыщенность цвета.|  
|[in] *V*|Число от 0 до 1, определяющее значение цвета.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представление RGB, предоставленные цвета HSV.  
  
### <a name="remarks"></a>Примечания  
 Цвет можно представить как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и яркость) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета, см. в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
##  <a name="huetorgb"></a>  CDrawingManager::HuetoRGB  
 Преобразует значение оттенка красного, зеленого или синего компонента.  
  
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
 [in] *m1*  
 См. заметки.  
  
 [in] *m2*  
 См. заметки.  
  
 [in] *h*  
 См. заметки.  
  
 [in] *rm1*  
 См. заметки.  
  
 [in] *rm2*  
 См. заметки.  
  
 [in] *rh*  
 См. заметки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отдельные красного, зеленого или синего компонента для указанного цветового тона.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является вспомогательным методом, `CDrawingManager` класс использует для вычисления отдельных красного, зеленого и синего компонентов цвета в представление HSV или HSL. Этот метод не предназначен для вызова непосредственно в программу самим разработчиком. Входные параметры являются значения, которые зависят от алгоритма преобразования.  
  
 Чтобы преобразовать цвет HSV или HSL в представление RGB, вызовите один из следующих методов:  
  
- [CDrawingManager::HSVtoRGB](#hsvtorgb)  
  
- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)  
  
- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)  
  
##  <a name="mirrorrect"></a>  CDrawingManager::MirrorRect  
 Зеркальное отражение прямоугольной области.  
  
```  
void MirrorRect(
    CRect rect,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rect*  
 Ограничивающий прямоугольник области, чтобы отразить.  
  
 [in] *bHorz*  
 Логический параметр, указывает ли прямоугольник зеркальное отражение по горизонтали или по вертикали.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно перевернуть любую область контекста устройства, принадлежащие `CDrawingManager` класса. Если *bHorz* имеет значение TRUE, этот метод горизонтальное зеркальное отражение области. В противном случае он переворачивается области по вертикали.  
  
##  <a name="pixelalpha"></a>  CDrawingManager::PixelAlpha  
 Вычисляет конечный цвет для полупрозрачные компоненты пикселя.  
  
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
 [in] *srcPixel*  
 Начальный цвет пикселя.  
  
 [in] *процентов*  
 Число, представляющее процент прозрачности от 0 до 100. Значение 100 указывает, что цвет полностью прозрачен.  
  
 [in] *percentR*  
 Число, представляющее процент прозрачности для красного компонента от 0 до 100.  
  
 [in] *percentG*  
 Число, представляющее процент прозрачности для зеленого компонента от 0 до 100.  
  
 [in] *percentB*  
 Число, представляющее процент прозрачности для синего компонента от 0 до 100.  
  
 [in] *dstPixel*  
 Базовый цвет пикселя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Конечный цвет для полупрозрачные компоненты пикселя.  
  
### <a name="remarks"></a>Примечания  
 Это — это вспомогательный класс для выделения цветом полупрозрачные компоненты точечные рисунки и не предназначен для вызова непосредственно в программу самим разработчиком.  
  
 При использовании версии метода, который имеет *dstPixel*, окончательный цвет представляет собой сочетание *dstPixel* и *srcPixel*. *SrcPixel* цвет является частично прозрачный цвет через базовый цвет *dstPixel*.  
  
##  <a name="prepareshadowmask"></a>  CDrawingManager::PrepareShadowMask  
 Создает точечный рисунок, который можно использовать в качестве тень.  
  
```  
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,  
    COLORREF clrBase,  
    int iMinBrightness = 0,  
    int iMaxBrightness = 100);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nDepth*  
 Ширина и высота тени.  
  
 [in] *clrBase*  
 Цвет тени.  
  
 [in] *iMinBrightness*  
 Минимальное яркость тени.  
  
 [in] *iMaxBrightness*  
 Максимальное яркость тени.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для созданного точечного рисунка, если этот метод выполнен успешно; в противном случае имеет значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Если *nDepth* имеет значение 0, этот метод завершает работу и возвращает значение NULL. Если *nDepth* меньше 3, ширина и высота тени равным 3 пикселя.  
  
##  <a name="rgbtohsl"></a>  CDrawingManager::RGBtoHSL  
 Преобразует цвет из красного, зеленого и синего (RGB) представления тона, насыщенности и представление освещенность (HSL)).  
  
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
|Параметр|Описание:|  
|[in] *rgb*|Цвет RGB-значения.|  
|[out] *H*|Указатель на значение типа double, где метод хранит оттенок цвета.|  
|[out] *S*|Указатель на значение типа double, где метод хранит насыщенность цвета.|  
|[out] *L*|Указатель на значение типа double, где метод хранит яркость выбранного цвета.|  
  
### <a name="remarks"></a>Примечания  
 Цвет можно представить как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и яркость) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета, см. в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Возвращаемое значение для *H* представляется в виде дробного числа от 0 до 1, где 0 и 1 представляют красный. Возвращаемые *S* и *L* являются числами от 0 до 1.  
  
##  <a name="rgbtohsv"></a>  CDrawingManager::RGBtoHSV  
 Преобразует цвета из RGB представления в HSV.  
  
```  
static void __stdcall RGBtoHSV(
    COLORREF rgb,  
    double* H,  
    double* S,  
    double* V);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rgb*  
 Цвет для преобразования в представление RGB.  
  
 [out] *H*  
 Указатель на значение типа double, где этот метод сохраняет результирующий оттенок цвета.  
  
 [out] *S*  
 Указатель на значение типа double, где этот метод сохраняет результирующий насыщенность цвета.  
  
 [out] *V*  
 Указатель на значение типа double, где этот метод сохраняет полученное значение цвета.  
  
### <a name="remarks"></a>Примечания  
 Цвет можно представить как HSV (оттенок, насыщенность и значение), HSL (оттенок, насыщенность и яркость) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета, см. в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Возвращаемое значение для *H* — это число от 0 до 360, где 0 до 360 градусов указать red. Возвращаемые значения для *S* и *V* являются числами от 0 до 1.  
  
##  <a name="setalphapixel"></a>  CDrawingManager::SetAlphaPixel  
 Цвет прозрачным пикселя в точечном рисунке.  
  
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
 [in] *pBits*  
 Указатель на битовые значения для растрового изображения.  
  
 [in] *rect*  
 Прямоугольная область в приложении. Диспетчер рисования рисует тень снизу и справа от этой области.  
  
 [in] *x*  
 Горизонтальная координата пикселя к цвету.  
  
 [in] *y*  
 Вертикальная координата пикселя к цвету.  
  
 [in] *процентов*  
 Процент прозрачности.  
  
 [in] *iShadowSize*  
 Ширина и высота тени.  
  
 [in] *clrBase*  
 Цвет тени.  
  
 [in] *bIsRight*  
 Логический параметр, который указывает, какой пиксел цвет. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Этот метод — это вспомогательный метод, который используется [CDrawingManager::DrawShadow](#drawshadow) метод. Мы рекомендуем, чтобы нарисовать тень, вызывающих `CDrawingManager::DrawShadow` вместо этого.  
  
 Если *bIsRight* имеет значение TRUE, измеряется на цвет пикселя *x* пикселей от правого края *rect*. Если он имеет значение FALSE, измеряется на цвет пикселя *x* пикселей правее левой границы *rect*.  
  
##  <a name="setpixel"></a>  CDrawingManager::SetPixel  
 Изменение на указанный цвет одного пикселя в точечном рисунке.  
  
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
|Параметр|Описание:|  
|[in] *pBits*|Указатель на битовые значения растрового изображения.|  
|[in] *cx*|Общая ширина растрового изображения.|  
|[in] *cy*|Общая высота растрового изображения.|  
|[in] *x*|Координата x пикселя в точечном рисунке для изменения.|  
|[in] *y*|Координата по оси y пикселя в точечном рисунке для изменения.|  
|[in] *цвет*|Новый цвет пикселя, с предоставленным координатами.|  
  
##  <a name="smartmixcolors"></a>  CDrawingManager::SmartMixColors  
 Объединяет два цвета на основе взвешенных коэффициента.  
  
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
|Параметр|Описание:|  
|[in] *color1*|Первый цвет смешивания.|  
|[in] *цвет2*|Второй цвет смешивания.|  
|[in] *dblLumRatio*|Отношение для нового цвета яркость. `SmartMixColors` Умножает яркость цвета смешанной перед определением окончательный цвет этого отношения.|  
|[in] *k1*|Взвешенное отношение для первого цвета.|  
|[in] *k2*|Взвешенное отношение для второй цвет.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет, который представляет взвешенного сочетание указанного цвета.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается с ошибкой, если параметр *k1* или *k2* меньше нуля. Если оба этих параметра имеют значение 0, то метод возвращает `RGB(0, 0, 0)`.  
  
 Взвешенное отношение вычисляется по следующей формуле: (color1 \* k1 + цвет2 \* k2) /(k1 + k2). После определения коэффициент взвешенного метода вычисляет яркость смешанной цвета. Затем она умножает яркость, *dblLumRatio*. Если значение больше, чем 1.0, метод устанавливает яркость цвета смешанной новое значение. В противном случае яркость имеет значение 1.0.  
  
##  <a name="drawrotated"></a>  CDrawingManager::DrawRotated  
 Поворачивает источником постоянного ТОКА содержимое внутри заданного прямоугольника на 90 градусов.  
  
```  
void DrawRotated(
    CRect rectDest,  
    CDC& dcSrc,  
    BOOL bClockWise);
```  
  
### <a name="parameters"></a>Параметры  
 *rectDest*  
 Прямоугольник назначения.  
  
 *dcSrc*  
 Контекст исходного устройства.  
  
 *bClockWise*  
 Значение TRUE указывает поворота 90 градусов; Значение FALSE указывает поворот-90 градусов.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
