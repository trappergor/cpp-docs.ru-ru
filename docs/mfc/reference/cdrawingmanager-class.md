---
title: "Класс CDrawingManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 689d538c03a35175040663aedb7bd6130aae10fd
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
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
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|Создает 32-разрядных аппаратно независимый точечный рисунок (DIB), приложения могут выполнять запись напрямую.|  
|[CDrawingManager::DrawAlpha](#drawalpha)|Отображает растровых изображений, имеющих пикселей прозрачным или полупрозрачным.|  
|[CDrawingManager::DrawRotated](#drawrotated)|Поворачивает исходного контроллера домена содержимое внутри данного прямоугольника по +/-90 градусов|  
|[CDrawingManager::DrawEllipse](#drawellipse)|Рисует эллипс, предоставленных цветами, заполнения и границы.|  
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Рисует кольцо и заполняет его с цветным градиентом.|  
|[CDrawingManager::DrawLine CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Проводит линию.|  
|[CDrawingManager::DrawRect](#drawrect)|Рисование прямоугольника с помощью предоставленного цвета заливки и границы.|  
|[CDrawingManager::DrawShadow](#drawshadow)|Рисует тень для прямоугольной области.|  
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|Заполняет прямоугольную область два цвета градиента.|  
|[CDrawingManager::FillGradient](#fillgradient)|Заполняет указанный цвет градиента прямоугольной области.|  
|[CDrawingManager::FillGradient2](#fillgradient2)|Заполняет указанный цвет градиента прямоугольной области. Также указывается направление изменение цвета градиента.|  
|[CDrawingManager::GrayRect](#grayrect)|Заполняет указанный серый цвет прямоугольника.|  
|[CDrawingManager::HighlightRect](#highlightrect)|Выделяет прямоугольной области.|  
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Преобразует цвет из представления HLS в RGB.|  
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Преобразует цвет из представления HLS в RGB.|  
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Преобразует цвет из представления HSV в RGB.|  
|[CDrawingManager::HuetoRGB](#huetorgb)|Вспомогательный метод, который преобразует значение оттенка красного, зеленого или синего компонента.|  
|[CDrawingManager::MirrorRect](#mirrorrect)|Зеркальное отражение прямоугольной области.|  
|[CDrawingManager::PixelAlpha](#pixelalpha)|Вспомогательный метод, который определяет конечный цвет для полупрозрачными пикселей.|  
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Создает точечного рисунка, который можно использовать в качестве тень.|  
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Преобразует цвет из представления RGB в HSL.|  
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Преобразует цвет из представления RGB в HSV.|  
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Вспомогательный метод, который сделает полупрозрачные пикселя в точечном рисунке.|  
|[CDrawingManager::SetPixel](#setpixel)|Вспомогательный метод, что изменения одной точки в точечном рисунке указанным цветом.|  
|[CDrawingManager::SmartMixColors](#smartmixcolors)|Объединяет два цвета на основе взвешенных коэффициента.|  
  
## <a name="remarks"></a>Примечания  
 `CDrawingManager` Класс предоставляет функции для рисования тени, цветовые градиенты и выделенные прямоугольники. Он также выполняет альфа смешения. Этот класс можно использовать для непосредственного изменения пользовательского интерфейса приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
 `CDrawingManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdrawmanager.h  
  
##  <a name="cdrawingmanager"></a>CDrawingManager::CDrawingManager  
 Создает [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) объекта.  
  
```  
CDrawingManager(CDC& dc);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dc`  
 Ссылка на контекст устройства. `CDrawingManager` Использует этот контекст для рисования.  
  
##  <a name="createbitmap_32"></a>CDrawingManager::CreateBitmap_32  
 Создает 32-разрядных аппаратно независимый точечный рисунок (DIB), приложения могут выполнять запись напрямую.  
  
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
|[in] `size`|Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) параметра, который определяет размер растрового изображения.|  
|[выходной] `pBits`|Указатель на указатель на данные, который получает расположение DIB-разрядных значений.|  
|`bitmap`|Дескриптор для исходного растрового изображения|  
|`clrTransparent`|Значение RGB, указав прозрачный цвет исходного растрового изображения.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор вновь созданного точечного DIB, если этот метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о способах создания растрового изображения DIB см. в разделе [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183491).  
  
##  <a name="drawalpha"></a>CDrawingManager::DrawAlpha  
 Отображает растровых изображений, имеющих пикселей прозрачным или полупрозрачным.  
  
```  
void DrawAlpha(
    CDC* pDstDC,  
    const CRect& rectDst,  
    CDC* pSrcDC,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDstDC`  
 Указатель на контекст устройства для назначения.  
  
 [in] `rectDst`  
 Прямоугольника назначения.  
  
 [in] `pSrcDC`  
 Указатель на контекст устройства для источника.  
  
 [in] `rectSrc`  
 Исходного прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет альфа смешения для двух растровых изображений. Дополнительные сведения о альфа смешения см. в разделе [AlphaBlend](http://msdn.microsoft.com/library/windows/desktop/dd183351) в Windows SDK.  
  
##  <a name="drawellipse"></a>CDrawingManager::DrawEllipse  
 Рисует эллипс, предоставленных цветами, заполнения и границы.  
  
```  
void DrawEllipse(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Ограничивающий прямоугольник для эллипса.  
  
 [in] `clrFill`  
 Цвет, который использует этот метод для заполнения эллипса.  
  
 [in] `clrLine`  
 Цвет, этот метод использует в качестве границы эллипса.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращается без Рисование эллипса, если любой цвет задан равным -1. Он также возвращает без Рисование эллипса 0 в случае любого размера, ограничивающего прямоугольника.  
  
##  <a name="drawgradientring"></a>CDrawingManager::DrawGradientRing  
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
 [in] `rect`  
 Объект [CRect](../../atl-mfc-shared/reference/crect-class.md) параметр, который определяет границы для градиента кольца.  
  
 [in] `colorStart`  
 Первый цвет градиента.  
  
 [in] `colorFinish`  
 Последний цвет градиента.  
  
 [in] `colorBorder`  
 Цвет границы.  
  
 [in] `nAngle`  
 Параметр, который определяет начальный угол градиентной рисования. Это значение должно быть в диапазоне от 0 до 360.  
  
 [in] `nWidth`  
 Ширина границы для кольца.  
  
 [in] `clrFace`  
 Цвет внутреннего кольца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник, определяемый `rect` должен быть по крайней мере 5 точек и шириной в 5 пикселей в высоту.  
  
##  <a name="drawline_cdrawingmanager__drawlinea"></a>CDrawingManager::DrawLine CDrawingManager::DrawLineA  
 Проводит линию.  
  
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
|[in] `x1`|Координата x, с которой начинается строка.|  
|[in] `y1`|Координата y, с которой начинается строка.|  
|[in] `x2`|Координата x, где строка завершается.|  
|[in] `y2`|Координата y, где строка завершается.|  
|[in] `clrLine`|Цвет линии.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если `clrLine` равно -1.  
  
##  <a name="drawrect"></a>CDrawingManager::DrawRect  
 Рисование прямоугольника с помощью предоставленного цвета заливки и границы.  
  
```  
void DrawRect(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Границы для прямоугольника.  
  
 [in] `clrFill`  
 Цвет, который использует этот метод для заполнения прямоугольника.  
  
 [in] `clrLine`  
 Цвет, этот метод использует для границы прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращается без Рисование прямоугольника, если любой цвет задан равным -1. Он также возвращает, если измерения, либо прямоугольника равен 0.  
  
##  <a name="drawshadow"></a>CDrawingManager::DrawShadow  
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
 [in] `rect`  
 Прямоугольная область в приложении. Рисование manager будет нарисовать тень под этой области.  
  
 [in] `nDepth`  
 Ширина и высота тени.  
  
 [in] `iMinBrightness`  
 Минимальная яркости тени.  
  
 [in] `iMaxBrightness`  
 Максимальная яркость тени.  
  
 [in] `pBmpSaveBottom`  
 Указатель точечного рисунка, который содержит изображение, чтобы в нижней части тени.  
  
 [in] `pBmpSaveRight`  
 Указатель точечного рисунка, который содержит изображение, чтобы тени, рисуется с правой стороны прямоугольника.  
  
 [in] `clrBase`  
 Цвет тени.  
  
 [in] `bRightShadow`  
 Логический параметр, указывает способ рисования тени. Если `bRightShadow` — `TRUE`, `DrawShadow` рисует тень правой стороны прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 С помощью параметров можно предоставить два допустимых растровые изображения для нижнего и правого shadows `pBmpSaveBottom` и `pBmpSaveRight`. Если эти [CBitmap](../../mfc/reference/cbitmap-class.md) объекты имеют присоединяемый объект GDI `DrawShadow` будет использовать эти растровых изображений как тени. Если `CBitmap` параметры не имеют присоединяемый объект GDI `DrawShadow` рисует тень и присоединяет точечных рисунков с параметрами. В последующих вызовов `DrawShadow`, вы можете предоставить эти битовые карты, чтобы ускорить процесс рисования. Дополнительные сведения о `CBitmap` классов и объекты GDI, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
 Если выполняется любое из этих параметров `NULL`, `DrawShadow` автоматически будет отрисовка теней.  
  
 Если задать `bRightShadow` для `FALSE`, снизу и слева от прямоугольной области, будут отрисовываться тени.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `DrawShadow` метод `CDrawingManager` класса. Этот фрагмент кода является частью [Prop лист демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]  
  
##  <a name="fill4colorsgradient"></a>CDrawingManager::Fill4ColorsGradient  
 Заполняет прямоугольную область два цвета градиента.  
  
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
 [in] `rect`  
 Прямоугольник для заливки.  
  
 [in] `colorStart1`  
 Цвет для цветового градиента первой.  
  
 [in] `colorFinish1`  
 Конечный цвет для первый цвет градиента.  
  
 [in] `colorStart2`  
 Цвет для второй цвет градиента.  
  
 [in] `colorFinish2`  
 Конечный цвет для второй цвет градиента.  
  
 [in] `bHorz`  
 Логический параметр, указывает ли `Fill4ColorsGradient` горизонтальный или Вертикальный градиент цветов. `TRUE`Указывает горизонтальный градиент.  
  
 [in] `nPercentage`  
 Целое число от 0 до 100. Это значение указывает процент прямоугольника для заливки с первый цвет градиента.  
  
### <a name="remarks"></a>Примечания  
 При заполнении прямоугольник с двумя цветовые градиенты, они расположены выше друг с другом либо Далее друг на друга в зависимости от значения `bHorz`. Каждый цвет градиента вычисляется независимо друг от друга с помощью метода [CDrawingManager::FillGradient](#fillgradient).  
  
 Если этот метод создает Сбой утверждения `nPercentage` меньше 0 или больше 100.  
  
##  <a name="fillgradient"></a>CDrawingManager::FillGradient  
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
 [in] `rect`  
 Прямоугольная область для заливки.  
  
 [in] `colorStart`  
 Первый цвет градиента.  
  
 [in] `colorFinish`  
 Последний цвет градиента.  
  
 [in] `bHorz`  
 Логический параметр, указывает ли `FillGradient` отображать горизонтального или вертикального градиента.  
  
 [in] `nStartFlatPercentage`  
 Процент прямоугольника, `FillGradient` заполняет `colorStart` перед началом градиента.  
  
 [in] `nEndFlatPercentage`  
 Процент прямоугольника, `FillGradient` заполняет `colorFinish` после ее завершения градиента.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `FillGradient` метод `CDrawingManager` класса. Этот фрагмент кода является частью [MS Office 2007 демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]  
  
##  <a name="fillgradient2"></a>CDrawingManager::FillGradient2  
 Заполняет указанный цвет градиента прямоугольной области.  
  
```  
void FillGradient2 (
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    int nAngle = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Прямоугольная область для заливки.  
  
 [in] `colorStart`  
 Первый цвет градиента.  
  
 [in] `colorFinish`  
 Последний цвет градиента.  
  
 [in] `nAngle`  
 Целое число от 0 до 360. Этот параметр задает направление цветового градиента.  
  
### <a name="remarks"></a>Примечания  
 Используйте `nAngle` для указания направления цветового градиента. При указании направление цвет градиента, можно также указать начало градиента. Значение 0 для `nAngle` указывает градиента начинается от верхней стороны прямоугольника. Как `nAngle` увеличивается, начальное положение для градиента перемещается в направлении против часовой стрелки на основе углов.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `FillGradient2` метод `CDrawingManager` класса. Этот фрагмент кода является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]  
  
##  <a name="grayrect"></a>CDrawingManager::GrayRect  
 Заполняет указанный серый цвет прямоугольника.  
  
```  
BOOL GrayRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    COLORREF clrDisabled = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Прямоугольная область для заливки.  
  
 [in] `nPercentage`  
 Процент серого в прямоугольник.  
  
 [in] `clrTransparent`  
 Прозрачный цвет.  
  
 [in] `clrDisabled`  
 Цвет, который использует этот метод для отмены насыщенности, если `nPercentage` имеет значение -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Для параметра `nPercentage`, более низкое значение указывает более темным цветом.  
  
 Максимальное значение для `nPercentage` равно 200. Значение больше, чем 200 не изменяет внешний вид прямоугольника. Если значение равно -1, этот метод использует `clrDisabled` для ограничения насыщенность прямоугольника.  
  
##  <a name="highlightrect"></a>CDrawingManager::HighlightRect  
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
 [in] `rect`  
 Прямоугольная область, чтобы выделить.  
  
 [in] `nPercentage`  
 Процент, на который указывает степень прозрачности выделения.  
  
 [in] `clrTransparent`  
 Прозрачный цвет.  
  
 [in] `nTolerance`  
 Целое число от 0 до 255, указывающее допустимое значение цвета.  
  
 [in] `clrBlend`  
 Базовый цвет для наложения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если `nPercentage` находится в диапазоне от 0 до 99, `HighlightRect` использует альфа-смешения алгоритма. Дополнительные сведения о альфа-смешение см. в разделе [альфа смешение цвета для линий и заливок](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills). Если `nPercentage` равно -1, этот метод использует уровень выделения по умолчанию. Если `nPercentage` — 100, этот метод не выполняет никаких действий и возвращает `TRUE`.  
  
 Метод использует параметр `nTolerance` для определения необходимости выделите прямоугольной области. Чтобы выделить прямоугольник разницу между цвет фона для приложения и `clrTransparent` должно быть меньше, чем `nTolerance` в каждом компоненте цвета (красный, зеленый и синий).  
  
##  <a name="hlstorgb_one"></a>CDrawingManager::HLStoRGB_ONE  
 Преобразует цвет из представления HLS в RGB.  
  
```  
static COLORREF __stdcall HLStoRGB_ONE(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `H`  
 Число от 0 до 1, представляющее оттенок цвета.  
  
 [in] `L`  
 Число от 0 до 1, указывающее, яркость цвета.  
  
 [in] `S`  
 Число от 0 до 1, указывающее, насыщенность цвета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представление RGB предоставленный цвета HLS.  
  
### <a name="remarks"></a>Примечания  
 Цвета могут быть представлены как HSV (цветового тона, насыщенности и значение), HSL (цветового тона, насыщенности и яркости) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Этот метод и `CDrawingManager::HLStoRGB_TWO` метод выполнить ту же операцию, но требуется указывать другие значения для `H` параметра. В этом методе `H` в процентах от круга. В `CDrawingManager::HLStoRGB_TWO` метода `H` имеет значение в градусах от 0 до 360 градусов, для которых представляют красный. Например, с помощью `HLStoRGB_ONE`, значение 0,25 для `H` эквивалентен значению 90 с `HLStoRGB_TWO`.  
  
##  <a name="hlstorgb_two"></a>CDrawingManager::HLStoRGB_TWO  
 Преобразует цвет из представления HLS в RGB.  
  
```  
static COLORREF __stdcall HLStoRGB_TWO(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `H`  
 Число от 0 до 360, представляющее оттенок цвета.  
  
 [in] `L`  
 Число от 0 до 1, указывающее, яркость цвета.  
  
 [in] `S`  
 Число от 0 до 1, указывающее, насыщенность цвета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представление RGB предоставленный цвета HLS.  
  
### <a name="remarks"></a>Примечания  
 Цвета могут быть представлены как HSV (цветового тона, насыщенности и значение), HSL (цветового тона, насыщенности и яркости) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Этот метод и [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) метод выполнить ту же операцию, но требуется указывать другие значения для `H` параметра. В этом методе `H` имеет значение в градусах от 0 до 360 градусов, для которых представляют красный. В [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) метода `H` в процентах от круга. Например, с помощью `HLStoRGB_ONE`, значение 0,25 для `H` эквивалентен значению 90 с `HLStoRGB_TWO`.  
  
##  <a name="hsvtorgb"></a>CDrawingManager::HSVtoRGB  
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
|[in] `H`|Число от 0 до 360, указывающее оттенок цвета.|  
|[in] `S`|Число от 0 до 1, указывающее, насыщенность цвета.|  
|[in] `V`|Число от 0 до 1, которое указывает значение цвета.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представление RGB указанный цвет HSV.  
  
### <a name="remarks"></a>Примечания  
 Цвета могут быть представлены как HSV (цветового тона, насыщенности и значение), HSL (цветового тона, насыщенности и яркости) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
##  <a name="huetorgb"></a>CDrawingManager::HuetoRGB  
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
 [in] `m1`  
 См. заметки.  
  
 [in] `m2`  
 См. заметки.  
  
 [in] `h`  
 См. заметки.  
  
 [in] `rm1`  
 См. заметки.  
  
 [in] `rm2`  
 См. заметки.  
  
 [in] `rh`  
 См. заметки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отдельные красного, зеленого и синего компонентов компонент для предоставленного цветовой тон.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является вспомогательным методом, `CDrawingManager` класс использует для отдельных компонентов красного, зеленого и синего цвета в иерархической структуре HSV или HSL вычисления. Этот метод предназначен не должна вызываться напрямую программиста. Входные параметры являются значениями, которые зависят от алгоритма преобразования.  
  
 Чтобы преобразовать HSV или HSL цвета RGB представление, вызовите один из следующих методов:  
  
- [CDrawingManager::HSVtoRGB](#hsvtorgb)  
  
- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)  
  
- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)  
  
##  <a name="mirrorrect"></a>CDrawingManager::MirrorRect  
 Зеркальное отражение прямоугольной области.  
  
```  
void MirrorRect(
    CRect rect,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Ограничивающий прямоугольник области, чтобы отразить.  
  
 [in] `bHorz`  
 Логический параметр, указывает ли прямоугольник зеркальное отражение, горизонтально или вертикально.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно отразить любую область контекста устройства, принадлежащие `CDrawingManager` класса. Если `bHorz` равно `TRUE`, этот метод горизонтальное зеркальное отражение области. В противном случае он Вертикальное зеркальное отражение области.  
  
##  <a name="pixelalpha"></a>CDrawingManager::PixelAlpha  
 Вычисляет окончательный цвет полупрозрачными пиксель.  
  
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
 [in] `srcPixel`  
 Начальный цвет пикселя.  
  
 [in] `percent`  
 Число от 0 до 100, представляющее процент прозрачности. Значение 100 указывает, что начальный цвет является полностью прозрачным.  
  
 [in] `percentR`  
 Число, представляющее процент прозрачности для красного компонента от 0 до 100.  
  
 [in] `percentG`  
 Число, представляющее процент прозрачности для зеленого компонента от 0 до 100.  
  
 [in] `percentB`  
 Число, представляющее процент прозрачности для синего компонента от 0 до 100.  
  
 [in] `dstPixel`  
 Базовый цвет пикселя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Конечный цвет для полупрозрачными пикселей.  
  
### <a name="remarks"></a>Примечания  
 — Это вспомогательный класс для выделения цветом полупрозрачными растровые изображения и не предназначен для вызова непосредственно программистом.  
  
 При использовании версии метода, который имеет `dstPixel`, окончательный цвет представляет собой сочетание `dstPixel` и `srcPixel`. `srcPixel` Цвет является частично прозрачный цвет через базовый цвет `dstPixel`.  
  
##  <a name="prepareshadowmask"></a>CDrawingManager::PrepareShadowMask  
 Создает точечного рисунка, который можно использовать в качестве тень.  
  
```  
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,  
    COLORREF clrBase,  
    int iMinBrightness = 0,  
    int iMaxBrightness = 100);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nDepth`  
 Ширина и высота тени.  
  
 [in] `clrBase`  
 Цвет тени.  
  
 [in] `iMinBrightness`  
 Минимальная яркости тени.  
  
 [in] `iMaxBrightness`  
 Максимальная яркость тени.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для созданного точечного рисунка, если этот метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если `nDepth` задано значение 0, этот метод завершает работу и возвращает `NULL`. Если `nDepth` меньше 3, ширину и высоту тени равным 3 пикселей.  
  
##  <a name="rgbtohsl"></a>CDrawingManager::RGBtoHSL  
 Преобразует цвет из представления красного, зеленого и синего (RGB) цветового тона, насыщенности и яркости (HSL) представление.  
  
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
|[in] `rgb`|С цветом RGB-значения.|  
|[выходной] `H`|Указатель на значение типа double, где метод сохраняет оттенок цвета.|  
|[выходной] `S`|Указатель на значение типа double, где метод сохраняет насыщенность цвета.|  
|[выходной] `L`|Указатель на значение типа double, где метод сохраняет яркости цвета.|  
  
### <a name="remarks"></a>Примечания  
 Цвета могут быть представлены как HSV (цветового тона, насыщенности и значение), HSL (цветового тона, насыщенности и яркости) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Возвращаемое значение для `H` представляется в виде дробного числа от 0 и 1, где 0 и 1 представляют красный. Возвращаемые `S` и `L` являются числами от 0 до 1.  
  
##  <a name="rgbtohsv"></a>CDrawingManager::RGBtoHSV  
 Преобразует цвет из представления RGB в HSV.  
  
```  
static void __stdcall RGBtoHSV(
    COLORREF rgb,  
    double* H,  
    double* S,  
    double* V);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rgb`  
 Цвет для преобразования в представление RGB.  
  
 [выходной] `H`  
 Указатель на значение типа double, где этот метод сохраняет полученный оттенок цвета.  
  
 [выходной] `S`  
 Указатель на значение типа double, где этот метод сохраняет полученный насыщенность цвета.  
  
 [выходной] `V`  
 Указатель на значение типа double, где этот метод сохраняет полученное значение цвета.  
  
### <a name="remarks"></a>Примечания  
 Цвета могут быть представлены как HSV (цветового тона, насыщенности и значение), HSL (цветового тона, насыщенности и яркости) или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Возвращаемое значение для `H` , число от 0 до 360 градусов, где 0 до 360 градусов указать красный. Возвращаемые значения для `S` и `V` являются числами от 0 до 1.  
  
##  <a name="setalphapixel"></a>CDrawingManager::SetAlphaPixel  
 Цвет прозрачной пикселя в точечном рисунке.  
  
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
 [in] `pBits`  
 Указатель на битовые значения для битовой карты.  
  
 [in] `rect`  
 Прямоугольная область в приложении. Рисование manager рисует тень снизу и справа от этой области.  
  
 [in] `x`  
 Горизонтальная координата цвет пикселя.  
  
 [in] `y`  
 Вертикальная координата цвет пикселя.  
  
 [in] `percent`  
 Процент прозрачности.  
  
 [in] `iShadowSize`  
 Ширина и высота тени.  
  
 [in] `clrBase`  
 Цвет тени.  
  
 [in] `bIsRight`  
 Логический параметр, указывающий пикселей, какой цвет. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Этот метод — это вспомогательный метод, который используется [CDrawingManager::DrawShadow](#drawshadow) метод. Корпорация Майкрософт рекомендует, чтобы нарисовать тень, вызывающих `CDrawingManager::DrawShadow` вместо него.  
  
 Если `bIsRight` равно `TRUE`, цвет пикселя измеряется `x` пикселей от правого края `rect`. Если это `FALSE`, цвет пикселя измеряется `x` пикселей от левого края `rect`.  
  
##  <a name="setpixel"></a>CDrawingManager::SetPixel  
 Изменение одной точки в точечном рисунке указанный цвет.  
  
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
|[in] `pBits`|Указатель на значения битов битовой карты.|  
|[in] `cx`|Общая ширина растрового изображения.|  
|[in] `cy`|Общая высота растрового изображения.|  
|[in] `x`|Координата x точки в битовой карте для изменения.|  
|[in] `y`|Координата y точки в битовой карте для изменения.|  
|[in] `color`|Новый цвет пикселя, с координатами предоставленного.|  
  
##  <a name="smartmixcolors"></a>CDrawingManager::SmartMixColors  
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
|[in] `color1`|Первый цвет смешивания.|  
|[in] `color2`|Второй цвет смешивания.|  
|[in] `dblLumRatio`|Соотношение яркость новый цвет. `SmartMixColors`Умножает яркость цвета смешанного перед определением окончательный цвет этого отношения.|  
|[in] `k1`|Взвешенное соотношение первый цвет.|  
|[in] `k2`|Взвешенное отношение для второй цвет.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет, представляющий взвешенного сочетание указанного цвета.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается с ошибкой, если параметр `k1` или `k2` меньше нуля. Если оба этих параметра имеют значение 0, то метод возвращает `RGB(0, 0, 0)`.  
  
 Взвешенное отношение рассчитывается по следующей формуле: (color1 * k1 + цвет2 \* k2) /(k1 + k2). После определения коэффициент взвешенного метода вычисляет яркость для смешанных цвета. Затем она умножает яркость с `dblLumRatio`. Если значение больше, чем 1.0, метод устанавливает яркость цвета смешанного новое значение. В противном случае яркость равно 1.0.  
  
##  <a name="drawrotated"></a>CDrawingManager::DrawRotated  
 Поворачивает исходного контроллера домена содержимое внутри данного прямоугольника на 90 градусов.  
  
```  
void DrawRotated(
    CRect rectDest,  
    CDC& dcSrc,  
    BOOL bClockWise);
```  
  
### <a name="parameters"></a>Параметры  
 `rectDest`  
 Прямоугольника назначения.  
  
 `dcSrc`  
 Контекст исходного устройства.  
  
 `bClockWise`  
 `TRUE`Указывает поворот + 90 градусов; `FALSE` указывает поворот-90 градусов.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
