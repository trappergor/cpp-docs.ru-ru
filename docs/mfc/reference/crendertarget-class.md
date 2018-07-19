---
title: Класс CRenderTarget | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRenderTarget
- AFXRENDERTARGET/CRenderTarget
- AFXRENDERTARGET/CRenderTarget::CRenderTarget
- AFXRENDERTARGET/CRenderTarget::Attach
- AFXRENDERTARGET/CRenderTarget::BeginDraw
- AFXRENDERTARGET/CRenderTarget::Clear
- AFXRENDERTARGET/CRenderTarget::COLORREF_TO_D2DCOLOR
- AFXRENDERTARGET/CRenderTarget::CreateCompatibleRenderTarget
- AFXRENDERTARGET/CRenderTarget::Destroy
- AFXRENDERTARGET/CRenderTarget::Detach
- AFXRENDERTARGET/CRenderTarget::DrawBitmap
- AFXRENDERTARGET/CRenderTarget::DrawEllipse
- AFXRENDERTARGET/CRenderTarget::DrawGeometry
- AFXRENDERTARGET/CRenderTarget::DrawGlyphRun
- AFXRENDERTARGET/CRenderTarget::DrawLine
- AFXRENDERTARGET/CRenderTarget::DrawRectangle
- AFXRENDERTARGET/CRenderTarget::DrawRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::DrawText
- AFXRENDERTARGET/CRenderTarget::DrawTextLayout
- AFXRENDERTARGET/CRenderTarget::EndDraw
- AFXRENDERTARGET/CRenderTarget::FillEllipse
- AFXRENDERTARGET/CRenderTarget::FillGeometry
- AFXRENDERTARGET/CRenderTarget::FillMesh
- AFXRENDERTARGET/CRenderTarget::FillOpacityMask
- AFXRENDERTARGET/CRenderTarget::FillRectangle
- AFXRENDERTARGET/CRenderTarget::FillRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::Flush
- AFXRENDERTARGET/CRenderTarget::GetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetDpi
- AFXRENDERTARGET/CRenderTarget::GetMaximumBitmapSize
- AFXRENDERTARGET/CRenderTarget::GetPixelFormat
- AFXRENDERTARGET/CRenderTarget::GetPixelSize
- AFXRENDERTARGET/CRenderTarget::GetRenderTarget
- AFXRENDERTARGET/CRenderTarget::GetSize
- AFXRENDERTARGET/CRenderTarget::GetTags
- AFXRENDERTARGET/CRenderTarget::GetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::GetTransform
- AFXRENDERTARGET/CRenderTarget::IsSupported
- AFXRENDERTARGET/CRenderTarget::IsValid
- AFXRENDERTARGET/CRenderTarget::PopAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PopLayer
- AFXRENDERTARGET/CRenderTarget::PushAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PushLayer
- AFXRENDERTARGET/CRenderTarget::RestoreDrawingState
- AFXRENDERTARGET/CRenderTarget::SaveDrawingState
- AFXRENDERTARGET/CRenderTarget::SetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetDpi
- AFXRENDERTARGET/CRenderTarget::SetTags
- AFXRENDERTARGET/CRenderTarget::SetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::SetTransform
- AFXRENDERTARGET/CRenderTarget::VerifyResource
- AFXRENDERTARGET/CRenderTarget::m_lstResources
- AFXRENDERTARGET/CRenderTarget::m_pRenderTarget
- AFXRENDERTARGET/CRenderTarget::m_pTextFormatDefault
dev_langs:
- C++
helpviewer_keywords:
- CRenderTarget [MFC], CRenderTarget
- CRenderTarget [MFC], Attach
- CRenderTarget [MFC], BeginDraw
- CRenderTarget [MFC], Clear
- CRenderTarget [MFC], COLORREF_TO_D2DCOLOR
- CRenderTarget [MFC], CreateCompatibleRenderTarget
- CRenderTarget [MFC], Destroy
- CRenderTarget [MFC], Detach
- CRenderTarget [MFC], DrawBitmap
- CRenderTarget [MFC], DrawEllipse
- CRenderTarget [MFC], DrawGeometry
- CRenderTarget [MFC], DrawGlyphRun
- CRenderTarget [MFC], DrawLine
- CRenderTarget [MFC], DrawRectangle
- CRenderTarget [MFC], DrawRoundedRectangle
- CRenderTarget [MFC], DrawText
- CRenderTarget [MFC], DrawTextLayout
- CRenderTarget [MFC], EndDraw
- CRenderTarget [MFC], FillEllipse
- CRenderTarget [MFC], FillGeometry
- CRenderTarget [MFC], FillMesh
- CRenderTarget [MFC], FillOpacityMask
- CRenderTarget [MFC], FillRectangle
- CRenderTarget [MFC], FillRoundedRectangle
- CRenderTarget [MFC], Flush
- CRenderTarget [MFC], GetAntialiasMode
- CRenderTarget [MFC], GetDpi
- CRenderTarget [MFC], GetMaximumBitmapSize
- CRenderTarget [MFC], GetPixelFormat
- CRenderTarget [MFC], GetPixelSize
- CRenderTarget [MFC], GetRenderTarget
- CRenderTarget [MFC], GetSize
- CRenderTarget [MFC], GetTags
- CRenderTarget [MFC], GetTextAntialiasMode
- CRenderTarget [MFC], GetTextRenderingParams
- CRenderTarget [MFC], GetTransform
- CRenderTarget [MFC], IsSupported
- CRenderTarget [MFC], IsValid
- CRenderTarget [MFC], PopAxisAlignedClip
- CRenderTarget [MFC], PopLayer
- CRenderTarget [MFC], PushAxisAlignedClip
- CRenderTarget [MFC], PushLayer
- CRenderTarget [MFC], RestoreDrawingState
- CRenderTarget [MFC], SaveDrawingState
- CRenderTarget [MFC], SetAntialiasMode
- CRenderTarget [MFC], SetDpi
- CRenderTarget [MFC], SetTags
- CRenderTarget [MFC], SetTextAntialiasMode
- CRenderTarget [MFC], SetTextRenderingParams
- CRenderTarget [MFC], SetTransform
- CRenderTarget [MFC], VerifyResource
- CRenderTarget [MFC], m_lstResources
- CRenderTarget [MFC], m_pRenderTarget
- CRenderTarget [MFC], m_pTextFormatDefault
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ab1f4a056e1a65475a71ede0b51db45189d2dd9
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079764"
---
# <a name="crendertarget-class"></a>Класс CRenderTarget
Программа-оболочка для ID2D1RenderTarget.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRenderTarget : public CObject;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRenderTarget::CRenderTarget](#crendertarget)|Создает объект CRenderTarget.|  
|[CRenderTarget:: ~ CRenderTarget](#crendertarget__~crendertarget)|Деструктор Вызывается при уничтожении целевой объект отрисовки.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRenderTarget::Attach](#attach)|Присоединяет существующую отрисовки интерфейса целевой объект|  
|[CRenderTarget::BeginDraw](#begindraw)|Инициирует рисования в этом целевом объекте отрисовки.|  
|[CRenderTarget::Clear](#clear)|Очищает область рисования указанного цвета.|  
|[CRenderTarget::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|Преобразует значения цвета и альфа-GDI D2D1_COLOR_F объекта.|  
|[CRenderTarget::CreateCompatibleRenderTarget](#createcompatiblerendertarget)|Создает новый целевой объект отрисовки растрового изображения для использования во время промежуточного созданного рисунка, которая совместима с текущей целевой объект отрисовки.|  
|[CRenderTarget::Destroy](#destroy)|Удаляет один или несколько ресурсов|  
|[CRenderTarget::Detach](#detach)|Отсоединяет интерфейса отрисовки целевого объекта|  
|[CRenderTarget::DrawBitmap](#drawbitmap)|Рисует форматированный текст, описанной заданным объектом IDWriteTextLayout.|  
|[CRenderTarget::DrawEllipse](#drawellipse)|Рисование контура указанным эллипса с использованием стиля, указанного штриха.|  
|[CRenderTarget::DrawGeometry](#drawgeometry)|Рисование контура указанным геометрического объекта с использованием стиля, указанного штриха.|  
|[CRenderTarget::DrawGlyphRun](#drawglyphrun)|Рисует указанный глифов.|  
|[CRenderTarget::DrawLine](#drawline)|Проводит линию между заданными точками, с использованием стиля, указанного штриха.|  
|[CRenderTarget::DrawRectangle](#drawrectangle)|Рисование контура прямоугольника, который имеет заданные размеры и стиль штриха.|  
|[CRenderTarget::DrawRoundedRectangle](#drawroundedrectangle)|Рисование контура прямоугольника с закругленными углами указанным с использованием стиля, указанного штриха.|  
|[CRenderTarget::DrawText](#drawtext)|Рисует заданный текст, используя сведения о форматировании, предоставляемые IDWriteTextFormat объекта.|  
|[CRenderTarget::DrawTextLayout](#drawtextlayout)|Рисует форматированный текст, описанной заданным объектом IDWriteTextLayout.|  
|[CRenderTarget::EndDraw](#enddraw)|Завершает операций рисования в целевом объекте отрисовки и указывает текущее состояние ошибки и связанные с ними теги.|  
|[CRenderTarget::FillEllipse](#fillellipse)|Заполняет внутреннюю часть эллипса, заданного.|  
|[CRenderTarget::FillGeometry](#fillgeometry)|Закрашивает внутреннюю часть указанного geometry.|  
|[CRenderTarget::FillMesh](#fillmesh)|Закрашивает внутреннюю часть указанного сетки.|  
|[CRenderTarget::FillOpacityMask](#fillopacitymask)|Применяет маску непрозрачности, описываемых в указанном точечном рисунке кисти которая затем используется для заполнения области целевого объекта отрисовки.|  
|[CRenderTarget::FillRectangle](#fillrectangle)|Заполняет внутреннюю часть заданного прямоугольника.|  
|[CRenderTarget::FillRoundedRectangle](#fillroundedrectangle)|Закрашивает внутреннюю часть указанного Скругленный прямоугольник.|  
|[CRenderTarget::Flush](#flush)|Выполняет всех ожидающих применения команд рисования.|  
|[CRenderTarget::GetAntialiasMode](#getantialiasmode)|Получает текущий режим сглаживания для нетекстовых графических операций.|  
|[CRenderTarget::GetDpi](#getdpi)|Возвращает целевой точек на дюйм (DPI) для подготовки к просмотру|  
|[CRenderTarget::GetMaximumBitmapSize](#getmaximumbitmapsize)|Возвращает максимальный размер в единицах зависящие от устройства (в пикселях), любое измерение одного точечного рисунка, поддерживаемые в целевом объекте отрисовки|  
|[CRenderTarget::GetPixelFormat](#getpixelformat)|Возвращает режим формат и альфа-пиксель целевого объекта отрисовки|  
|[CRenderTarget::GetPixelSize](#getpixelsize)|Возвращает размер целевого объекта отрисовки в пикселях устройства|  
|[CRenderTarget::GetRenderTarget](#getrendertarget)|Возвращает интерфейс ID2D1RenderTarget|  
|[CRenderTarget::GetSize](#getsize)|Возвращает размер целевого объекта отрисовки в аппаратно независимых пикселях|  
|[CRenderTarget::GetTags](#gettags)|Возвращает метку для последующих операций рисования.|  
|[CRenderTarget::GetTextAntialiasMode](#gettextantialiasmode)|Возвращает текущий режим сглаживания для текста и операций рисования глифов.|  
|[CRenderTarget::GetTextRenderingParams](#gettextrenderingparams)|Возвращает целевой объект отрисовки текущие параметры отрисовки текста.|  
|[CRenderTarget::GetTransform](#gettransform)|Применяет указанное преобразование в целевом объекте отрисовки, заменив существующий преобразования. Все последующие операции рисования происходят в преобразованный пространства.|  
|[CRenderTarget::IsSupported](#issupported)|Указывает, поддерживает ли целевой объект отрисовки указанные свойства|  
|[CRenderTarget::IsValid](#isvalid)|Проверяет допустимость ресурсов|  
|[CRenderTarget::PopAxisAlignedClip](#popaxisalignedclip)|Удаляет последний выровненный по осям клип из целевого объекта отрисовки. После вызова этого метода, клип больше не применяется для последующих операций рисования.|  
|[CRenderTarget::PopLayer](#poplayer)|Останавливает перенаправление операций рисования с уровнем, определяется последней PushLayer вызова.|  
|[CRenderTarget::PushAxisAlignedClip](#pushaxisalignedclip)|Удаляет последний выровненный по осям клип из целевого объекта отрисовки. После вызова этого метода, клип больше не применяется для последующих операций рисования.|  
|[CRenderTarget::PushLayer](#pushlayer)|Добавляет указанный слой в целевом объекте отрисовки, чтобы он получает все последующие операции рисования, пока не будет вызван PopLayer.|  
|[CRenderTarget::RestoreDrawingState](#restoredrawingstate)|Задает состояние рисования целевой объект отрисовки, указанным ID2D1DrawingStateBlock.|  
|[CRenderTarget::SaveDrawingState](#savedrawingstate)|Сохраняет текущее состояние отображения для указанного ID2D1DrawingStateBlock.|  
|[CRenderTarget::SetAntialiasMode](#setantialiasmode)|Задает режим сглаживания целевого объекта отрисовки. Режим сглаживания применяет все последующие операции рисования, за исключением текста и операций рисования глифов.|  
|[CRenderTarget::SetDpi](#setdpi)|Задает размер в точках на дюйм (DPI) целевого объекта отрисовки.|  
|[CRenderTarget::SetTags](#settags)|Задает метку для последующих операций рисования.|  
|[CRenderTarget::SetTextAntialiasMode](#settextantialiasmode)|Задает режим сглаживания, который будет использоваться для последующего текста и операции рисования глифов.|  
|[CRenderTarget::SetTextRenderingParams](#settextrenderingparams)|Указывает параметры отрисовки текста, применяемые ко всем весь последующий текст и операций рисования глифов.|  
|[CRenderTarget::SetTransform](#settransform)|Перегружен. Применяет указанное преобразование в целевом объекте отрисовки, заменив существующий преобразования. Все последующие операции рисования происходят в преобразованный пространства.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRenderTarget::VerifyResource](#verifyresource)|Проверяет допустимость объекта CD2DResource; Создает объект, если он еще не существует.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget *](#operator_id2d1rendertarget_star)|Возвращает интерфейс ID2D1RenderTarget|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CRenderTarget::m_lstResources](#m_lstresources)|Список указателей на объекты CD2DResource.|  
|[CRenderTarget::m_pRenderTarget](#m_prendertarget)|Указатель на объект ID2D1RenderTarget.|  
|[CRenderTarget::m_pTextFormatDefault](#m_ptextformatdefault)|Указатель на объект CD2DTextFormat, который содержит текстовый формат по умолчанию.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcrendertarget"></a>  CRenderTarget:: ~ CRenderTarget  
 Деструктор Вызывается при уничтожении целевой объект отрисовки.  
  
```  
virtual ~CRenderTarget();
```  
  
##  <a name="attach"></a>  CRenderTarget::Attach  
 Присоединяет существующую отрисовки интерфейса целевой объект  
  
```  
void Attach(ID2D1RenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 *pRenderTarget*  
 Существующий интерфейс цели отрисовки. Не может иметь значение NULL  
  
##  <a name="begindraw"></a>  CRenderTarget::BeginDraw  
 Инициирует рисования в этом целевом объекте отрисовки.  
  
```  
void BeginDraw();
```  
  
##  <a name="clear"></a>  CRenderTarget::Clear  
 Очищает область рисования указанного цвета.  
  
```  
void Clear(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>Параметры  
 *Цвет*  
 Цвет, который очищается области рисования.  
  
##  <a name="colorref_to_d2dcolor"></a>  CRenderTarget::COLORREF_TO_D2DCOLOR  
 Преобразует значения цвета и альфа-GDI D2D1_COLOR_F объекта.  
  
```  
static D2D1_COLOR_F COLORREF_TO_D2DCOLOR(
    COLORREF color,  
    int nAlpha = 255);
```  
  
### <a name="parameters"></a>Параметры  
 *Цвет*  
 RGB-значение.  
  
 *nAlpha*  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение D2D1_COLOR_F.  
  
##  <a name="createcompatiblerendertarget"></a>  CRenderTarget::CreateCompatibleRenderTarget  
 Создает новый целевой объект отрисовки растрового изображения для использования во время промежуточного созданного рисунка, которая совместима с текущей целевой объект отрисовки.  
  
```  
BOOL CreateCompatibleRenderTarget(
    CBitmapRenderTarget& bitmapTarget,  
    CD2DSizeF sizeDesired = CD2DSizeF(0., 0.), 
    CD2DSizeU sizePixelDesired = CD2DSizeU(0, 0), 
    D2D1_PIXEL_FORMAT* desiredFormat = NULL,  
    D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS options = D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Параметры  
 *bitmapTarget*  
 По возвращении из этого метода содержит адрес указателя на новый целевой объект отрисовки растрового изображения. Этот параметр передается неинициализированным.  
  
 *sizeDesired*  
 По размеру нового целевого объекта отрисовки в аппаратно независимых пикселях, если он должен отличаться от исходного целевым объектом прорисовки или NULL. Дополнительные сведения см. в разделе "Примечания".  
  
 *sizePixelDesired*  
 По размеру нового целевого объекта отрисовки в пикселях, если он должен отличаться от исходного целевым объектом прорисовки или NULL. Дополнительные сведения см. в разделе "Примечания".  
  
 *desiredFormat*  
 Формат нужную точку и альфа-режим нового целевым объектом прорисовки или NULL. Если формат пикселей для DXGI_FORMAT_UNKNOWN или если этот параметр имеет значение null, новый целевой объект отрисовки использует тот же формат пикселей, как исходный целевым объектом прорисовки. Если альфа-режим — D2D1_ALPHA_MODE_UNKNOWN или этот параметр имеет значение NULL, альфа-режим нового целевого объекта отрисовки по умолчанию D2D1_ALPHA_MODE_PREMULTIPLIED. Сведения о поддерживаемых форматов пикселей см. Поддерживаемые форматы точек и режимов альфа-канал.  
  
 *Параметры*  
 Значение, указывающее, является ли новый целевой объект отрисовки должен быть совместим с GDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE.  
  
##  <a name="crendertarget"></a>  CRenderTarget::CRenderTarget  
 Создает объект CRenderTarget.  
  
```  
CRenderTarget();
```  
  
##  <a name="destroy"></a>  CRenderTarget::Destroy  
 Удаляет один или несколько ресурсов  
  
```  
BOOL Destroy(BOOL bDeleteResources = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bDeleteResources*  
 Если bDeleteResources имеет значение TRUE, все ресурсы, расположенные в m_lstResources будет автоматически удаляется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение TRUE. В противном случае возвращается значение FALSE  
  
##  <a name="detach"></a>  CRenderTarget::Detach  
 Отсоединяет интерфейса отрисовки целевого объекта  
  
```  
ID2D1RenderTarget* Detach ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на отсоединенной отрисовки интерфейс целевого объекта.  
  
##  <a name="drawbitmap"></a>  CRenderTarget::DrawBitmap  
 Рисует форматированный текст, описанной заданным объектом IDWriteTextLayout.  
  
```  
void DrawBitmap(
    CD2DBitmap* pBitmap,  
    const CD2DRectF& rectDest,  
    float fOpacity = 1.0,  
    D2D1_BITMAP_INTERPOLATION_MODE interpolationMode = D2D1_BITMAP_INTERPOLATION_MODE_LINEAR,  
    const CD2DRectF* pRectSrc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pBitmap*  
 Битовая карта для подготовки к просмотру.  
  
 *rectDest*  
 Размер и положение в аппаратно независимых пикселях в целевом объекте отрисовки системы координат, области, в которую рисуется растровое изображение. Если не упорядоченный прямоугольника, не выводится ничего, но целевой объект отрисовки не переходят в состояние ошибки.  
  
 *fOpacity*  
 Значение в диапазоне от 0, 0f до 1, 0f, включительно, указывающее значение непрозрачности для применения к растровому изображению; Это значение умножается на альфа-значения содержимого растрового изображения.  
  
 *interpolationMode*  
 Режим интерполяции, используемый Если растровое изображение масштабируется или поворачивать операции рисования.  
  
 *pRectSrc*  
 Размер и положение в аппаратно независимых пикселях в координатное пространство растрового изображения, области в растровое изображение для отрисовки.  
  
##  <a name="drawellipse"></a>  CRenderTarget::DrawEllipse  
 Рисование контура указанным эллипса с использованием стиля, указанного штриха.  
  
```  
void DrawEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *эллипс*  
 Положение и радиус эллипса для отрисовки в аппаратно независимых пикселях.  
  
 *pBrush*  
 Кисть, используемую для рисования контура эллипса.  
  
 *fStrokeWidth*  
 Толщина контура эллипса. Штриха центрируется на контура эллипса.  
  
 *strokeStyle*  
 Стиль штриха для применения контура эллипса, или значение NULL для закрашивания сплошной штриха.  
  
##  <a name="drawgeometry"></a>  CRenderTarget::DrawGeometry  
 Рисование контура указанным геометрического объекта с использованием стиля, указанного штриха.  
  
```  
void DrawGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pGeometry*  
 Geometry для отрисовки.  
  
 *pBrush*  
 Кисть для отрисовки обводки геометрии.  
  
 *fStrokeWidth*  
 Толщину обводки геометрии. Штриха центрируется на геометрии структуры.  
  
 *strokeStyle*  
 Стиль штриха для применения структуры геометрии, или значение NULL для закрашивания сплошной штриха.  
  
##  <a name="drawglyphrun"></a>  CRenderTarget::DrawGlyphRun  
 Рисует указанный глифов.  
  
```  
void DrawGlyphRun(
    const CD2DPointF& ptBaseLineOrigin,  
    const DWRITE_GLYPH_RUN& glyphRun,  
    CD2DBrush* pForegroundBrush,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>Параметры  
 *ptBaseLineOrigin*  
 Источник в аппаратно независимых пикселях Базовые глифы в объекте.  
  
 *glyphRun*  
 Глифы для отображения.  
  
 *pForegroundBrush*  
 Кисть для отрисовки указанного глифов.  
  
 *measuringMode*  
 Значение, указывающее, как метрики глифа используются для определения текста, при форматировании. Значение по умолчанию — DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawline"></a>  CRenderTarget::DrawLine  
 Проводит линию между заданными точками, с использованием стиля, указанного штриха.  
  
```  
void DrawLine(
    const CD2DPointF& ptFrom,  
    const CD2DPointF& ptTo,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *ptFrom*  
 Начальная точка строки в аппаратно независимых пикселях.  
  
 *ptTo*  
 Конечная точка строки в аппаратно независимых пикселях.  
  
 *pBrush*  
 Кисть для отрисовки линии обводки.  
  
 *fStrokeWidth*  
 Значение больше или равно 0, 0f, указывающее толщину обводки. Если этот параметр не указан, то по умолчанию 1, 0f. Штриха выравнивается по центру в строке.  
  
 *strokeStyle*  
 Стиль штриха рисования, или значение NULL для закрашивания сплошная линия.  
  
##  <a name="drawrectangle"></a>  CRenderTarget::DrawRectangle  
 Рисование контура прямоугольника, который имеет заданные размеры и стиль штриха.  
  
```  
void DrawRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *Rect*  
 Размеры прямоугольника для рисования в аппаратно независимых пикселях  
  
 *pBrush*  
 Кисть, используемую для отрисовки прямоугольника штриха  
  
 *fStrokeWidth*  
 Значение больше или равно 0, 0f, указывающее толщину обводки прямоугольника. Штриха центрируется на контура прямоугольника.  
  
 *strokeStyle*  
 Стиль штриха рисования, или значение NULL для закрашивания сплошной штриха.  
  
##  <a name="drawroundedrectangle"></a>  CRenderTarget::DrawRoundedRectangle  
 Рисование контура прямоугольника с закругленными углами указанным с использованием стиля, указанного штриха.  
  
```  
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *rectRounded*  
 Размеры прямоугольника с закругленными углами для отрисовки в аппаратно независимых пикселях.  
  
 *pBrush*  
 Кисть для отрисовки структуры Скругленный прямоугольник.  
  
 *fStrokeWidth*  
 Толщина штриха Скругленный прямоугольник. Штриха центрируется на структуры Скругленный прямоугольник. Значение по умолчанию — 1, 0f.  
  
 *strokeStyle*  
 Стиль штриха Скругленный прямоугольник, или значение NULL для закрашивания сплошной штриха. Значение по умолчанию — NULL.  
  
##  <a name="drawtext"></a>  CRenderTarget::DrawText  
 Рисует заданный текст, используя сведения о форматировании, предоставляемые IDWriteTextFormat объекта.  
  
```  
void DrawText(
    const CString& strText,  
    const CD2DRectF& rect,  
    CD2DBrush* pForegroundBrush,  
    CD2DTextFormat* textFormat = NULL,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>Параметры  
 *strText*  
 Указатель на массив знаков Юникода для рисования.  
  
 *Rect*  
 Размер и положение области, в которой рисуется текст.  
  
 *pForegroundBrush*  
 Кисть для отрисовки текста.  
  
 *textFormat*  
 Объект, который описывает форматирование сведений текст для отрисовки, например шрифт, размер шрифта и направление потока.  
  
 *Параметры*  
 Значение, указывающее, должны быть привязаны текст к границам ячейки и должно быть обрезано текст в прямоугольник размещения. Значение по умолчанию — D2D1_DRAW_TEXT_OPTIONS_NONE, который указывает, что текст должны быть привязаны к границам ячейки, и он не будет обрезано в прямоугольник размещения.  
  
 *measuringMode*  
 Значение, указывающее, как метрики глифа используются для определения текста, при форматировании. Значение по умолчанию — DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawtextlayout"></a>  CRenderTarget::DrawTextLayout  
 Рисует форматированный текст, описанной заданным объектом IDWriteTextLayout.  
  
```  
void DrawTextLayout(
    const CD2DPointF& ptOrigin,  
    CD2DTextLayout* textLayout,  
    CD2DBrush* pBrushForeground,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Параметры  
 *ptOrigin*  
 Точка, описанные в аппаратно независимых пикселях, на которых строится верхнего левого угла описываемого textLayout текста.  
  
 *textLayout*  
 Форматированный текст для отрисовки. Все эффекты рисования, которые не наследуются от ID2D1Resource игнорируются. При наличии эффекты рисования, наследующие от ID2D1Resource, не кисти, этот метод завершается ошибкой, и в целевом объекте отрисовки помещается в состоянии ошибки.  
  
 *pBrushForeground*  
 Кисть для отрисовки любой текст в textLayout, не имеет кисть, связанную с ним как эффекта рисования (указанный с помощью метода IDWriteTextLayout::SetDrawingEffect).  
  
 *Параметры*  
 Значение, указывающее, должны быть привязаны текст к границам ячейки и должно быть обрезано текст в прямоугольник размещения. Значение по умолчанию — D2D1_DRAW_TEXT_OPTIONS_NONE, который указывает, что текст должны быть привязаны к границам ячейки, и он не будет обрезано в прямоугольник размещения.  
  
##  <a name="enddraw"></a>  CRenderTarget::EndDraw  
 Завершает операций рисования в целевом объекте отрисовки и указывает текущее состояние ошибки и связанные с ними теги.  
  
```  
HRESULT EndDraw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="fillellipse"></a>  CRenderTarget::FillEllipse  
 Заполняет внутреннюю часть эллипса, заданного.  
  
```  
void FillEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Параметры  
 *эллипс*  
 Положение и radius в аппаратно независимых пикселях для рисования эллипса.  
  
 *pBrush*  
 Кисть, используемую для рисования внутренней части эллипса.  
  
##  <a name="fillgeometry"></a>  CRenderTarget::FillGeometry  
 Закрашивает внутреннюю часть указанного geometry.  
  
```  
void FillGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    CD2DBrush* pOpacityBrush = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pGeometry*  
 Geometry для рисования.  
  
 *pBrush*  
 Кисть, используемая для закрашивания геометрию внутренними.  
  
 *pOpacityBrush*  
 Маски непрозрачности для применения к геометрии; Значение NULL для маски непрозрачности отсутствуют. Если указан маски непрозрачности (параметр opacityBrush), кисти должен быть ID2D1BitmapBrush, который имеет значение D2D1_EXTEND_MODE_CLAMP режимов расширить x и y. Дополнительные сведения см. в разделе "Примечания".  
  
##  <a name="fillmesh"></a>  CRenderTarget::FillMesh  
 Закрашивает внутреннюю часть указанного сетки.  
  
```  
void FillMesh(
    CD2DMesh* pMesh,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Параметры  
 *pMesh*  
 Сетка для рисования.  
  
 *pBrush*  
 Кисть для отрисовки сетки.  
  
##  <a name="fillopacitymask"></a>  CRenderTarget::FillOpacityMask  
 Применяет маску непрозрачности, описываемых в указанном точечном рисунке кисти которая затем используется для заполнения области целевого объекта отрисовки.  
  
```  
void FillOpacityMask(
    CD2DBitmap* pOpacityMask,  
    CD2DBrush* pBrush,  
    D2D1_OPACITY_MASK_CONTENT content,  
    const CD2DRectF& rectDest,  
    const CD2DRectF& rectSrc);
```  
  
### <a name="parameters"></a>Параметры  
 *pOpacityMask*  
 Положение и radius в аппаратно независимых пикселях для рисования эллипса.  
  
 *pBrush*  
 Кисть для отрисовки области целевого объекта отрисовки, заданные destinationRectangle.  
  
 *содержимое*  
 Содержит тип содержимого с маской непрозрачности. Значение используется для определения цветовое пространство, в котором смешивается маски непрозрачности.  
  
 *rectDest*  
 Область рисования в аппаратно независимых пикселях целевого объекта отрисовки.  
  
 *rectSrc*  
 Область растрового изображения для использования в качестве маску непрозрачности в аппаратно независимых пикселях.  
  
##  <a name="fillrectangle"></a>  CRenderTarget::FillRectangle  
 Заполняет внутреннюю часть заданного прямоугольника.  
  
```  
void FillRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Параметры  
 *Rect*  
 Измерение прямоугольника для рисования в аппаратно независимых пикселях.  
  
 *pBrush*  
 Фона элемента кисть, используемую для отрисовки прямоугольника.  
  
##  <a name="fillroundedrectangle"></a>  CRenderTarget::FillRoundedRectangle  
 Закрашивает внутреннюю часть указанного Скругленный прямоугольник.  
  
```  
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Параметры  
 *rectRounded*  
 Размеры прямоугольника с закругленными углами для отрисовки в аппаратно-независимых пикселях.  
  
 *pBrush*  
 Кисть, используемую для рисования внутренней прямоугольника с закругленными углами.  
  
##  <a name="flush"></a>  CRenderTarget::Flush  
 Выполняет всех ожидающих применения команд рисования.  
  
```  
void Flush(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *tag1*  
 Содержит тег для рисования, вызвавших ошибки или 0, если ошибки отсутствуют. Этот параметр передается неинициализированным.  
  
 *tag2*  
 Содержит тег для рисования, вызвавших ошибки или 0, если ошибки отсутствуют. Этот параметр передается неинициализированным.  
  
##  <a name="getantialiasmode"></a>  CRenderTarget::GetAntialiasMode  
 Получает текущий режим сглаживания для нетекстовых графических операций.  
  
```  
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий режим сглаживания для нетекстовых операций рисования.  
  
##  <a name="getdpi"></a>  CRenderTarget::GetDpi  
 Возвращает целевой точек на дюйм (DPI) для подготовки к просмотру  
  
```  
CD2DSizeF GetDpi() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целевой объект отрисовки точек на дюйм (DPI).  
  
##  <a name="getmaximumbitmapsize"></a>  CRenderTarget::GetMaximumBitmapSize  
 Возвращает максимальный размер в единицах зависящие от устройства (в пикселях), любое измерение одного точечного рисунка, поддерживаемые в целевом объекте отрисовки  
  
```  
UINT32 GetMaximumBitmapSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальный размер в пикселях любого измерения одного точечного рисунка, поддерживаемые в целевом объекте отрисовки  
  
##  <a name="getpixelformat"></a>  CRenderTarget::GetPixelFormat  
 Возвращает режим формат и альфа-пиксель целевого объекта отрисовки  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Формат и альфа-режим пиксель целевого объекта отрисовки  
  
##  <a name="getpixelsize"></a>  CRenderTarget::GetPixelSize  
 Возвращает размер целевого объекта отрисовки в пикселях устройства  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер целевого объекта отрисовки в пикселях устройства  
  
##  <a name="getrendertarget"></a>  CRenderTarget::GetRenderTarget  
 Возвращает интерфейс ID2D1RenderTarget  
  
```  
ID2D1RenderTarget* GetRenderTarget();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1RenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getsize"></a>  CRenderTarget::GetSize  
 Возвращает размер целевого объекта отрисовки в аппаратно независимых пикселях  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий размер целевого объекта отрисовки в аппаратно независимых пикселях  
  
##  <a name="gettags"></a>  CRenderTarget::GetTags  
 Возвращает метку для последующих операций рисования.  
  
```  
void GetTags(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *tag1*  
 Содержит первую метку для последующих операций рисования. Этот параметр передается неинициализированным. Если задано значение NULL, значение не извлекается для этого параметра.  
  
 *tag2*  
 Содержит второй метки для последующих операций рисования. Этот параметр передается неинициализированным. Если задано значение NULL, значение не извлекается для этого параметра.  
  
##  <a name="gettextantialiasmode"></a>  CRenderTarget::GetTextAntialiasMode  
 Возвращает текущий режим сглаживания для текста и операций рисования глифов.  
  
```  
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий режим сглаживания для текста и операций рисования глифов.  
  
##  <a name="gettextrenderingparams"></a>  CRenderTarget::GetTextRenderingParams  
 Возвращает целевой объект отрисовки текущие параметры отрисовки текста.  
  
```  
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```  
  
### <a name="parameters"></a>Параметры  
 *textRenderingParams*  
 По возвращении из этого метода textRenderingParamscontains адрес указателя в целевом объекте отрисовки текущего параметры отрисовки текста.  
  
##  <a name="gettransform"></a>  CRenderTarget::GetTransform  
 Применяет указанное преобразование в целевом объекте отрисовки, заменив существующий преобразования. Все последующие операции рисования происходят в преобразованный пространства.  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Параметры  
 *transform*  
 Преобразования для применения в целевом объекте отрисовки.  
  
##  <a name="issupported"></a>  CRenderTarget::IsSupported  
 Указывает, поддерживает ли целевой объект отрисовки указанные свойства  
  
```  
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *renderTargetProperties*  
 Свойства целевого объекта отрисовки для тестирования  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если свойства целевого объекта отрисовки указанного поддерживаются этот целевой объект отрисовки; в противном случае — значение FALSE  
  
##  <a name="isvalid"></a>  CRenderTarget::IsValid  
 Проверяет допустимость ресурсов  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_lstresources"></a>  CRenderTarget::m_lstResources  
 Список указателей на объекты CD2DResource.  
  
```  
CObList m_lstResources;  
```  
  
##  <a name="m_prendertarget"></a>  CRenderTarget::m_pRenderTarget  
 Указатель на объект ID2D1RenderTarget.  
  
```  
ID2D1RenderTarget* m_pRenderTarget;  
```  
  
##  <a name="m_ptextformatdefault"></a>  CRenderTarget::m_pTextFormatDefault  
 Указатель на объект CD2DTextFormat, который содержит текстовый формат по умолчанию.  
  
```  
CD2DTextFormat* m_pTextFormatDefault;  
```  
  
##  <a name="operator_id2d1rendertarget_star"></a>  CRenderTarget::operator ID2D1RenderTarget *  
 Возвращает интерфейс ID2D1RenderTarget  
  
```  
operator ID2D1RenderTarget*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1RenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="popaxisalignedclip"></a>  CRenderTarget::PopAxisAlignedClip  
 Удаляет последний выровненный по осям клип из целевого объекта отрисовки. После вызова этого метода, клип больше не применяется для последующих операций рисования.  
  
```  
void PopAxisAlignedClip();
```  
  
##  <a name="poplayer"></a>  CRenderTarget::PopLayer  
 Останавливает перенаправление операций рисования с уровнем, определяется последней PushLayer вызова.  
  
```  
void PopLayer();
```  
  
##  <a name="pushaxisalignedclip"></a>  CRenderTarget::PushAxisAlignedClip  
 Удаляет последний выровненный по осям клип из целевого объекта отрисовки. После вызова этого метода, клип больше не применяется для последующих операций рисования.  
  
```  
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,  
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```  
  
### <a name="parameters"></a>Параметры  
 *rectClip*  
 Размер и положение области отсечения в аппаратно независимых пикселях.  
  
 *mode*  
 Режим сглаживания, который используется для отрисовки краев clip прямоугольники, имеют субточечное границы и blend клип с содержимым сцены. Наложение выполняется после при вызывается метод PopAxisAlignedClip и не относится к каждый примитив, на уровне.  
  
##  <a name="pushlayer"></a>  CRenderTarget::PushLayer  
 Добавляет указанный слой в целевом объекте отрисовки, чтобы он получает все последующие операции рисования, пока не будет вызван PopLayer.  
  
```  
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,  
    CD2DLayer& layer);
```  
  
### <a name="parameters"></a>Параметры  
 *layerParameters*  
 Границы содержимого, геометрические маски, прозрачность, маской непрозрачности и параметры сглаживания для слоя.  
  
 *слой*  
 Уровень, который получает последующих операций рисования.  
  
##  <a name="restoredrawingstate"></a>  CRenderTarget::RestoreDrawingState  
 Задает состояние рисования целевой объект отрисовки, указанным ID2D1DrawingStateBlock.  
  
```  
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```  
  
### <a name="parameters"></a>Параметры  
 *drawingStateBlock*  
 Новое состояние рисования целевого объекта отрисовки.  
  
##  <a name="savedrawingstate"></a>  CRenderTarget::SaveDrawingState  
 Сохраняет текущее состояние отображения для указанного ID2D1DrawingStateBlock.  
  
```  
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *drawingStateBlock*  
 По возвращении из этого метода содержит текущее состояние отображения целевого объекта отрисовки. Этот параметр необходимо инициализировать перед передачей его в метод.  
  
##  <a name="setantialiasmode"></a>  CRenderTarget::SetAntialiasMode  
 Задает режим сглаживания целевого объекта отрисовки. Режим сглаживания применяет все последующие операции рисования, за исключением текста и операций рисования глифов.  
  
```  
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```  
  
### <a name="parameters"></a>Параметры  
 *antialiasMode*  
 Режим сглаживания для будущих операций рисования.  
  
##  <a name="setdpi"></a>  CRenderTarget::SetDpi  
 Задает размер в точках на дюйм (DPI) целевого объекта отрисовки.  
  
```  
void SetDpi(const CD2DSizeF& sizeDPI);
```  
  
### <a name="parameters"></a>Параметры  
 *sizeDPI*  
 Значение больше или равно 0, указывающее горизонтальное/verticalDPI целевого объекта отрисовки.  
  
##  <a name="settags"></a>  CRenderTarget::SetTags  
 Задает метку для последующих операций рисования.  
  
```  
void SetTags(
    D2D1_TAG tag1,  
    D2D1_TAG tag2);
```  
  
### <a name="parameters"></a>Параметры  
 *tag1*  
 Метку для применения для последующих операций рисования.  
  
 *tag2*  
 Метку для применения для последующих операций рисования.  
  
##  <a name="settextantialiasmode"></a>  CRenderTarget::SetTextAntialiasMode  
 Задает режим сглаживания, который будет использоваться для последующего текста и операции рисования глифов.  
  
```  
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```  
  
### <a name="parameters"></a>Параметры  
 *textAntialiasMode*  
 Режим сглаживания, используемый для последующего текста и операций рисования глифов.  
  
##  <a name="settextrenderingparams"></a>  CRenderTarget::SetTextRenderingParams  
 Указывает параметры отрисовки текста, применяемые ко всем весь последующий текст и операций рисования глифов.  
  
```  
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *textRenderingParams*  
 Параметры отрисовки текста, применяемые ко всем весь последующий текст и глиф операции; Значение NULL, чтобы очистить текущие параметры отрисовки текста.  
  
##  <a name="settransform"></a>  CRenderTarget::SetTransform  
 Применяет указанное преобразование в целевом объекте отрисовки, заменив существующий преобразования. Все последующие операции рисования происходят в преобразованный пространства.  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);  
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```  
  
### <a name="parameters"></a>Параметры  
 *transform*  
 Преобразования для применения в целевом объекте отрисовки.  
  
##  <a name="verifyresource"></a>  CRenderTarget::VerifyResource  
 Проверяет допустимость объекта CD2DResource; Создает объект, если он еще не существует.  
  
```  
BOOL VerifyResource(CD2DResource* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 *pResource*  
 Указатель на объект CD2DResource.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, объект, если допустимый; в противном случае — значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
