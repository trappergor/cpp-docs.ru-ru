---
title: "Класс CRenderTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CRenderTarget class
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6f77d482e7ee3bf0798ad488067893b3712aac62
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="crendertarget-class"></a>Класс CRenderTarget
Программа-оболочка для ID2D1RenderTarget.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CRenderTarget : public CObject;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRenderTarget::CRenderTarget](#crendertarget)|Создает объект CRenderTarget.|  
|[CRenderTarget:: ~ CRenderTarget](#crendertarget__~crendertarget)|Деструктор Вызывается при уничтожении целевой объект отрисовки.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRenderTarget::Attach](#attach)|Присоединяет существующую отображения интерфейса целевой объект|  
|[CRenderTarget::BeginDraw](#begindraw)|Инициирует рисование на данный целевой объект отрисовки.|  
|[CRenderTarget::Clear](#clear)|Очищает область рисования указанный цвет.|  
|[CRenderTarget::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|Преобразует значения цвета и альфа-GDI D2D1_COLOR_F объекта.|  
|[CRenderTarget::CreateCompatibleRenderTarget](#createcompatiblerendertarget)|Создает новую цель визуализации точечного рисунка для использования во время промежуточного созданного рисунка, совместимую с текущей целевой объект отрисовки.|  
|[CRenderTarget::Destroy](#destroy)|Удаляет один или несколько ресурсов|  
|[CRenderTarget::Detach](#detach)|Отсоединяет визуализации интерфейса целевого объекта|  
|[CRenderTarget::DrawBitmap](#drawbitmap)|Рисование форматированного текста, описанной заданным объектом IDWriteTextLayout.|  
|[CRenderTarget::DrawEllipse](#drawellipse)|Рисование контура указанным эллипса с использованием стиля, указанного штриха.|  
|[CRenderTarget::DrawGeometry](#drawgeometry)|Рисование контура указанным геометрического объекта с использованием стиля, указанного штриха.|  
|[CRenderTarget::DrawGlyphRun](#drawglyphrun)|Рисует указанный глифы.|  
|[CRenderTarget::DrawLine](#drawline)|Проводит линию между заданными точками, с использованием стиля, указанного штриха.|  
|[CRenderTarget::DrawRectangle](#drawrectangle)|Рисование контура прямоугольника, который имеет указанные размеры и стиля обводки.|  
|[CRenderTarget::DrawRoundedRectangle](#drawroundedrectangle)|Рисование контура прямоугольника с закругленными углами указанным с использованием стиля, указанного штриха.|  
|[CRenderTarget::DrawText](#drawtext)|Рисует заданный текст, используя сведения о форматировании, предоставляемый объект IDWriteTextFormat.|  
|[CRenderTarget::DrawTextLayout](#drawtextlayout)|Рисование форматированного текста, описанной заданным объектом IDWriteTextLayout.|  
|[CRenderTarget::EndDraw](#enddraw)|Завершает операции рисования на целевой объект отрисовки и указывает текущее состояние ошибки и связанные с ними теги.|  
|[CRenderTarget::FillEllipse](#fillellipse)|Заполняет внутреннюю часть эллипса, заданного.|  
|[CRenderTarget::FillGeometry](#fillgeometry)|Заполняет внутреннюю часть заданной геометрий.|  
|[CRenderTarget::FillMesh](#fillmesh)|Заполняет внутреннюю часть указанного сетки.|  
|[CRenderTarget::FillOpacityMask](#fillopacitymask)|Применяет маску непрозрачности, описываемого в указанном точечном рисунке кисти которая затем используется для заполнения области цели отрисовки.|  
|[CRenderTarget::FillRectangle](#fillrectangle)|Заполняет внутреннюю часть указанного прямоугольника.|  
|[CRenderTarget::FillRoundedRectangle](#fillroundedrectangle)|Заполняет внутреннюю часть указанного прямоугольника со скругленными.|  
|[CRenderTarget::Flush](#flush)|Выполняет всех ожидающих применения команд рисования.|  
|[CRenderTarget::GetAntialiasMode](#getantialiasmode)|Получает текущий режим сглаживания для нетекстовых операций рисования.|  
|[CRenderTarget::GetDpi](#getdpi)|Возвращает визуализации целевого объекта в точках на дюйм (DPI)|  
|[CRenderTarget::GetMaximumBitmapSize](#getmaximumbitmapsize)|Получает максимальный размер в единицах зависящих от устройства (в пикселях), любого измерения одного изображения, поддерживаемый целевой объект отрисовки|  
|[CRenderTarget::GetPixelFormat](#getpixelformat)|Получает режим формат и альфа-пиксель целевого объекта отрисовки|  
|[CRenderTarget::GetPixelSize](#getpixelsize)|Возвращает размер целевого объекта отрисовки в пикселях устройства|  
|[CRenderTarget::GetRenderTarget](#getrendertarget)|Возвращает интерфейс ID2D1RenderTarget|  
|[CRenderTarget::GetSize](#getsize)|Возвращает размер целевого объекта отрисовки в аппаратно независимые пиксели|  
|[CRenderTarget::GetTags](#gettags)|Возвращает метку для последующих операций рисования.|  
|[CRenderTarget::GetTextAntialiasMode](#gettextantialiasmode)|Возвращает текущий режим сглаживания для текста и глиф операций рисования.|  
|[CRenderTarget::GetTextRenderingParams](#gettextrenderingparams)|Возвращает целевой объект отрисовки текущие параметры отрисовки текста.|  
|[CRenderTarget::GetTransform](#gettransform)|Применяет указанное преобразование в объект рендеринга, заменив существующее преобразование. Все последующие операции рисования происходят в преобразованные места.|  
|[CRenderTarget::IsSupported](#issupported)|Указывает, поддерживает ли объект рендеринга указанные свойства|  
|[CRenderTarget::IsValid](#isvalid)|Проверяет допустимость ресурсов|  
|[CRenderTarget::PopAxisAlignedClip](#popaxisalignedclip)|Удаляет последний выровненный по осям клип из целевого объекта отрисовки. После вызова этого метода клип больше не применяется к последующие операции рисования.|  
|[CRenderTarget::PopLayer](#poplayer)|Останавливает перенаправление операций рисования слой, на котором определяется последней PushLayer вызова.|  
|[CRenderTarget::PushAxisAlignedClip](#pushaxisalignedclip)|Удаляет последний выровненный по осям клип из целевого объекта отрисовки. После вызова этого метода клип больше не применяется к последующие операции рисования.|  
|[CRenderTarget::PushLayer](#pushlayer)|Добавляет указанный слой целевой объект отрисовки, который получает все последующие операции рисования, пока не будет вызван PopLayer.|  
|[CRenderTarget::RestoreDrawingState](#restoredrawingstate)|Задает состояние рисования целевой объект отрисовки, указанным ID2D1DrawingStateBlock.|  
|[CRenderTarget::SaveDrawingState](#savedrawingstate)|Сохраняет текущее состояние отображения для указанного ID2D1DrawingStateBlock.|  
|[CRenderTarget::SetAntialiasMode](#setantialiasmode)|Задает режим сглаживания целевого объекта отрисовки. Режим сглаживания применяется ко всем последующим операциям рисования, за исключением текста и глиф операций рисования.|  
|[CRenderTarget::SetDpi](#setdpi)|Задает число точек на дюйм (DPI) целевого объекта отрисовки.|  
|[CRenderTarget::SetTags](#settags)|Задает метку для последующих операций рисования.|  
|[CRenderTarget::SetTextAntialiasMode](#settextantialiasmode)|Задает режим сглаживания для последующего текста и операции рисования глифов.|  
|[CRenderTarget::SetTextRenderingParams](#settextrenderingparams)|Указывает параметры отрисовки текста для применения ко всем весь последующий текст и глиф операций рисования.|  
|[CRenderTarget::SetTransform](#settransform)|Перегружен. Применяет указанное преобразование в объект рендеринга, заменив существующее преобразование. Все последующие операции рисования происходят в преобразованные места.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRenderTarget::VerifyResource](#verifyresource)|Проверяет допустимость CD2DResource объекта; Создает объект, если он еще не существует.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget *](#operator_id2d1rendertarget_star)|Возвращает интерфейс ID2D1RenderTarget|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRenderTarget::m_lstResources](#m_lstresources)|Список указателей на объекты CD2DResource.|  
|[CRenderTarget::m_pRenderTarget](#m_prendertarget)|Указатель на объект ID2D1RenderTarget.|  
|[CRenderTarget::m_pTextFormatDefault](#m_ptextformatdefault)|Указатель на объект CD2DTextFormat, содержащий текстовом формате по умолчанию.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="_dtorcrendertarget"></a>CRenderTarget:: ~ CRenderTarget  
 Деструктор Вызывается при уничтожении целевой объект отрисовки.  
  
```  
virtual ~CRenderTarget();
```  
  
##  <a name="attach"></a>CRenderTarget::Attach  
 Присоединяет существующую отображения интерфейса целевой объект  
  
```  
void Attach(ID2D1RenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `pRenderTarget`  
 Существующий интерфейс целевой отрисовки. Не может иметь значение NULL  
  
##  <a name="begindraw"></a>CRenderTarget::BeginDraw  
 Инициирует рисование на данный целевой объект отрисовки.  
  
```  
void BeginDraw();
```  
  
##  <a name="clear"></a>CRenderTarget::Clear  
 Очищает область рисования указанный цвет.  
  
```  
void Clear(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 Цвет, для которой очищается области рисования.  
  
##  <a name="colorref_to_d2dcolor"></a>CRenderTarget::COLORREF_TO_D2DCOLOR  
 Преобразует значения цвета и альфа-GDI D2D1_COLOR_F объекта.  
  
```  
static D2D1_COLOR_F COLORREF_TO_D2DCOLOR(
    COLORREF color,  
    int nAlpha = 255);
```  
  
### <a name="parameters"></a>Параметры  
 `color`  
 RGB-значение.  
  
 `nAlpha`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение D2D1_COLOR_F.  
  
##  <a name="createcompatiblerendertarget"></a>CRenderTarget::CreateCompatibleRenderTarget  
 Создает новую цель визуализации точечного рисунка для использования во время промежуточного созданного рисунка, совместимую с текущей целевой объект отрисовки.  
  
```  
BOOL CreateCompatibleRenderTarget(
    CBitmapRenderTarget& bitmapTarget,  
    CD2DSizeF sizeDesired = CD2DSizeF(0., 0.), 
    CD2DSizeU sizePixelDesired = CD2DSizeU(0, 0), 
    D2D1_PIXEL_FORMAT* desiredFormat = NULL,  
    D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS options = D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Параметры  
 `bitmapTarget`  
 При возвращении данного метода содержит адрес указателя на новую цель визуализации точечного рисунка. Этот параметр передается неинициализированным.  
  
 `sizeDesired`  
 Требуемый размер нового целевого объекта отрисовки в аппаратно независимые пиксели, если он должен отличаться от исходного целевой объект отрисовки, или NULL. Дополнительные сведения см. в разделе "Примечания".  
  
 `sizePixelDesired`  
 Требуемый размер нового целевого буфера визуализации в пикселях, если он должен отличаться от исходного целевой объект отрисовки, или NULL. Дополнительные сведения см. в разделе "Примечания".  
  
 `desiredFormat`  
 Желаемый формат пиксела и альфа-режим новой целевой объект отрисовки, или NULL. Если формат точек установлен на DXGI_FORMAT_UNKNOWN или если этот параметр имеет значение null, новый рендеринга использует тот же формат пикселей, как исходный целевой объект отрисовки. Если альфа-режим — D2D1_ALPHA_MODE_UNKNOWN или этот параметр имеет значение NULL, альфа-режим нового целевого объекта отрисовки по умолчанию D2D1_ALPHA_MODE_PREMULTIPLIED. Сведения о поддерживаемых форматов пикселей см. Поддерживаемые форматы точек и режимов альфа-канала.  
  
 `options`  
 Значение, указывающее, является ли новый объект визуализации должен быть совместим с GDI.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае возвращает значение FALSE.  
  
##  <a name="crendertarget"></a>CRenderTarget::CRenderTarget  
 Создает объект CRenderTarget.  
  
```  
CRenderTarget();
```  
  
##  <a name="destroy"></a>CRenderTarget::Destroy  
 Удаляет один или несколько ресурсов  
  
```  
BOOL Destroy(BOOL bDeleteResources = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bDeleteResources`  
 Если bDeleteResources имеет значение TRUE, все ресурсы, расположенные в m_lstResources будет автоматически удаляется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение TRUE. В противном случае она возвращает значение FALSE  
  
##  <a name="detach"></a>CRenderTarget::Detach  
 Отсоединяет визуализации интерфейса целевого объекта  
  
```  
ID2D1RenderTarget* Detach ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на отсоединенные отображения интерфейса целевой.  
  
##  <a name="drawbitmap"></a>CRenderTarget::DrawBitmap  
 Рисование форматированного текста, описанной заданным объектом IDWriteTextLayout.  
  
```  
void DrawBitmap(
    CD2DBitmap* pBitmap,  
    const CD2DRectF& rectDest,  
    float fOpacity = 1.0,  
    D2D1_BITMAP_INTERPOLATION_MODE interpolationMode = D2D1_BITMAP_INTERPOLATION_MODE_LINEAR,  
    const CD2DRectF* pRectSrc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pBitmap`  
 Растровое изображение для отображения.  
  
 `rectDest`  
 Размер и положение в аппаратно независимые пиксели в пространстве координат целевого объекта отрисовки области, к которой рисуется растровое изображение. Если прямоугольник не хорошо организованных, не выводится ничего, но целевой объект отрисовки не входит в состояние ошибки.  
  
 `fOpacity`  
 Значение в диапазоне от 0, 0f до 1.0f включительно, указывающее значение непрозрачности для применения к растрового изображения. Это значение умножается на альфа-значения содержимое растрового изображения.  
  
 `interpolationMode`  
 Режим интерполяции, если точечный рисунок масштабировать или поворачивать операции рисования.  
  
 `pRectSrc`  
 Размер и положение в аппаратно независимые пиксели в пространстве координат точечного рисунка области внутри точечного рисунка для рисования.  
  
##  <a name="drawellipse"></a>CRenderTarget::DrawEllipse  
 Рисование контура указанным эллипса с использованием стиля, указанного штриха.  
  
```  
void DrawEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `ellipse`  
 Позиция и радиус эллипса для рисования в аппаратно независимые пиксели.  
  
 `pBrush`  
 Кисть, используемую для рисования контура эллипса.  
  
 `fStrokeWidth`  
 Толщина штрихов эллипса. Штриха ориентирован на контура эллипса.  
  
 `strokeStyle`  
 Стиль штриха, чтобы применить контура эллипса, или значение NULL для рисования штриха сплошной.  
  
##  <a name="drawgeometry"></a>CRenderTarget::DrawGeometry  
 Рисование контура указанным геометрического объекта с использованием стиля, указанного штриха.  
  
```  
void DrawGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pGeometry`  
 Geometry для отрисовки.  
  
 `pBrush`  
 Кисть, используемая для закрашивания обводки геометрии.  
  
 `fStrokeWidth`  
 Толщину обводки геометрии. Штриха ориентирован на структуры геометрии.  
  
 `strokeStyle`  
 Стиль штриха, назначаемое геометрии структуры или значение NULL, чтобы нарисовать сплошной штриха.  
  
##  <a name="drawglyphrun"></a>CRenderTarget::DrawGlyphRun  
 Рисует указанный глифы.  
  
```  
void DrawGlyphRun(
    const CD2DPointF& ptBaseLineOrigin,  
    const DWRITE_GLYPH_RUN& glyphRun,  
    CD2DBrush* pForegroundBrush,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>Параметры  
 `ptBaseLineOrigin`  
 Источник в аппаратно независимые пиксели показателя нужные глифы.  
  
 `glyphRun`  
 Глифы для отображения.  
  
 `pForegroundBrush`  
 Кисть, используемая для закрашивания указанного глифов.  
  
 `measuringMode`  
 Значение, указывающее, как метрики глифа используются для измерения текст при его форматировании. Значение по умолчанию — DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawline"></a>CRenderTarget::DrawLine  
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
 `ptFrom`  
 Начальная точка в строке, аппаратно независимые пиксели.  
  
 `ptTo`  
 Конечная точка в строке, аппаратно независимые пиксели.  
  
 `pBrush`  
 Кисть, используемую для рисования линии штриха.  
  
 `fStrokeWidth`  
 Значение больше или равное 0, 0f, указывающее толщину обводки. Если этот параметр не указан, по умолчанию используется значение 1.0f. Штриха выравнивается по центру в строке.  
  
 `strokeStyle`  
 Стиль штриха paint или значение NULL, чтобы нарисовать сплошной линией.  
  
##  <a name="drawrectangle"></a>CRenderTarget::DrawRectangle  
 Рисование контура прямоугольника, который имеет указанные размеры и стиля обводки.  
  
```  
void DrawRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Размеры прямоугольника для рисования в аппаратно независимые пиксели  
  
 `pBrush`  
 Кисть, которая используется для рисования штриха прямоугольника  
  
 `fStrokeWidth`  
 Значение больше или равное 0, 0f, ширина штриха прямоугольника. Штриха ориентирован на контур прямоугольника.  
  
 `strokeStyle`  
 Стиль штриха paint или значение NULL, чтобы нарисовать сплошной штриха.  
  
##  <a name="drawroundedrectangle"></a>CRenderTarget::DrawRoundedRectangle  
 Рисование контура прямоугольника с закругленными углами указанным с использованием стиля, указанного штриха.  
  
```  
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `rectRounded`  
 Размеры прямоугольника с закругленными углами для рисования в аппаратно независимые пиксели.  
  
 `pBrush`  
 Кисть, используемую для рисования контура с закругленными углами.  
  
 `fStrokeWidth`  
 Ширина штриха с закругленными углами. Штриха ориентирован на структуры с закругленными углами. Значение по умолчанию — 1.0f.  
  
 `strokeStyle`  
 Стиль штриха Скругленный прямоугольник или значение NULL, чтобы нарисовать сплошной штриха. Значение по умолчанию — NULL.  
  
##  <a name="drawtext"></a>CRenderTarget::DrawText  
 Рисует заданный текст, используя сведения о форматировании, предоставляемый объект IDWriteTextFormat.  
  
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
 `strText`  
 Указатель на массив знаков Юникода для рисования.  
  
 `rect`  
 Размер и положение области, в которой отображается текст.  
  
 `pForegroundBrush`  
 Кисть, используемую для рисования текста.  
  
 `textFormat`  
 Объект, описывающий форматирование сведения текст для отрисовки, например шрифт, размер шрифта и направление потока.  
  
 `options`  
 Значение, указывающее, должны быть привязаны текст к границам ячейки и должно быть обрезано текст в прямоугольник. Значение по умолчанию — D2D1_DRAW_TEXT_OPTIONS_NONE, что означает, что текст будут привязаны к границам ячейки, и он не будет обрезано в прямоугольник размещения.  
  
 `measuringMode`  
 Значение, указывающее, как метрики глифа используются для измерения текст при его форматировании. Значение по умолчанию — DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawtextlayout"></a>CRenderTarget::DrawTextLayout  
 Рисование форматированного текста, описанной заданным объектом IDWriteTextLayout.  
  
```  
void DrawTextLayout(
    const CD2DPointF& ptOrigin,  
    CD2DTextLayout* textLayout,  
    CD2DBrush* pBrushForeground,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Параметры  
 `ptOrigin`  
 Точка, описанные в аппаратно независимые пиксели, в которых строится угла верхнего левого описываемых textLayout текст.  
  
 `textLayout`  
 Форматированный текст для рисования. Эффекты рисования не наследуют от ID2D1Resource игнорируются. Если эффекты рисования, наследующие от ID2D1Resource, не кисти, этот метод завершается ошибкой и целевой объект отрисовки помещается в состояние ошибки.  
  
 `pBrushForeground`  
 Кисть, используемая для закрашивания любой текст в textLayout, у которых уже нет кисти, связанные с ним как эффекта рисования (указанный с помощью метода IDWriteTextLayout::SetDrawingEffect).  
  
 `options`  
 Значение, указывающее, должны быть привязаны текст к границам ячейки и должно быть обрезано текст в прямоугольник. Значение по умолчанию — D2D1_DRAW_TEXT_OPTIONS_NONE, что означает, что текст будут привязаны к границам ячейки, и он не будет обрезано в прямоугольник размещения.  
  
##  <a name="enddraw"></a>CRenderTarget::EndDraw  
 Завершает операции рисования на целевой объект отрисовки и указывает текущее состояние ошибки и связанные с ними теги.  
  
```  
HRESULT EndDraw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="fillellipse"></a>CRenderTarget::FillEllipse  
 Заполняет внутреннюю часть эллипса, заданного.  
  
```  
void FillEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Параметры  
 `ellipse`  
 Позиция и radius в аппаратно независимые пиксели для рисования эллипса.  
  
 `pBrush`  
 Кисть, используемую для рисования внутренней части эллипса.  
  
##  <a name="fillgeometry"></a>CRenderTarget::FillGeometry  
 Заполняет внутреннюю часть заданной геометрий.  
  
```  
void FillGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    CD2DBrush* pOpacityBrush = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pGeometry`  
 Геометрия для рисования.  
  
 `pBrush`  
 Кисть для закрашивания geometry внутренними.  
  
 `pOpacityBrush`  
 Маска непрозрачности для применения к геометрии; Значение NULL для маски непрозрачности отсутствуют. Если указан маски непрозрачности (параметр opacityBrush), кисти должен быть ID2D1BitmapBrush, имеющий значение D2D1_EXTEND_MODE_CLAMP режимов расширения x и y. Дополнительные сведения см. в разделе "Примечания".  
  
##  <a name="fillmesh"></a>CRenderTarget::FillMesh  
 Заполняет внутреннюю часть указанного сетки.  
  
```  
void FillMesh(
    CD2DMesh* pMesh,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Параметры  
 `pMesh`  
 Сетка для рисования.  
  
 `pBrush`  
 Кисть, используемая для закрашивания сетки.  
  
##  <a name="fillopacitymask"></a>CRenderTarget::FillOpacityMask  
 Применяет маску непрозрачности, описываемого в указанном точечном рисунке кисти которая затем используется для заполнения области цели отрисовки.  
  
```  
void FillOpacityMask(
    CD2DBitmap* pOpacityMask,  
    CD2DBrush* pBrush,  
    D2D1_OPACITY_MASK_CONTENT content,  
    const CD2DRectF& rectDest,  
    const CD2DRectF& rectSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `pOpacityMask`  
 Позиция и radius в аппаратно независимые пиксели для рисования эллипса.  
  
 `pBrush`  
 Кисть, используемая для закрашивания области цели отрисовки, указанной destinationRectangle.  
  
 `content`  
 Содержит тип содержимого маска непрозрачности. Значение используется для определения цветовое пространство, в котором смешивается маска непрозрачности.  
  
 `rectDest`  
 Область рисования в аппаратно независимые пиксели целевого объекта отрисовки.  
  
 `rectSrc`  
 Регион для использования в качестве маски непрозрачности, в аппаратно независимые пиксели точечного рисунка.  
  
##  <a name="fillrectangle"></a>CRenderTarget::FillRectangle  
 Заполняет внутреннюю часть указанного прямоугольника.  
  
```  
void FillRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Измерение прямоугольника для рисования в аппаратно независимые пиксели.  
  
 `pBrush`  
 Кисть для закрашивания прямоугольника внутренними.  
  
##  <a name="fillroundedrectangle"></a>CRenderTarget::FillRoundedRectangle  
 Заполняет внутреннюю часть указанного прямоугольника со скругленными.  
  
```  
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Параметры  
 `rectRounded`  
 Размеры прямоугольника с закругленными углами для рисования в аппаратно-независимых точках.  
  
 `pBrush`  
 Кисть, используемую для рисования внутренней части прямоугольника с закругленными углами.  
  
##  <a name="flush"></a>CRenderTarget::Flush  
 Выполняет всех ожидающих применения команд рисования.  
  
```  
void Flush(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `tag1`  
 Содержит тег для рисования, вызвавшие ошибки или 0, если не содержит ошибок. Этот параметр передается неинициализированным.  
  
 `tag2`  
 Содержит тег для рисования, вызвавшие ошибки или 0, если не содержит ошибок. Этот параметр передается неинициализированным.  
  
##  <a name="getantialiasmode"></a>CRenderTarget::GetAntialiasMode  
 Получает текущий режим сглаживания для нетекстовых операций рисования.  
  
```  
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий режим сглаживания для нетекстовых операций рисования.  
  
##  <a name="getdpi"></a>CRenderTarget::GetDpi  
 Возвращает визуализации целевого объекта в точках на дюйм (DPI)  
  
```  
CD2DSizeF GetDpi() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целевой объект отрисовки в точках на дюйм (DPI).  
  
##  <a name="getmaximumbitmapsize"></a>CRenderTarget::GetMaximumBitmapSize  
 Получает максимальный размер в единицах зависящих от устройства (в пикселях), любого измерения одного изображения, поддерживаемый целевой объект отрисовки  
  
```  
UINT32 GetMaximumBitmapSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальный размер в пикселях любого измерения одного изображения, поддерживаемый целевой объект отрисовки  
  
##  <a name="getpixelformat"></a>CRenderTarget::GetPixelFormat  
 Получает режим формат и альфа-пиксель целевого объекта отрисовки  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Формат и альфа-режим пиксель целевого объекта отрисовки  
  
##  <a name="getpixelsize"></a>CRenderTarget::GetPixelSize  
 Возвращает размер целевого объекта отрисовки в пикселях устройства  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер целевого объекта отрисовки в пикселях устройства  
  
##  <a name="getrendertarget"></a>CRenderTarget::GetRenderTarget  
 Возвращает интерфейс ID2D1RenderTarget  
  
```  
ID2D1RenderTarget* GetRenderTarget();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1RenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="getsize"></a>CRenderTarget::GetSize  
 Возвращает размер целевого объекта отрисовки в аппаратно независимые пиксели  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий размер целевого объекта отрисовки в аппаратно независимые пиксели  
  
##  <a name="gettags"></a>CRenderTarget::GetTags  
 Возвращает метку для последующих операций рисования.  
  
```  
void GetTags(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `tag1`  
 Содержит первую метку для последующих операций рисования. Этот параметр передается неинициализированным. Если задано значение NULL, значение не будет получен для этого параметра.  
  
 `tag2`  
 Содержит второй метки для последующих операций рисования. Этот параметр передается неинициализированным. Если задано значение NULL, значение не будет получен для этого параметра.  
  
##  <a name="gettextantialiasmode"></a>CRenderTarget::GetTextAntialiasMode  
 Возвращает текущий режим сглаживания для текста и глиф операций рисования.  
  
```  
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий режим сглаживания для текста и глиф операций рисования.  
  
##  <a name="gettextrenderingparams"></a>CRenderTarget::GetTextRenderingParams  
 Возвращает целевой объект отрисовки текущие параметры отрисовки текста.  
  
```  
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```  
  
### <a name="parameters"></a>Параметры  
 `textRenderingParams`  
 По возвращении из этого метода textRenderingParamscontains адрес указателя в объект рендеринга текущего параметры отрисовки текста.  
  
##  <a name="gettransform"></a>CRenderTarget::GetTransform  
 Применяет указанное преобразование в объект рендеринга, заменив существующее преобразование. Все последующие операции рисования происходят в преобразованные места.  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Параметры  
 `transform`  
 Преобразование в объект рендеринга.  
  
##  <a name="issupported"></a>CRenderTarget::IsSupported  
 Указывает, поддерживает ли объект рендеринга указанные свойства  
  
```  
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `renderTargetProperties`  
 Свойства целевого объекта отрисовки для тестирования  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если указанный отрисовки целевые свойства поддерживаются этот целевой объект отрисовки; в противном случае — FALSE  
  
##  <a name="isvalid"></a>CRenderTarget::IsValid  
 Проверяет допустимость ресурсов  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ресурс является допустимым; в противном случае — значение FALSE.  
  
##  <a name="m_lstresources"></a>CRenderTarget::m_lstResources  
 Список указателей на объекты CD2DResource.  
  
```  
CObList m_lstResources;  
```  
  
##  <a name="m_prendertarget"></a>CRenderTarget::m_pRenderTarget  
 Указатель на объект ID2D1RenderTarget.  
  
```  
ID2D1RenderTarget* m_pRenderTarget;  
```  
  
##  <a name="m_ptextformatdefault"></a>CRenderTarget::m_pTextFormatDefault  
 Указатель на объект CD2DTextFormat, содержащий текстовом формате по умолчанию.  
  
```  
CD2DTextFormat* m_pTextFormatDefault;  
```  
  
##  <a name="operator_id2d1rendertarget_star"></a>CRenderTarget::operator ID2D1RenderTarget *  
 Возвращает интерфейс ID2D1RenderTarget  
  
```  
operator ID2D1RenderTarget*();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс ID2D1RenderTarget или значение NULL, если объект еще не инициализирован.  
  
##  <a name="popaxisalignedclip"></a>CRenderTarget::PopAxisAlignedClip  
 Удаляет последний выровненный по осям клип из целевого объекта отрисовки. После вызова этого метода клип больше не применяется к последующие операции рисования.  
  
```  
void PopAxisAlignedClip();
```  
  
##  <a name="poplayer"></a>CRenderTarget::PopLayer  
 Останавливает перенаправление операций рисования слой, на котором определяется последней PushLayer вызова.  
  
```  
void PopLayer();
```  
  
##  <a name="pushaxisalignedclip"></a>CRenderTarget::PushAxisAlignedClip  
 Удаляет последний выровненный по осям клип из целевого объекта отрисовки. После вызова этого метода клип больше не применяется к последующие операции рисования.  
  
```  
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,  
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```  
  
### <a name="parameters"></a>Параметры  
 `rectClip`  
 Размер и координата области отсечения в аппаратно независимые пиксели.  
  
 `mode`  
 Режим сглаживания, используемый для рисования края клип прямоугольники, имеют субточечное границы и blend клип с содержимым сцены. Наложение выполняется, как только при вызове метода PopAxisAlignedClip, не относится к каждый примитив, на одном уровне.  
  
##  <a name="pushlayer"></a>CRenderTarget::PushLayer  
 Добавляет указанный слой целевой объект отрисовки, который получает все последующие операции рисования, пока не будет вызван PopLayer.  
  
```  
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,  
    CD2DLayer& layer);
```  
  
### <a name="parameters"></a>Параметры  
 `layerParameters`  
 Границы содержимого, геометрические маски, прозрачность, маска непрозрачности и параметры сглаживания для слоя.  
  
 `layer`  
 Уровень, который получает последующие операции рисования.  
  
##  <a name="restoredrawingstate"></a>CRenderTarget::RestoreDrawingState  
 Задает состояние рисования целевой объект отрисовки, указанным ID2D1DrawingStateBlock.  
  
```  
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```  
  
### <a name="parameters"></a>Параметры  
 `drawingStateBlock`  
 Новое состояние рисования целевого объекта отрисовки.  
  
##  <a name="savedrawingstate"></a>CRenderTarget::SaveDrawingState  
 Сохраняет текущее состояние отображения для указанного ID2D1DrawingStateBlock.  
  
```  
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `drawingStateBlock`  
 При возвращении данного метода содержит текущее состояние рисования целевого объекта отрисовки. Этот параметр должен быть инициализирован перед его передачей в метод.  
  
##  <a name="setantialiasmode"></a>CRenderTarget::SetAntialiasMode  
 Задает режим сглаживания целевого объекта отрисовки. Режим сглаживания применяется ко всем последующим операциям рисования, за исключением текста и глиф операций рисования.  
  
```  
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```  
  
### <a name="parameters"></a>Параметры  
 `antialiasMode`  
 Режим сглаживания для будущих операций рисования.  
  
##  <a name="setdpi"></a>CRenderTarget::SetDpi  
 Задает число точек на дюйм (DPI) целевого объекта отрисовки.  
  
```  
void SetDpi(const CD2DSizeF& sizeDPI);
```  
  
### <a name="parameters"></a>Параметры  
 `sizeDPI`  
 Значение больше или равно нулю, указывает горизонтальное или verticalDPI целевого объекта отрисовки.  
  
##  <a name="settags"></a>CRenderTarget::SetTags  
 Задает метку для последующих операций рисования.  
  
```  
void SetTags(
    D2D1_TAG tag1,  
    D2D1_TAG tag2);
```  
  
### <a name="parameters"></a>Параметры  
 `tag1`  
 Метка для применения к последующие операции рисования.  
  
 `tag2`  
 Метка для применения к последующие операции рисования.  
  
##  <a name="settextantialiasmode"></a>CRenderTarget::SetTextAntialiasMode  
 Задает режим сглаживания для последующего текста и операции рисования глифов.  
  
```  
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```  
  
### <a name="parameters"></a>Параметры  
 `textAntialiasMode`  
 Режим сглаживания, используемый для последующего текста и глиф операций рисования.  
  
##  <a name="settextrenderingparams"></a>CRenderTarget::SetTextRenderingParams  
 Указывает параметры отрисовки текста для применения ко всем весь последующий текст и глиф операций рисования.  
  
```  
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `textRenderingParams`  
 Параметры отрисовки текста, применяемые ко всем весь последующий текст и глиф рисования; Значение NULL, чтобы очистить текущие параметры отрисовки текста.  
  
##  <a name="settransform"></a>CRenderTarget::SetTransform  
 Применяет указанное преобразование в объект рендеринга, заменив существующее преобразование. Все последующие операции рисования происходят в преобразованные места.  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);  
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```  
  
### <a name="parameters"></a>Параметры  
 `transform`  
 Преобразование в объект рендеринга.  
  
##  <a name="verifyresource"></a>CRenderTarget::VerifyResource  
 Проверяет допустимость CD2DResource объекта; Создает объект, если он еще не существует.  
  
```  
BOOL VerifyResource(CD2DResource* pResource);
```  
  
### <a name="parameters"></a>Параметры  
 `pResource`  
 Указатель на объект CD2DResource.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, объект результата проверки; в противном случае — значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

