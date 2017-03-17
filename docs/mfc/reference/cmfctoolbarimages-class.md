---
title: "Класс CMFCToolBarImages | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::AdaptColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::AddIcon
- AFXTOOLBARIMAGES/CMFCToolBarImages::AddImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::CleanUp
- AFXTOOLBARIMAGES/CMFCToolBarImages::Clear
- AFXTOOLBARIMAGES/CMFCToolBarImages::ConvertTo32Bits
- AFXTOOLBARIMAGES/CMFCToolBarImages::CopyImageToClipboard
- AFXTOOLBARIMAGES/CMFCToolBarImages::CopyTo
- AFXTOOLBARIMAGES/CMFCToolBarImages::CreateFromImageList
- AFXTOOLBARIMAGES/CMFCToolBarImages::CreateRegionFromImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::DeleteImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::Draw
- AFXTOOLBARIMAGES/CMFCToolBarImages::DrawEx
- AFXTOOLBARIMAGES/CMFCToolBarImages::EnableRTL
- AFXTOOLBARIMAGES/CMFCToolBarImages::EndDrawImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::ExtractIcon
- AFXTOOLBARIMAGES/CMFCToolBarImages::FillDitheredRect
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetAlwaysLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetBitsPerPixel
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetCount
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetDisabledImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetFadedImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageSize
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageWell
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageWellLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetLastImageRect
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetLightPercentage
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetMapTo3DColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetMask
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetResourceOffset
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetScale
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetTransparentColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::GrayImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::Is32BitTransparencySupported
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsPreMultiplyAutoCheck
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsRTL
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsReadOnly
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsScaled
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsUserImagesList
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsValid
- AFXTOOLBARIMAGES/CMFCToolBarImages::Load
- AFXTOOLBARIMAGES/CMFCToolBarImages::LoadStr
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapFromSysColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapTo3dColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapToSysColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapToSysColorAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::Mirror
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorBitmap
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorBitmapVert
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorVert
- AFXTOOLBARIMAGES/CMFCToolBarImages::OnSysColorChange
- AFXTOOLBARIMAGES/CMFCToolBarImages::PrepareDrawImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::Save
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetAlwaysLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetDisabledImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetFadedImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetImageSize
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetLightPercentage
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetMapTo3DColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetPreMultiplyAutoCheck
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetSingleImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetTransparentColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::SmoothResize
- AFXTOOLBARIMAGES/CMFCToolBarImages::UpdateImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::PreMultiplyAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::m_bDisableTrueColorAlpha
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarImages class
ms.assetid: d4e50518-9ffc-406f-9996-f79e5cd38155
caps.latest.revision: 31
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ff94497108033b17d52b79594fdbe30e8ed7da03
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarimages-class"></a>Класс CMFCToolBarImages
Изображения на панели инструментов. `CMFCToolBarImages` Класс управляет изображений панели инструментов, загруженными из ресурсов приложения или из файлов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCToolBarImages : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarImages::CMFCToolBarImages](#cmfctoolbarimages)|Создает объект `CMFCToolBarImages`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarImages::AdaptColors](#adaptcolors)||  
|[CMFCToolBarImages::AddIcon](#addicon)|Добавляет значок изображений панели инструментов.|  
|[CMFCToolBarImages::AddImage](#addimage)|Добавляет точечный рисунок изображений панели инструментов.|  
|[CMFCToolBarImages::CleanUp](#cleanup)||  
|[CMFCToolBarImages::Clear](#clear)|Освобождает системные ресурсы, выделенные для этого объекта.|  
|[CMFCToolBarImages::ConvertTo32Bits](#convertto32bits)|Преобразует подчеркнуть точечные рисунки в 32 bpp изображения.|  
|[CMFCToolBarImages::CopyImageToClipboard](#copyimagetoclipboard)||  
|[CMFCToolBarImages::CopyTo](#copyto)||  
|[CMFCToolBarImages::CreateFromImageList](#createfromimagelist)|Инициализирует изображений панели инструментов из списка изображений ( [класса CImageList](../../mfc/reference/cimagelist-class.md)).|  
|[CMFCToolBarImages::CreateRegionFromImage](#createregionfromimage)||  
|[CMFCToolBarImages::DeleteImage](#deleteimage)|Удаляет изображение с указанным индексом из изображений панели инструментов, если этот набор инструментов изображения содержит пользовательские изображения.|  
|[CMFCToolBarImages::Draw](#draw)|Рисует изображение одной панели инструментов (кнопка).|  
|[CMFCToolBarImages::DrawEx](#drawex)||  
|[CMFCToolBarImages::EnableRTL](#enablertl)||  
|[CMFCToolBarImages::EndDrawImage](#enddrawimage)|Освобождает системные ресурсы, нарисовав значок панели инструментов.|  
|[CMFCToolBarImages::ExtractIcon](#extracticon)|Возвращает значок, который имеет указанное изображение индекс из изображений панели инструментов.|  
|[CMFCToolBarImages::FillDitheredRect](#fillditheredrect)|Выполняет заливку прямоугольника с помощью кисти с цветами фона панели инструментов.|  
|[CMFCToolBarImages::GetAlwaysLight](#getalwayslight)||  
|[CMFCToolBarImages::GetBitsPerPixel](#getbitsperpixel)|Возвращает текущее разрешение изображения подчеркнутым.|  
|[CMFCToolBarImages::GetCount](#getcount)|Возвращает число образов, на панели инструментов.|  
|[CMFCToolBarImages::GetDisabledImageAlpha](#getdisabledimagealpha)|Возвращает значение альфа-канал, используемый для изображений отключено.|  
|[CMFCToolBarImages::GetFadedImageAlpha](#getfadedimagealpha)||  
|[CMFCToolBarImages::GetImageSize](#getimagesize)|Возвращает размер изображений панели инструментов, которые хранятся в памяти (размер источника) или размер изображений, отображаемых на экране (размер) на панели инструментов.|  
|[CMFCToolBarImages::GetImageWell](#getimagewell)|Возвращает дескриптор растровому изображению, которое содержит все изображения панели инструментов.|  
|[CMFCToolBarImages::GetImageWellLight](#getimagewelllight)||  
|[CMFCToolBarImages::GetLastImageRect](#getlastimagerect)||  
|[CMFCToolBarImages::GetLightPercentage](#getlightpercentage)||  
|[CMFCToolBarImages::GetMapTo3DColors](#getmapto3dcolors)||  
|[CMFCToolBarImages::GetMask](#getmask)||  
|[CMFCToolBarImages::GetResourceOffset](#getresourceoffset)|Возвращает индекс образа для указанного ресурса.|  
|[CMFCToolBarImages::GetScale](#getscale)|Возвращает текущий масштаб подчеркнутым изображений.|  
|[CMFCToolBarImages::GetTransparentColor](#gettransparentcolor)||  
|[CMFCToolBarImages::GrayImages](#grayimages)|Grays изображений панели инструментов выглядела отключено.|  
|[CMFCToolBarImages::Is32BitTransparencySupported](#is32bittransparencysupported)|Определяет, поддерживает ли операционная система альфа-смешение цвета 32 бита.|  
|[CMFCToolBarImages::IsPreMultiplyAutoCheck](#ispremultiplyautocheck)||  
|[CMFCToolBarImages::IsRTL](#isrtl)|Определяет, включена ли поддержка справа налево (RTL).|  
|[CMFCToolBarImages::IsReadOnly](#isreadonly)|Определяет, являются ли изображений панели инструментов только для чтения.|  
|[CMFCToolBarImages::IsScaled](#isscaled)|Указывает, масштабируется подчеркнутым изображения или нет.|  
|[CMFCToolBarImages::IsUserImagesList](#isuserimageslist)|Определяет, содержит ли этот набор инструментов образы пользовательских образов.|  
|[CMFCToolBarImages::IsValid](#isvalid)|Определяет, содержит ли этот набор изображений на панели инструментов значок допустимым панели инструментов.|  
|[CMFCToolBarImages::Load](#load)|Загрузка изображений панели инструментов из системных ресурсов или из файла.|  
|[CMFCToolBarImages::LoadStr](#loadstr)||  
|[CMFCToolBarImages::MapFromSysColor](#mapfromsyscolor)||  
|[CMFCToolBarImages::MapTo3dColors](#mapto3dcolors)||  
|[CMFCToolBarImages::MapToSysColor](#maptosyscolor)||  
|[CMFCToolBarImages::MapToSysColorAlpha](#maptosyscoloralpha)||  
|[CMFCToolBarImages::Mirror](#mirror)|Отражает все изображения панели инструментов по горизонтали.|  
|[CMFCToolBarImages::MirrorBitmap](#mirrorbitmap)|Горизонтальное отражение точечного рисунка.|  
|[CMFCToolBarImages::MirrorBitmapVert](#mirrorbitmapvert)||  
|[CMFCToolBarImages::MirrorVert](#mirrorvert)||  
|[CMFCToolBarImages::OnSysColorChange](#onsyscolorchange)||  
|[CMFCToolBarImages::PrepareDrawImage](#preparedrawimage)|Распределяет ресурсы, которые необходимо нарисовать изображение с панели инструментов с указанным размером.|  
|[CMFCToolBarImages::Save](#save)|Сохраняет в файле изображений панели инструментов, если этот набор инструментов изображения содержит пользовательские изображения.|  
|[CMFCToolBarImages::SetAlwaysLight](#setalwayslight)||  
|[CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha)|Задает значение альфа-канал, используемый для изображений отключено.|  
|[CMFCToolBarImages::SetFadedImageAlpha](#setfadedimagealpha)||  
|[CMFCToolBarImages::SetImageSize](#setimagesize)|Задает размер значка панели инструментов (размер источника).|  
|[CMFCToolBarImages::SetLightPercentage](#setlightpercentage)||  
|[CMFCToolBarImages::SetMapTo3DColors](#setmapto3dcolors)||  
|[CMFCToolBarImages::SetPreMultiplyAutoCheck](#setpremultiplyautocheck)||  
|[CMFCToolBarImages::SetSingleImage](#setsingleimage)||  
|[CMFCToolBarImages::SetTransparentColor](#settransparentcolor)|Задает прозрачный цвет изображения панели инструментов.|  
|[CMFCToolBarImages::SmoothResize](#smoothresize)|Плавно изменяет размер изображения подчеркнутым.|  
|[CMFCToolBarImages::UpdateImage](#updateimage)|Обновляет образ пользовательских инструментов из растрового изображения.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarImages::PreMultiplyAlpha](#premultiplyalpha)||  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCToolBarImages::m_bDisableTrueColorAlpha](#m_bdisabletruecoloralpha)|`TRUE`Если отключено truecolor альфа-смешение (32-разрядный цвет).|  
  
## <a name="remarks"></a>Примечания  
 Полный точечный рисунок изображений панели инструментов, которые управляются `CMFCToolbarImages` состоит из одного или нескольких изображений небольшую панель инструментов (кнопки) фиксированный размер.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить `CMFCToolBarImages` объектов с помощью различных методов в `CMFCToolBarImages` класса. В примере показано определение размера изображения панели инструментов, загрузить изображение и задать прозрачный цвет изображения. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#32;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#33;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCToolBarImages`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtoolbarimages.h  
  
##  <a name="adaptcolors"></a>CMFCToolBarImages::AdaptColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AdaptColors(
    COLORREF clrBase,  
    COLORREF clrTone);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clrBase`  
 [in] `clrTone`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addicon"></a>CMFCToolBarImages::AddIcon  
 Добавляет в список изображений панели инструментов значок.  
  
```  
int AddIcon(
    HICON hIcon,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hIcon`  
 Дескриптор значка для добавления.  
  
 [in] `bAlphaBlend`  
 `TRUE`Если этот значок используется с альфа-смешение; в противном случае `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс изображения панели инструментов, который был добавлен, если метод выполнен успешно; в противном случае — значение -1.  
  
##  <a name="addimage"></a>CMFCToolBarImages::AddImage  
 Добавляет точечный рисунок изображений панели инструментов.  
  
```  
int AddImage(
    HBITMAP hbmp,  
    BOOL bSetBitPerPixel=FALSE);

int AddImage(
    const CMFCToolBarImages& imageList,  
    int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hbmp`  
 Дескриптор точечного рисунка для добавления.  
  
 [in] `bSetBitPerPixel`  
 `TRUE`Если `CMFCToolBarImages` объект использует глубина цвета (бит на пиксель) нового изображения. `FALSE` Если `CMFCToolbarImages` сохраняет текущую глубину цвета.  
  
 [in] `imageList`  
 Ссылку на `CMFCToolbarImages` объект, содержащий изображение для добавления.  
  
 [in] `nIndex`  
 Индекс в исходном `CMFCToolbarImages` объекта изображения для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество инструментов изображений, `CMFCToolBarImages` сохраняет после новый точечный рисунок был успешно добавлен; -1, если операция завершилась неудачно.  
  
##  <a name="cleanup"></a>CMFCToolBarImages::CleanUp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall CleanUp();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="clear"></a>CMFCToolBarImages::Clear  
 Освобождает системные ресурсы, [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) выделенного объекта.  
  
```  
void Clear();
```  
  
##  <a name="cmfctoolbarimages"></a>CMFCToolBarImages::CMFCToolBarImages  
 Создает объект `CMFCToolBarImages`.  
  
```  
CMFCToolBarImages();
```  
  
### <a name="remarks"></a>Примечания  
 Создает `CMFCToolBarImages` , инициализирует его механизм визуализации и устанавливает размер изображения к значению по умолчанию 16 x 15 пикселов. Используйте [CMFCToolBarImages::SetImageSize](#setimagesize) для изменения размера изображения до добавления изображений.  
  
##  <a name="copyimagetoclipboard"></a>CMFCToolBarImages::CopyImageToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyImageToClipboard(int iImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iImage`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="copyto"></a>CMFCToolBarImages::CopyTo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyTo(CMFCToolBarImages& imageList);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `imageList`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="createfromimagelist"></a>CMFCToolBarImages::CreateFromImageList  
 Инициализирует изображений панели инструментов из [класса CImageList](../../mfc/reference/cimagelist-class.md) объекта.  
  
```  
BOOL CreateFromImageList(const CImageList& imageList);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `imageList`  
 Список изображений для использования в качестве источника для изображений на панели инструментов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для быстрого инициализации списка изображений инструментов из списка внешних изображений.  
  
##  <a name="createregionfromimage"></a>CMFCToolBarImages::CreateRegionFromImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static HRGN __stdcall CreateRegionFromImage(
    HBITMAP bmp,  
    COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bmp`  
 [in] `clrTransparent`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="deleteimage"></a>CMFCToolBarImages::DeleteImage  
 Удаление определяемых пользователем изображения с указанным индексом из изображений панели инструментов.  
  
```  
BOOL DeleteImage(int iImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iImage`  
 Задает отсчитываемый от нуля индекс образа для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если изображение было удалено успешно. `FALSE` Если недопустимый индекс образа, `CMFCToolbarImages` объект является временным, `CMFCToolbarImages` объект не содержит пользовательских образов, или если некоторые другие произошла ошибка.  
  
##  <a name="draw"></a>CMFCToolBarImages::Draw  
 Рисует изображение одной панели инструментов.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int x,  
    int y,  
    int iImageIndex,  
    BOOL bHilite=FALSE,  
    BOOL bDisabled=FALSE,  
    BOOL bIndeterminate=FALSE,  
    BOOL bShadow=FALSE,  
    BOOL bInactive=FALSE,  
    BYTE alphaSrc=255);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `x`  
 Координата X левой стороны прямоугольника, где изображение для отображения.  
  
 [in] `y`  
 Координаты Y верхнего края прямоугольника, где изображение для отображения.  
  
 [in] `iImageIndex`  
 Отсчитываемый от нуля индекс изображения для отображения.  
  
 [in] `bHilite`  
 `TRUE`Если изображение выделяться; в противном случае `FALSE`.  
  
 [in] `bDisabled`  
 `TRUE`Если изображение для отрисовки на отключенный стиля; в противном случае `FALSE`.  
  
 [in] `bIndeterminate`  
 `TRUE`Если изображение в неопределенном состоянии стиля; в противном случае `FALSE`.  
  
 [in] `bShadow`  
 `TRUE`Если изображение для отрисовки с тенью; в противном случае `FALSE`.  
  
 [in] `bInactive`  
 `TRUE`Если изображение находится в неактивном состоянии стиль; в противном случае `FALSE`.  
  
 [in] `alphaSrc`  
 Значение альфа-канала (прозрачности). Значение 255 означает изображение формируемого непрозрачный. Значение 0 означает изображение рисуется прозрачным. Это значение используется только для 32-разрядных цветных изображений и изображений, которые отображаются стекла стиля Windows Vista.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если указанное изображение отображалось успешно; `FALSE` Если недопустимый индекс образа или возникла другая ошибка.  
  
##  <a name="drawex"></a>CMFCToolBarImages::DrawEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL DrawEx(
    CDC* pDC,  
    CRect rect,  
    int iImageIndex,  
    ImageAlignHorz horzAlign = ImageAlignHorzLeft,  
    ImageAlignVert vertAlign = ImageAlignVertTop,  
    CRect rectSrc = CRect(0,
    0,
    0,
    0),  
    BYTE alphaSrc = 255);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 [in] `rect`  
 [in] `iImageIndex`  
 [in] `horzAlign`  
 [in] `vertAlign`  
 [in] `rectSrc`  
 [in] `0`  
 [in] `0)`  
 [in] `alphaSrc`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enablertl"></a>CMFCToolBarImages::EnableRTL  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall EnableRTL(BOOL bIsRTL = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsRTL`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enddrawimage"></a>CMFCToolBarImages::EndDrawImage  
 Освобождает системные ресурсы, [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage) выделенной после рисования изображения панели инструментов, вызвав [CMFCToolBarImages::Draw](#draw).  
  
```  
void EndDrawImage(CAfxDrawState& ds);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ds`  
 Ссылку на `CAfxDrawState` объекта, который был передан в `PrepareDrawImage` метод.  
  
##  <a name="extracticon"></a>CMFCToolBarImages::ExtractIcon  
 Возвращает значок, который имеет указанное изображение индекс из изображений панели инструментов.  
  
```  
HICON ExtractIcon(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Отсчитываемый от нуля индекс в списке изображений, в котором находится изображение извлекается в виде значка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для извлеченных значок или `NULL` Если `nIndex` выходит за пределы диапазона.  
  
##  <a name="fillditheredrect"></a>CMFCToolBarImages::FillDitheredRect  
 Заполняет прямоугольник с цветами фона панели инструментов.  
  
```  
static void FillDitheredRect(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rect`  
 Координаты прямоугольника для заливки.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для заполнения прямоугольника цветом, — это среднее COLOR_BTNFACE и COLOR_BTNHIGHLIGHT системные цвета. Если в системе используется не более 256 цветов, прямоугольник будет заполняться сглаженных шаблон из этих двух цветов вместо.  
  
##  <a name="getalwayslight"></a>CMFCToolBarImages::GetAlwaysLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetAlwaysLight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcount"></a>CMFCToolBarImages::GetCount  
 Возвращает число изображений в списке изображений панели инструментов.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число изображений в `CMFCToolBarImages` объекта.  
  
##  <a name="getdisabledimagealpha"></a>CMFCToolBarImages::GetDisabledImageAlpha  
 Возвращает значение альфа-канала (прозрачности), которое используется для изображений отключено.  
  
```  
static BYTE GetDisabledImageAlpha();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение альфа-канала.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать [CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha) изменить значение альфа-канала.  
  
##  <a name="getfadedimagealpha"></a>CMFCToolBarImages::GetFadedImageAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BYTE __stdcall GetFadedImageAlpha();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getimagesize"></a>CMFCToolBarImages::GetImageSize  
 Возвращает размер изображений панели инструментов, которые хранятся в памяти (размер источника) или размер изображений, отображаемых на экране (размер) на панели инструментов.  
  
```  
SIZE GetImageSize(BOOL bDest=FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDest`  
 `TRUE`Для получения размера назначения; `FALSE` для получения размера исходного изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `SIZE` структура, которая задает размер изображения в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Размер исходного изображения — размер изображения, которые хранятся в [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) объекта. Можно вызвать [CMFCToolBarImages::SetImageSize](#setimagesize) исходный размер. Значение по умолчанию — 16 x 15 пикселей.  
  
 По умолчанию назначения составляет 0x0. Указать размер целевого при вызове [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage). [CMFCToolBarImages::EndDrawImage](#enddrawimage) метод сбрасывает размер целевого значения по умолчанию.  
  
##  <a name="getimagewell"></a>CMFCToolBarImages::GetImageWell  
 Возвращает дескриптор растровому изображению, которое содержит все изображения панели инструментов.  
  
```  
HBITMAP GetImageWell() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор точечного рисунка, содержащего изображений на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 Панель инструментов изображения хранятся в строке в одном точечном рисунке под названием *резервуар изображений*. Чтобы найти изображение панели инструментов в списке изображений, умножить индекс образа ширину изображений панели инструментов (см. [CMFCToolBarImages::GetImageSize](#getimagesize)) также получить горизонтальное смещение изображения в образе.  
  
##  <a name="getimagewelllight"></a>CMFCToolBarImages::GetImageWellLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HBITMAP GetImageWellLight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getlastimagerect"></a>CMFCToolBarImages::GetLastImageRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetLastImageRect() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getlightpercentage"></a>CMFCToolBarImages::GetLightPercentage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetLightPercentage() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getmapto3dcolors"></a>CMFCToolBarImages::GetMapTo3DColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetMapTo3DColors() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getmask"></a>CMFCToolBarImages::GetMask  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HBITMAP GetMask(int iImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iImage`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getresourceoffset"></a>CMFCToolBarImages::GetResourceOffset  
 Возвращает индекс образа для указанного ресурса.  
  
```  
int GetResourceOffset(UINT uiResId) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiResId`  
 Идентификатор ресурса изображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс изображения, если метод был выполнен успешно; значение -1, если изображение с Идентификатором указанный ресурс не существует.  
  
##  <a name="gettransparentcolor"></a>CMFCToolBarImages::GetTransparentColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
COLORREF GetTransparentColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="grayimages"></a>CMFCToolBarImages::GrayImages  
 Grays изображений панели инструментов выглядела отключено.  
  
```  
BOOL GrayImages(int nGrayImageLuminancePercentage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nGrayImageLuminancePercentage`  
 Процентное значение яркости.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если изображения в коллекции были установлены успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод изменяет изображений панели инструментов, вычисление среднего значения красного, зеленого и синего компонентов каждого пикселя и умножением на `nGrayImageLuminancePercentage` делится на 100. Если `nGrayImageLuminancePercentage` — ноль или отрицательное значение, значение по умолчанию 130 вместо него используется.  
  
> [!NOTE]
>  Если вы хотите отменить изменения, необходимо перезагрузить изображений из источника. Это можно сделать, вызвав [CMFCToolBarImages::Load](#load) или [CMFCToolBarImages::UpdateImage](#updateimage) (только для пользовательских образов), или путем вызова [CMFCToolBarImages::Clear](#clear) и снова добавив изображения путем вызова [CMFCToolBarImages::AddIcon](#addicon) или [CMFCToolBarImages::AddImage](#addimage).  
  
##  <a name="is32bittransparencysupported"></a>CMFCToolBarImages::Is32BitTransparencySupported  
 Указывает, поддерживает альфа-смешение 32-разрядной операционной системы.  
  
```  
static BOOL Is32BitTransparencySupported();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если альфа-смешение цвета 32 бита поддерживается; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте статический метод на этапе выполнения определить, поддерживает ли альфа-смешение 32-разрядной операционной системы. Эта функция поддерживается на [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] и более поздних версиях.  
  
##  <a name="ispremultiplyautocheck"></a>CMFCToolBarImages::IsPreMultiplyAutoCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsPreMultiplyAutoCheck() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isreadonly"></a>CMFCToolBarImages::IsReadOnly  
 Указывает, являются ли изображений панели инструментов только для чтения.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если изображений панели инструментов доступны только для чтения, в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `CMFCToolbarImages` Объект доступен только для чтения при загрузке точечного рисунка с изображениями на панели инструментов из файла только для чтения или точечный рисунок был скопирован с помощью `CMFCToolBarImages::CopyTemp` метод.  
  
##  <a name="isrtl"></a>CMFCToolBarImages::IsRTL  
 Указывает, включена ли поддержка справа налево (RTL).  
  
```  
static BOOL IsRTL();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если включена поддержка справа НАЛЕВО; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Поддержка справа НАЛЕВО используется при локализации приложения для языка, который читается справа налево, например арабский, иврит, фарси и урду.  
  
##  <a name="isuserimageslist"></a>CMFCToolBarImages::IsUserImagesList  
 Указывает, содержит ли этот набор инструментов образы пользовательских образов.  
  
```  
BOOL IsUserImagesList() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `CMFCToolBarImages` объект содержит изображений на пользовательской панели инструментов; в противном случае `FALSE`.  
  
##  <a name="isvalid"></a>CMFCToolBarImages::IsValid  
 Указывает, содержит ли этот набор изображений на панели инструментов значок допустимым панели инструментов.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `CMFCToolBarImages` объект является допустимым; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 `CMFCToolBarImages` Недопустимый объект при его дескриптор точечного рисунка с изображениями на панели инструментов `NULL`.  
  
##  <a name="load"></a>CMFCToolBarImages::Load  
 Загрузка изображений панели инструментов из системных ресурсов или из файла.  
  
```  
BOOL Load(
    UINT uiResID,  
    HINSTANCE hinstRes=NULL,  
    BOOL bAdd=FALSE);

BOOL Load(
    LPCTSTR lpszBmpFileName,   
    DWORD nMaxFileSize = 819200);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiResID`  
 Идентификатор ресурса растрового изображения.  
  
 [in] `hinstRes`  
 Экземпляр DLL-Библиотеки ресурсов.  
  
 [in] `bAdd`  
 `TRUE`Добавление существующего точечного рисунка, загруженное растровое изображение или `FALSE` для замены существующего точечного рисунка.  
  
 [in] `lpszBmpFileName`  
 Путь к файлу диска из для загрузки точечного рисунка.  
  
 [in] `nMaxFileSize`  
 Максимальное число байтов в файле битовой карты; или 0 для загрузки точечного рисунка, независимо от размера файла. Если размер файла превышает этот предел, метод возвращает `FALSE` и не загружает точечный рисунок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если точечный рисунок был загружен успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если файл имеет атрибут только для чтения, список изображений помечен как доступный только для чтения.  
  
##  <a name="loadstr"></a>CMFCToolBarImages::LoadStr  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL LoadStr(
    LPCTSTR lpszResourceName,  
    HINSTANCE hinstRes = NULL,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszResourceName`  
 [in] `hinstRes`  
 [in] `bAdd`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="mapfromsyscolor"></a>CMFCToolBarImages::MapFromSysColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapFromSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 [in] `bUseRGBQUAD`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="mapto3dcolors"></a>CMFCToolBarImages::MapTo3dColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL MapTo3dColors(
    BOOL bUseRGBQUAD = TRUE,  
    COLORREF clrSrc = (COLORREF)-1,  
    COLORREF clrDest = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bUseRGBQUAD`  
 [in] `clrSrc`  
 [in] `clrDest`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="maptosyscolor"></a>CMFCToolBarImages::MapToSysColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapToSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
 [in] `bUseRGBQUAD`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="maptosyscoloralpha"></a>CMFCToolBarImages::MapToSysColorAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapToSysColorAlpha(COLORREF color);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `color`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="mirror"></a>CMFCToolBarImages::Mirror  
 Заменяет их горизонтальное зеркальное отражение изображения панели инструментов.  
  
```  
BOOL Mirror();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если изображения были успешно зеркально; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для поддержки систем письма справа налево.  
  
##  <a name="mirrorbitmap"></a>CMFCToolBarImages::MirrorBitmap  
 Заменяет его горизонтальное зеркальное изображение точечного рисунка.  
  
```  
static BOOL MirrorBitmap(
    HBITMAP& hbmp,  
    int cxImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `hbmp`  
 Дескриптор точечного рисунка для зеркального отображения.  
  
 [in] `cxImage`  
 Ширина изображения в пикселях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если образ был успешно зеркально; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для поддержки систем письма справа налево.  
  
##  <a name="mirrorbitmapvert"></a>CMFCToolBarImages::MirrorBitmapVert  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall MirrorBitmapVert(
    HBITMAP& hbmp,  
    int cyImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hbmp`  
 [in] `cyImage`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="mirrorvert"></a>CMFCToolBarImages::MirrorVert  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL MirrorVert();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onsyscolorchange"></a>CMFCToolBarImages::OnSysColorChange  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="premultiplyalpha"></a>CMFCToolBarImages::PreMultiplyAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall PreMultiplyAlpha(
    HBITMAP hbmp,  
    BOOL bAutoCheckPremlt);

BOOL PreMultiplyAlpha(HBITMAP hbmp);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hbmp`  
 [in] `bAutoCheckPremlt`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_bdisabletruecoloralpha"></a>CMFCToolBarImages::m_bDisableTrueColorAlpha  
 `TRUE`Если отключено truecolor альфа-смешение (32-разрядный цвет).  
  
```  
static BOOL m_bDisableTrueColorAlpha;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этой переменной-члена `FALSE` для включения truecolor альфа смешения для изображений на панели инструментов.  
  
 Значение по умолчанию — `TRUE` для обеспечения обратной совместимости.  
  
##  <a name="preparedrawimage"></a>CMFCToolBarImages::PrepareDrawImage  
 Распределяет ресурсы, которые необходимо нарисовать изображение с панели инструментов с указанным размером.  
  
```  
BOOL PrepareDrawImage(
    CAfxDrawState& ds,  
    CSize sizeImageDest=CSize(0,
    0)  
    BOOL bFadeInactive=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ds`  
 Ссылку на `CAfxDrawState` структура, которая хранит выделенные ресурсы между этапами подготовки к просмотру изображений.  
  
 [in] `sizeImageDest`  
 Указывает размер конечного изображения.  
  
 [in] `bFadeInactive`  
 `TRUE`Если вы хотите неактивные проявление изображения для отрисовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если ресурсы, необходимые для рисования изображения панели инструментов были выделены успешно, в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 После вызова этого метода можно вызвать [CMFCToolBarImages::Draw](#draw) любое число раз. После завершения рисования, необходимо вызвать [CMFCToolBarImages::EndDrawImage](#enddrawimage) для освобождения ресурсов, выделенных в `PrepareDrawImage`.  
  
##  <a name="save"></a>CMFCToolBarImages::Save  
 Сохраняет в файле изображений панели инструментов, если этот набор инструментов изображения содержит пользовательские изображения.  
  
```  
BOOL Save(LPCTSTR lpszBmpFileName=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszBmpFileName`  
 Путь к файлу диска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель инструментов изображений были сохранены успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для хранения определенных пользователем изображений в файл на диске. Если `lpszBmpFileName` — `NULL`, метод сохраняет точечный рисунок в файл, из которого был загружен точечного рисунка по [CMFCToolBarImages::Load](#load) метод.  
  
##  <a name="setalwayslight"></a>CMFCToolBarImages::SetAlwaysLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetAlwaysLight(BOOL bAlwaysLight = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAlwaysLight`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdisabledimagealpha"></a>CMFCToolBarImages::SetDisabledImageAlpha  
 Задает значение альфа-канала (прозрачности), которое используется для изображений отключено.  
  
```  
static void SetDisabledImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nValue`  
 Новое значение альфа-канала.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы задать настраиваемое значение альфа-канала для изображений отключено. Значение по умолчанию — 127, вследствие чего полупрозрачных изображений отключенной кнопки. Если задано значение 0, отключенные изображения будут полностью прозрачным. Если задано значение 255, отключенные изображения будут полностью непрозрачным.  
  
##  <a name="setfadedimagealpha"></a>CMFCToolBarImages::SetFadedImageAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall SetFadedImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nValue`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setimagesize"></a>CMFCToolBarImages::SetImageSize  
 Задает размер каждого изображения панели инструментов (размер источника).  
  
```  
void SetImageSize(
    SIZE sizeImage,  
    BOOL bUpdateCount=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `sizeImage`  
 Новый размер изображений на панели инструментов.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию размер изображения панели инструментов — 16 x 15 пикселов. Этот метод вызывается в том случае, если вы хотите использовать образы инструментов другого размера.  
  
##  <a name="setlightpercentage"></a>CMFCToolBarImages::SetLightPercentage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetLightPercentage(int nValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nValue`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setmapto3dcolors"></a>CMFCToolBarImages::SetMapTo3DColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetMapTo3DColors(BOOL bMapTo3DColors);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMapTo3DColors`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpremultiplyautocheck"></a>CMFCToolBarImages::SetPreMultiplyAutoCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPreMultiplyAutoCheck(BOOL bAuto = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAuto`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setsingleimage"></a>CMFCToolBarImages::SetSingleImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetSingleImage();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="settransparentcolor"></a>CMFCToolBarImages::SetTransparentColor  
 Задает прозрачный цвет изображения панели инструментов.  
  
```  
COLORREF SetTransparentColor(COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clrTransparent`  
 RGB-значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие прозрачный цвет.  
  
### <a name="remarks"></a>Примечания  
 При вызове разработчика или используемой инфраструктуры [CMFCToolBarImages::Draw](#draw), метод не пиксель любой, соответствующий цвет, определенный параметром `clrTransparent`.  
  
##  <a name="updateimage"></a>CMFCToolBarImages::UpdateImage  
 Обновляет образ пользовательских инструментов из растрового изображения.  
  
```  
BOOL UpdateImage(
    int iImage,  
    HBITMAP hbmp);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iImage`  
 Отсчитываемый от нуля индекс образа для обновления.  
  
 [in] `hbmp`  
 Дескриптор точечного рисунка из обновляемого образа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если образ был успешно обновлен; `FALSE` Если список изображений не определяемых пользователем или временной.  
  
##  <a name="convertto32bits"></a>CMFCToolBarImages::ConvertTo32Bits  
 Преобразует подчеркнуть точечные рисунки в 32 bpp изображения.  
  
```  
BOOL ConvertTo32Bits(COLORREF clrTransparent = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Параметры  
 `clrTransparent`  
 Указывает прозрачный цвет подчеркнутым точечных рисунков.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getbitsperpixel"></a>CMFCToolBarImages::GetBitsPerPixel  
 Возвращает текущее разрешение изображения подчеркнутым.  
  
```  
int GetBitsPerPixel() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число, представляющее текущее разрешение подчеркнутым изображений в бит на пиксель (bpp).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getscale"></a>CMFCToolBarImages::GetScale  
 Возвращает текущий масштаб подчеркнутым изображений.  
  
```  
double GetScale() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, представляющее текущий масштаб.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isscaled"></a>CMFCToolBarImages::IsScaled  
 Указывает, масштабируется подчеркнутым изображения или нет.  
  
```  
BOOL IsScaled () const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если подчеркнутый изображения масштабируются; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="smoothresize"></a>CMFCToolBarImages::SmoothResize  
 Плавно изменяет размер изображения подчеркнутым.  
  
```  
BOOL SmoothResize(double dblImageScale);
```  
  
### <a name="parameters"></a>Параметры  
 `dblImageScale`  
 Коэффициент масштабирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если изменения размера выполняется успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)   
 [Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

