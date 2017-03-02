---
title: "Класс CDrawingManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDrawingManager
dev_langs:
- C++
helpviewer_keywords:
- CDrawingManager class
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
caps.latest.revision: 30
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 53929fff6df57b4e5fe00572f8a7cec8a218c638
ms.lasthandoff: 02/24/2017

---
# <a name="cdrawingmanager-class"></a>Класс CDrawingManager
`CDrawingManager` Класс реализует сложные алгоритмы рисования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDrawingManager : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|Создает объект `CDrawingManager`.|  
|`CDrawingManager::~CDrawingManager`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|Создает 32-разрядных аппаратно независимые точечный рисунок (DIB), приложения могут записывать напрямую.|  
|[CDrawingManager::DrawAlpha](#drawalpha)|Отображает точечным рисункам, имеющим прозрачным или полупрозрачным пикселей.|  
|[CDrawingManager::DrawRotated](#drawrotated)|Поворачивает исходного контроллера домена содержимого внутри данного прямоугольника по +/-90 градусов|  
|[CDrawingManager::DrawEllipse](#drawellipse)|Рисование эллипса с предоставленным цвета заливки и границ.|  
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Рисует кольцо и заполняет его с цветным градиентом.|  
|[CDrawingManager::DrawLine CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Проводит линию.|  
|[CDrawingManager::DrawRect](#drawrect)|Рисование прямоугольника с предоставленным цвета заливки и границ.|  
|[CDrawingManager::DrawShadow](#drawshadow)|Рисует тень прямоугольной области.|  
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|Заполняет прямоугольную область два цвета градиента.|  
|[CDrawingManager::FillGradient](#fillgradient)|Заполняет указанный цвет градиента прямоугольной области.|  
|[CDrawingManager::FillGradient2](#fillgradient2)|Заполняет указанный цвет градиента прямоугольной области. Также задается направление изменение цвета градиента.|  
|[CDrawingManager::GrayRect](#grayrect)|Заполняет прямоугольник заданным серым цветом.|  
|[CDrawingManager::HighlightRect](#highlightrect)|Выделяет прямоугольную область.|  
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Преобразует цвет из представления HLS в формате RGB.|  
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Преобразует цвет из представления HLS в формате RGB.|  
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Преобразует цвет из представления HSV в формате RGB.|  
|[CDrawingManager::HuetoRGB](#huetorgb)|Вспомогательный метод, который преобразует значение оттенка красного, зеленого или синего компонента.|  
|[CDrawingManager::MirrorRect](#mirrorrect)|Зеркальное отражение прямоугольной области.|  
|[CDrawingManager::PixelAlpha](#pixelalpha)|Вспомогательный метод, который определяет конечный цвет для Полупрозрачная пикселей.|  
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Создает точечный рисунок, который можно использовать в качестве тень.|  
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Преобразует цвет из представления RGB в HSL.|  
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Преобразует цвет из представления RGB в HSV.|  
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Вспомогательный метод, который цвета частично прозрачных точек в точечном рисунке.|  
|[CDrawingManager::SetPixel](#setpixel)|Вспомогательный метод, который примет указанный цвет одной точки в точечном рисунке.|  
|[CDrawingManager::SmartMixColors](#smartmixcolors)|Объединяет два цвета на основе взвешенных коэффициента.|  
  
## <a name="remarks"></a>Примечания  
 `CDrawingManager` Класс предоставляет функции для рисования тени, цветовые градиенты и выделенные прямоугольники. Он также выполняет альфа смешения. Этот класс можно использовать для непосредственного изменения пользовательского интерфейса приложения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
 `CDrawingManager`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdrawmanager.h  
  
##  <a name="a-namecdrawingmanagera--cdrawingmanagercdrawingmanager"></a><a name="cdrawingmanager"></a>CDrawingManager::CDrawingManager  
 Создает [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) объекта.  
  
```  
CDrawingManager(CDC& dc);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dc`  
 Ссылка на контекст устройства. `CDrawingManager` Использует этот контекст для рисования.  
  
##  <a name="a-namecreatebitmap32a--cdrawingmanagercreatebitmap32"></a><a name="createbitmap_32"></a>CDrawingManager::CreateBitmap_32  
 Создает 32-разрядных аппаратно независимые точечный рисунок (DIB), приложения могут записывать напрямую.  
  
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
|[in] `size`|Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) параметр, указывающий размер точечного рисунка.|  
|[выходной] `pBits`|Значения битов в указатель на указатель на данные, принимающий расположение DIB.|  
|`bitmap`|Дескриптор для исходного растрового изображения|  
|`clrTransparent`|Значение RGB, указав прозрачный цвет исходного растрового изображения.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор вновь созданного точечного DIB, если этот метод выполнен успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о способах создания растрового изображения DIB см. в разделе [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183491).  
  
##  <a name="a-namedrawalphaa--cdrawingmanagerdrawalpha"></a><a name="drawalpha"></a>CDrawingManager::DrawAlpha  
 Отображает точечным рисункам, имеющим прозрачным или полупрозрачным пикселей.  
  
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
 Прямоугольник назначения.  
  
 [in] `pSrcDC`  
 Указатель на контекст устройства для источника.  
  
 [in] `rectSrc`  
 Исходного прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет альфа смешения для двух растровых изображений. Дополнительные сведения о альфа смешения. в разделе [AlphaBlend](http://msdn.microsoft.com/library/windows/desktop/dd183351) в Windows SDK.  
  
##  <a name="a-namedrawellipsea--cdrawingmanagerdrawellipse"></a><a name="drawellipse"></a>CDrawingManager::DrawEllipse  
 Рисование эллипса с предоставленным цвета заливки и границ.  
  
```  
void DrawEllipse(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Ограничивающий прямоугольник, эллипс.  
  
 [in] `clrFill`  
 Цвет, который использует этот метод для рисования эллипса.  
  
 [in] `clrLine`  
 Цвет, этот метод использует в качестве границы эллипса.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращается без Рисование эллипса, если любого цвета равно-1. Он также возвращает без Рисование эллипса 0 в случае любого размера, ограничивающего прямоугольника.  
  
##  <a name="a-namedrawgradientringa--cdrawingmanagerdrawgradientring"></a><a name="drawgradientring"></a>CDrawingManager::DrawGradientRing  
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
 Объект [CRect](../../atl-mfc-shared/reference/crect-class.md) параметр, который задает границы для градиента кольца.  
  
 [in] `colorStart`  
 Первый цвет градиента.  
  
 [in] `colorFinish`  
 Последний цвет градиента.  
  
 [in] `colorBorder`  
 Цвет границы.  
  
 [in] `nAngle`  
 Параметр, который задает начальный угол градиента рисования. Это значение должно быть в диапазоне от 0 до 360.  
  
 [in] `nWidth`  
 Ширина границы для кольца.  
  
 [in] `clrFace`  
 Цвет внутренней кольца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Прямоугольник, определяемый `rect` должен быть по крайней мере 5 пикселов шириной и 5 пикселов в высоту.  
  
##  <a name="a-namedrawlinecdrawingmanagerdrawlineaa--cdrawingmanagerdrawline-cdrawingmanagerdrawlinea"></a><a name="drawline_cdrawingmanager__drawlinea"></a>CDrawingManager::DrawLine CDrawingManager::DrawLineA  
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
|Параметр|Описание|  
|[in] `x1`|Координата x, с которой начинается строка.|  
|[in] `y1`|Координата y, с которой начинается строка.|  
|[in] `x2`|Координата x, где заканчивается строки.|  
|[in] `y2`|Координата y, где заканчивается строки.|  
|[in] `clrLine`|Цвет линии.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняется, если `clrLine` равно -1.  
  
##  <a name="a-namedrawrecta--cdrawingmanagerdrawrect"></a><a name="drawrect"></a>CDrawingManager::DrawRect  
 Рисование прямоугольника с предоставленным цвета заливки и границ.  
  
```  
void DrawRect(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Границы прямоугольника.  
  
 [in] `clrFill`  
 Цвет, который использует этот метод для заполнения прямоугольника.  
  
 [in] `clrLine`  
 Цвет, этот метод использует для границы прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращается без Рисование прямоугольника, если любого цвета равно-1. Также возвращается, если либо измерения прямоугольника — 0.  
  
##  <a name="a-namedrawshadowa--cdrawingmanagerdrawshadow"></a><a name="drawshadow"></a>CDrawingManager::DrawShadow  
 Рисует тень прямоугольной области.  
  
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
 Прямоугольная область, в приложении. Рисование manager будет нарисовать тень внутри этой области.  
  
 [in] `nDepth`  
 Ширина и высота тени.  
  
 [in] `iMinBrightness`  
 Минимальное яркости тени.  
  
 [in] `iMaxBrightness`  
 Максимальная яркость тени.  
  
 [in] `pBmpSaveBottom`  
 Указатель на точечный рисунок, который содержит изображение, чтобы в нижней части тени.  
  
 [in] `pBmpSaveRight`  
 Указатель на точечный рисунок, который содержит изображение, чтобы тени, рисуется правой стороны прямоугольника.  
  
 [in] `clrBase`  
 Цвет тени.  
  
 [in] `bRightShadow`  
 Логический параметр, указывающий, как нарисовать тень. Если `bRightShadow` — `TRUE`, `DrawShadow` рисует тень правой стороны прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Два допустимых точечных рисунков для нижнего и правого тени можно предоставить с помощью параметров `pBmpSaveBottom` и `pBmpSaveRight`. Если эти [CBitmap](../../mfc/reference/cbitmap-class.md) объекты имеют присоединенный объект GDI `DrawShadow` будет использовать эти точечные рисунки, как тени. Если `CBitmap` параметров нет вложенного объекта GDI, `DrawShadow` рисует тень и присоединяет точечные рисунки с параметрами. В последующих вызовов `DrawShadow`, вы можете предоставить эти точечные рисунки, чтобы ускорить процесс рисования. Дополнительные сведения о `CBitmap` класс и GDI-объекты, в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
 При выполнении любого из этих параметров `NULL`, `DrawShadow` будет автоматически отрисовка теней.  
  
 Если задать `bRightShadow` в `FALSE`, снизу и слева от прямоугольной области рисования тени.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `DrawShadow` метод `CDrawingManager` класса. Этот фрагмент кода является частью [Prop лист демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_PropSheetDemo&#1;](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]  
  
##  <a name="a-namefill4colorsgradienta--cdrawingmanagerfill4colorsgradient"></a><a name="fill4colorsgradient"></a>CDrawingManager::Fill4ColorsGradient  
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
 Цвет, первый цвет градиента.  
  
 [in] `colorFinish1`  
 Конечный цвет первый цвет градиента.  
  
 [in] `colorStart2`  
 Начальный цвет для второй цвет градиента.  
  
 [in] `colorFinish2`  
 Конечный цвет для второй цвет градиента.  
  
 [in] `bHorz`  
 Логический параметр, указывающий ли `Fill4ColorsGradient` горизонтальный или Вертикальный градиент цвета. `TRUE`Указывает горизонтальный градиент.  
  
 [in] `nPercentage`  
 Целое число от 0 до 100. Это значение указывает долю прямоугольника для заливки с первый цвет градиента.  
  
### <a name="remarks"></a>Примечания  
 Если прямоугольник заполняется два цвета градиента, они являются находится выше друг с другом либо рядом друг с другом, в зависимости от значения `bHorz`. Каждый цвет градиента вычисляется независимо друг от друга с помощью метода [CDrawingManager::FillGradient](#fillgradient).  
  
 Этот метод создает ошибку подтверждения, если `nPercentage` меньше 0 или больше 100.  
  
##  <a name="a-namefillgradienta--cdrawingmanagerfillgradient"></a><a name="fillgradient"></a>CDrawingManager::FillGradient  
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
 Конечный цвет градиента.  
  
 [in] `bHorz`  
 Логический параметр, указывает ли `FillGradient` должна нарисовать горизонтальный или Вертикальный градиент.  
  
 [in] `nStartFlatPercentage`  
 Процент прямоугольника, `FillGradient` заполняет `colorStart` начала градиента.  
  
 [in] `nEndFlatPercentage`  
 Процент прямоугольника, `FillGradient` заполняет `colorFinish` после его завершения градиента.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `FillGradient` метод `CDrawingManager` класса. Этот фрагмент кода является частью [MS Office 2007 демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#12;](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]  
  
##  <a name="a-namefillgradient2a--cdrawingmanagerfillgradient2"></a><a name="fillgradient2"></a>CDrawingManager::FillGradient2  
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
 Целое число от 0 до 360. Этот параметр указывает направление градиента.  
  
### <a name="remarks"></a>Примечания  
 Используйте `nAngle` для указания направления градиента. При указании направление градиента можно также указать начала градиента. Значение 0 для `nAngle` указывает градиента начинается от верхнего края прямоугольника. Как `nAngle` увеличивается, начальное положение для градиента перемещается в направлении против часовой стрелки на основе углов.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `FillGradient2` метод `CDrawingManager` класса. Этот фрагмент кода является частью [образец новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#37;](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]  
  
##  <a name="a-namegrayrecta--cdrawingmanagergrayrect"></a><a name="grayrect"></a>CDrawingManager::GrayRect  
 Заполняет прямоугольник заданным серым цветом.  
  
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
 Процентная доля серого в прямоугольник.  
  
 [in] `clrTransparent`  
 Прозрачный цвет.  
  
 [in] `clrDisabled`  
 Цвет, который использует этот метод для удаления насыщенность, если `nPercentage` имеет значение -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Для параметра `nPercentage`, более низкое значение указывает более темный цвет.  
  
 Максимальное значение для `nPercentage` равно 200. Значение, превышающее 200 не изменяется внешний вид прямоугольника. Если значение равно -1, этот метод использует `clrDisabled` для ограничения насыщенность прямоугольника.  
  
##  <a name="a-namehighlightrecta--cdrawingmanagerhighlightrect"></a><a name="highlightrect"></a>CDrawingManager::HighlightRect  
 Выделяет прямоугольную область.  
  
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
 Если `nPercentage` находится в диапазоне от 0 до 99 `HighlightRect` использует альфа-смешения алгоритма. Дополнительные сведения о альфа-смешение, в разделе [альфа смешение цвета для линий и заливок](http://msdn.microsoft.com/library/5440f48c-3ac9-44c3-b170-c1c110bdbab8). Если `nPercentage` равно -1, этот метод использует уровень выделения по умолчанию. Если `nPercentage` — 100, этот метод не выполняет никаких действий и возвращает `TRUE`.  
  
 Метод использует параметр `nTolerance` для определения необходимости выделите прямоугольную область. Чтобы выделить прямоугольник, разница между цвет фона для приложения и `clrTransparent` должно быть меньше, чем `nTolerance` каждого компонента цвета (красный, зеленый и синий).  
  
##  <a name="a-namehlstorgbonea--cdrawingmanagerhlstorgbone"></a><a name="hlstorgb_one"></a>CDrawingManager::HLStoRGB_ONE  
 Преобразует цвет из представления HLS в формате RGB.  
  
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
 Число от 0 до 1, определяющее насыщенность цвета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представление RGB, предоставляемые цвета HLS.  
  
### <a name="remarks"></a>Примечания  
 Цвет может быть представлено как HSV (оттенок, насыщенность и значение), (цветового тона, насыщенности и яркости) HSL или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Этот метод и `CDrawingManager::HLStoRGB_TWO` способ выполнить ту же операцию, но требуются разные значения для `H` параметр. В этом методе `H` круга в процентах. В `CDrawingManager::HLStoRGB_TWO` метода `H` значение степени от 0 до 360, представляющие обе красным. Например, при использовании `HLStoRGB_ONE`, значение 0,25 для `H` эквивалентен значению 90 с `HLStoRGB_TWO`.  
  
##  <a name="a-namehlstorgbtwoa--cdrawingmanagerhlstorgbtwo"></a><a name="hlstorgb_two"></a>CDrawingManager::HLStoRGB_TWO  
 Преобразует цвет из представления HLS в формате RGB.  
  
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
 Число от 0 до 1, определяющее насыщенность цвета.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представление RGB, предоставляемые цвета HLS.  
  
### <a name="remarks"></a>Примечания  
 Цвет может быть представлено как HSV (оттенок, насыщенность и значение), (цветового тона, насыщенности и яркости) HSL или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Этот метод и [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) способ выполнить ту же операцию, но требуются разные значения для `H` параметр. В этом методе `H` значение степени от 0 до 360, представляющие обе красным. В [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) метода `H` в процентах от круга. Например, при использовании `HLStoRGB_ONE`, значение 0,25 для `H` эквивалентен значению 90 с `HLStoRGB_TWO`.  
  
##  <a name="a-namehsvtorgba--cdrawingmanagerhsvtorgb"></a><a name="hsvtorgb"></a>CDrawingManager::HSVtoRGB  
 Преобразует цвет из представления HSV в формате RGB.  
  
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
|[in] `H`|Число от 0 до 360, определяющее оттенок цвета.|  
|[in] `S`|Число от 0 до 1, определяющее насыщенность цвета.|  
|[in] `V`|Число от 0 до 1, определяющее значение цвета.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представление RGB предоставленных цвет HSV.  
  
### <a name="remarks"></a>Примечания  
 Цвет может быть представлено как HSV (оттенок, насыщенность и значение), (цветового тона, насыщенности и яркости) HSL или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/linkid=119126).  
  
##  <a name="a-namehuetorgba--cdrawingmanagerhuetorgb"></a><a name="huetorgb"></a>CDrawingManager::HuetoRGB  
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
 Отдельные красного, зеленого или синего компонента для предоставленного цветовой тон.  
  
### <a name="remarks"></a>Примечания  
 Этот метод является вспомогательным методом, `CDrawingManager` класс использует для вычисления отдельных компонентов красного, зеленого и синего цвета в HSV или HSL представление. Этот метод не позволяет вызывать непосредственно программистом. Входные параметры являются значения, зависящие от алгоритма преобразования.  
  
 Чтобы преобразовать цвет HSV или HSL представления RGB, вызовите один из следующих методов:  
  
- [CDrawingManager::HSVtoRGB](#hsvtorgb)  
  
- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)  
  
- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)  
  
##  <a name="a-namemirrorrecta--cdrawingmanagermirrorrect"></a><a name="mirrorrect"></a>CDrawingManager::MirrorRect  
 Зеркальное отражение прямоугольной области.  
  
```  
void MirrorRect(
    CRect rect,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Прямоугольник, ограничивающий область, чтобы отразить.  
  
 [in] `bHorz`  
 Логический параметр, указывающий, изменяет ли прямоугольник горизонтально или вертикально.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно перевернуть любую область контекста устройства, принадлежащие `CDrawingManager` класса. Если `bHorz` равен `TRUE`, этот метод горизонтальное зеркальное отражение области. В противном случае — он Вертикальное зеркальное отражение области.  
  
##  <a name="a-namepixelalphaa--cdrawingmanagerpixelalpha"></a><a name="pixelalpha"></a>CDrawingManager::PixelAlpha  
 Вычисляет конечный цвет для полупрозрачными пикселей.  
  
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
 Число от 0 до 100, представляющее процент прозрачности. Значение 100 означает, что цвет является полностью прозрачным.  
  
 [in] `percentR`  
 Число, представляющее процент прозрачности для красного компонента от 0 до 100.  
  
 [in] `percentG`  
 Число, представляющее процент прозрачности для зеленого компонента от 0 до 100.  
  
 [in] `percentB`  
 Число от 0 до 100, представляющее процент прозрачности для синего компонента.  
  
 [in] `dstPixel`  
 Базовый цвет пикселя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Конечный цвет полупрозрачными пикселей.  
  
### <a name="remarks"></a>Примечания  
 Это является вспомогательным классом для закрашивания полупрозрачными точечные рисунки и не может вызываться напрямую, программист.  
  
 При использовании версии метода, который имеет `dstPixel`, окончательный цвет представляет собой сочетание `dstPixel` и `srcPixel`. `srcPixel` Имеет частично прозрачный цвет через базовый цвет `dstPixel`.  
  
##  <a name="a-nameprepareshadowmaska--cdrawingmanagerprepareshadowmask"></a><a name="prepareshadowmask"></a>CDrawingManager::PrepareShadowMask  
 Создает точечный рисунок, который можно использовать в качестве тень.  
  
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
 Минимальное яркости тени.  
  
 [in] `iMaxBrightness`  
 Максимальная яркость тени.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для созданного точечного рисунка в случае успешного выполнения; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если `nDepth` имеет значение 0, этот метод завершает работу и возвращает `NULL`. Если `nDepth` меньше 3, ширину и высоту тени равным 3 пикселя.  
  
##  <a name="a-namergbtohsla--cdrawingmanagerrgbtohsl"></a><a name="rgbtohsl"></a>CDrawingManager::RGBtoHSL  
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
|Параметр|Описание|  
|[in] `rgb`|С цветом RGB-значения.|  
|[выходной] `H`|Указатель на значение типа double, где метод хранит оттенок цвета.|  
|[выходной] `S`|Указатель на значение типа double, где метод хранит насыщенность цвета.|  
|[выходной] `L`|Указатель на значение типа double, где метод хранит яркость выбранного цвета.|  
  
### <a name="remarks"></a>Примечания  
 Цвет может быть представлено как HSV (оттенок, насыщенность и значение), (цветового тона, насыщенности и яркости) HSL или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Возвращаемое значение для `H` представляется в виде дробного числа от 0 до 1, где 0 и 1 представляют красный. Возвращаемые значения для `S` и `L` являются числами от 0 до 1.  
  
##  <a name="a-namergbtohsva--cdrawingmanagerrgbtohsv"></a><a name="rgbtohsv"></a>CDrawingManager::RGBtoHSV  
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
 Указатель на значение типа double, где этот метод сохраняет результирующий оттенок цвета.  
  
 [выходной] `S`  
 Указатель на значение типа double, где этот метод сохраняет результирующий насыщенность цвета.  
  
 [выходной] `V`  
 Указатель на значение типа double, где этот метод сохраняет полученное значение цвета.  
  
### <a name="remarks"></a>Примечания  
 Цвет может быть представлено как HSV (оттенок, насыщенность и значение), (цветового тона, насыщенности и яркости) HSL или RGB (красный, зеленый и синий). Дополнительные сведения о разных представления цвета в разделе [цвет](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Возвращаемое значение для `H` — число от 0 до 360, где 0 до 360 указываем красным. Возвращаемые значения для `S` и `V` являются числами от 0 до 1.  
  
##  <a name="a-namesetalphapixela--cdrawingmanagersetalphapixel"></a><a name="setalphapixel"></a>CDrawingManager::SetAlphaPixel  
 Цвета прозрачность пикселов в точечном рисунке.  
  
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
 Указатель битовые значения для точечного рисунка.  
  
 [in] `rect`  
 Прямоугольная область, в приложении. Рисование manager рисует тень снизу и справа от этой области.  
  
 [in] `x`  
 Горизонтальная координата точки цвета.  
  
 [in] `y`  
 Вертикальная координата точки цвета.  
  
 [in] `percent`  
 Процент прозрачности.  
  
 [in] `iShadowSize`  
 Ширина и высота тени.  
  
 [in] `clrBase`  
 Цвет тени.  
  
 [in] `bIsRight`  
 Логический параметр, который указывает, какой пиксел цвет. Дополнительные сведения см. в разделе "Примечания".  
  
### <a name="remarks"></a>Примечания  
 Этот метод является вспомогательным методом, используемый [CDrawingManager::DrawShadow](#drawshadow) метод. Корпорация Майкрософт рекомендует, чтобы нарисовать тень, вызовите `CDrawingManager::DrawShadow` вместо.  
  
 Если `bIsRight` равен `TRUE`, цвет пикселя измеряется `x` пикселей от правого края `rect`. Если это `FALSE`, цвет пикселя измеряется `x` пикселей от левого края `rect`.  
  
##  <a name="a-namesetpixela--cdrawingmanagersetpixel"></a><a name="setpixel"></a>CDrawingManager::SetPixel  
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
|Параметр|Описание|  
|[in] `pBits`|Указатель битовые значения битовой карты.|  
|[in] `cx`|Общая ширина растрового изображения.|  
|[in] `cy`|Общая высота растрового изображения.|  
|[in] `x`|Координата x точки в растровое изображение, чтобы изменить.|  
|[in] `y`|Координата y точки в растровое изображение, чтобы изменить.|  
|[in] `color`|Новый цвет пикселя определяется заданными координатами.|  
  
##  <a name="a-namesmartmixcolorsa--cdrawingmanagersmartmixcolors"></a><a name="smartmixcolors"></a>CDrawingManager::SmartMixColors  
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
|Параметр|Описание|  
|[in] `color1`|Первый цвет одновременно.|  
|[in] `color2`|Второй цвет одновременно.|  
|[in] `dblLumRatio`|Отношение для нового цвета яркость. `SmartMixColors`Умножает яркость смешанный цвет этого отношения перед определением конечный цвет.|  
|[in] `k1`|Взвешенное степень первый цвет.|  
|[in] `k2`|Взвешенное отношение для второй цвет.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет, представляющий взвешенного сочетание указанного цвета.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается с ошибкой, если параметр `k1` или `k2` меньше нуля. Если оба этих параметра значение 0, метод возвращает `RGB(0, 0, 0)`.  
  
 Взвешенное отношение вычисляется по следующей формуле: (color1 * k1 + цвет2 \* k2) /(k1 + k2). После определения взвешенного отношение, метод вычисляет яркость для смешанных цвета. Умножает яркость, `dblLumRatio`. Если значение больше, чем 1.0, метод задает яркость цвета смешанного новое значение. В противном случае — яркость равен 1.0.  
  
##  <a name="a-namedrawrotateda--cdrawingmanagerdrawrotated"></a><a name="drawrotated"></a>CDrawingManager::DrawRotated  
 Поворачивает исходного контроллера домена содержимого внутри данного прямоугольника на 90 градусов.  
  
```  
void DrawRotated(
    CRect rectDest,  
    CDC& dcSrc,  
    BOOL bClockWise);
```  
  
### <a name="parameters"></a>Параметры  
 `rectDest`  
 Прямоугольник назначения.  
  
 `dcSrc`  
 Контекст исходного устройства.  
  
 `bClockWise`  
 `TRUE`Указывает поворота&90; градусов; `FALSE` указывает поворот-90 градусов.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

