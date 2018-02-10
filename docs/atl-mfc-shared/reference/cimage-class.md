---
title: "CImage-класс | Документы Microsoft"
ms.custom: 
ms.date: 02/01/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d5478a258c55996fe4073ffc1ab616b2b71386c
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="cimage-class"></a>CImage-класс
`CImage`предоставляет улучшенную поддержку растровых изображений, включая возможность загрузки и сохранения изображений в формате JPEG, GIF, BMP и Portable Network Graphics (PNG).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CImage
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CImage::CImage](#cimage)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CImage::AlphaBlend](#alphablend)|Отображает растровых изображений, имеющих пикселей прозрачным или полупрозрачным.|  
|[CImage::Attach](#attach)|Присоединяет `HBITMAP` для `CImage` объекта. Можно использовать с растровые изображения не DIB раздела или растровые изображения DIB раздела.|  
|[CImage::BitBlt](#bitblt)|Копирует растровое изображение из контекста исходного устройства это текущий контекст устройства.|  
|[CImage::Create](#create)|Создает раздел точечный рисунок DIB и привязывает его к ранее созданные `CImage` объекта.|  
|[CImage::CreateEx](#createex)|Создает раздел DIB точечный рисунок (с добавлением дополнительных параметров) и привязывает его к ранее созданные `CImage` объекта.|  
|[CImage::Destroy](#destroy)|Отсоединяет точечный рисунок из `CImage` объекта и уничтожает растрового изображения.|  
|[CImage::Detach](#detach)|Отсоединяет точечный рисунок из `CImage` объекта.|  
|[CImage::Draw](#draw)|Копирует точечный рисунок из исходного прямоугольника в прямоугольник назначения. **Рисование** растягивает или сжимает растрового изображения в соответствии с размерами прямоугольника назначения, при необходимости, а также обрабатывает альфа-смешение и прозрачные цвета.|  
|[CImage::GetBits](#getbits)|Извлекает указатель на фактическое пикселов растрового изображения.|  
|[CImage::GetBPP](#getbpp)|Возвращает значение бита на пиксель.|  
|[CImage::GetColorTable](#getcolortable)|Извлекает красный, зеленый, синий (RGB) цветовых значений из диапазона записей в таблице цветов.|  
|[CImage::GetDC](#getdc)|Извлекает контекст устройства, в которую установлен текущую битовую карту.|  
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Находит форматы доступных изображений и их описания.|  
|[CImage::GetHeight](#getheight)|Получает высоту текущего изображения в пикселях.|  
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Находит форматы доступных изображений и их описания.|  
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Получает максимальное количество записей в таблице цветов.|  
|[CImage::GetPitch](#getpitch)|Получает высоту текущего изображения, в байтах.|  
|[CImage::GetPixel](#getpixel)|Получает цвет пикселя, определяемый *x* и *y*.|  
|[CImage::GetPixelAddress](#getpixeladdress)|Извлекает адрес произвольной точки.|  
|[CImage::GetTransparentColor](#gettransparentcolor)|Возвращает позицию прозрачный цвет в таблице цветов.|  
|[CImage::GetWidth](#getwidth)|Получает ширину текущего изображения в пикселях.|  
|[CImage::IsDIBSection](#isdibsection)|Определяет, является ли вложенный растрового изображения DIB раздела.|  
|[CImage::IsIndexed](#isindexed)|Указывает, что цвета точечного рисунка, сопоставляются с индексированную палитру.|  
|[CImage::IsNull](#isnull)|Указывает, если исходный точечный рисунок в данный момент загружен.|  
|[CImage::IsTransparencySupported](#istransparencysupported)|Указывает, поддерживает ли приложение прозрачными точечными рисунками.|  
|[CImage::Load](#load)|Загружает изображение из указанного файла.|  
|[CImage::LoadFromResource](#loadfromresource)|Загружает изображение из указанного ресурса.|  
|[CImage::MaskBlt](#maskblt)|Объединяет данные о цвете для исходного и конечного точечных рисунков, с помощью указанной маске и выполнению растровую операцию.|  
|[CImage::PlgBlt](#plgblt)|Выполняет перемещение набора битов с прямоугольник в контексте устройства источника параллелограмма в контексте устройства назначения.|  
|[CImage::ReleaseDC](#releasedc)|Освобождает контекст устройства, которые были получены с [CImage::GetDC](#getdc).|  
|[CImage::ReleaseGDIPlus](#releasegdiplus)|Освобождает ресурсы, используемые в GDI +. Необходимо вызвать для освобождения ресурсов, созданные глобальный `CImage` объекта.|  
|[CImage::Save](#save)|Сохраняет изображение в указанный тип. **Сохранить** нельзя указать параметры изображения.|  
|[CImage::SetColorTable](#setcolortable)|Задает RGB красный, зеленый, синий) значения в диапазоне от записей в таблице цвет раздела DIB цветов.|  
|[CImage::SetPixel](#setpixel)|Задает пикселя по указанным координатам на указанный цвет.|  
|[CImage::SetPixelIndexed](#setpixelindexed)|Задает пикселя по указанным координатам цвет палитры по указанному индексу.|  
|[CImage::SetPixelRGB](#setpixelrgb)|Задает пикселя по указанным координатам значение указанного красный, зеленый, синего (RGB).|  
|[CImage::SetTransparentColor](#settransparentcolor)|Задает индекс цвет, который будет рассматриваться как прозрачный. Только один цвет в палитре может быть прозрачным.|  
|[CImage::StretchBlt](#stretchblt)|Копирует точечный рисунок из исходного прямоугольника в прямоугольник назначения, растягивая или сжимая точечный рисунок в соответствии с размерами прямоугольника назначения, при необходимости.|  
|[CImage::TransparentBlt](#transparentblt)|Копирует растровое изображение со прозрачный цвет из контекста исходного устройства это текущий контекст устройства.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[HBITMAP CImage::operator](#operator_hbitmap)|Возвращает дескриптор Windows, присоединенного к `CImage` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CImage`принимает точечные рисунки, — это либо участки аппаратно независимый точечный рисунок (DIB) или нет; Тем не менее, можно использовать [создать](#create) или [CImage::Load](#load) с только разделы DIB. Можно присоединить растровое изображение не DIB раздел для `CImage` с помощью [присоединение](#attach), но их нельзя использовать следующие `CImage` методы, которые поддерживают только растровые изображения DIB раздела:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
 Чтобы определить, является ли вложенный растрового изображения DIB раздел, вызовите [IsDibSection](#isdibsection)**.**  
  
> [!NOTE]
> **Примечание** в Visual Studio .NET 2003, этот класс отслеживает количество число `CImage` объекты, созданные. Каждый раз, когда счетчик становится равным 0, функция **GdiplusShutdown** вызывается автоматически для освобождения ресурсов, используемых в GDI +. Это гарантирует, что любой `CImage` уничтожения объектов, созданных DLL прямо или косвенно всегда правильно и что **GdiplusShutdown** не вызывается из `DllMain`.  
  
> [!NOTE]
>  С помощью глобального `CImage` объектов в библиотеке DLL не рекомендуется. Если необходимо использовать глобальный `CImage` объектов в библиотеке DLL, вызов [CImage::ReleaseGDIPlus](#releasegdiplus) явно освободить ресурсы, используемые в GDI +.  
  
 `CImage`не могут быть выбраны в новую [CDC](../../mfc/reference/cdc-class.md). `CImage`создает свой собственный **HDC** для изображения. Поскольку `HBITMAP` может быть выбран только в одну **HDC** одновременно, `HBITMAP` связанных с `CImage` не могут быть выбраны в другой **HDC**. Если вам требуется `CDC`, получить **HDC** из `CImage` и присвойте ему [CDC::FromHandle] (.. /.. /MFC/Reference/CDC-Class.md#cdc__fromhandle.  
  
## <a name="example"></a>Пример  
```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```  
  
 При использовании `CImage` в проекте MFC Обратите внимание на то, какие функции-члены в проекте ожидается, что указатель [CBitmap](../../mfc/reference/cbitmap-class.md) объекта. Если вы хотите использовать `CImage` с помощью функции как [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), используйте [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), передать его на `CImage` `HBITMAP`и использовать возвращаемое `CBitmap*`.  

  
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

  
 Через `CImage`, у вас есть право число битов DIB раздела. Можно использовать `CImage` объекта ранее использовался раздел Win32 HBITMAP или DIB.  
  
 Можно использовать `CImage` из MFC и ATL.  
  
> [!NOTE]
>  При создании проекта с помощью `CImage`, необходимо определить `CString` перед включением `atlimage.h`. Если проект использует ATL без использования MFC, включают `atlstr.h` перед включением `atlimage.h`. Если проект использует MFC (или если это проект ATL с поддержкой MFC), включают `afxstr.h` перед включением `atlimage.h`.  
>   
>  Аналогичным образом, необходимо включить `atlimage.h` перед включением `atlimpl.cpp`. Для этого просто включить `atlimage.h` в вашей `stdafx.h`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlimage.h  
  
##  <a name="alphablend"></a>  CImage::AlphaBlend  
 Отображает растровых изображений, имеющих пикселей прозрачным или полупрозрачным.  
  
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
 `hDestDC`  
 Дескриптор контекста устройства назначения.  
  
 `xDest`  
 Координата x, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `yDest`  
 Координата y, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 *bSrcAlpha*  
 Значение альфа-прозрачность для использования на всей исходный точечный рисунок. Значение по умолчанию 0xff (255) предполагается, что образ является непрозрачным, и вы хотите использовать только альфа-значения каждой точки.  
  
 `bBlendOp`  
 Функция альфа смешения источника и точечным рисунком назначения, глобальное значение альфа-канала для применения к весь исходный точечный рисунок и сведения о формате для исходного точечного рисунка. Исходный и целевой функции blend ограничены **AC_SRC_OVER**.  
  
 `pointDest`  
 Ссылку на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структура, определяющая верхнего левого угла прямоугольника назначения в логических единицах.  
  
 `nDestWidth`  
 Ширина в логических единицах прямоугольника назначения.  
  
 `nDestHeight`  
 Высота в логических единицах прямоугольника назначения.  
  
 `xSrc`  
 Логический Координата x верхнего левого угла исходного прямоугольника.  
  
 `ySrc`  
 Логический Координата y верхнего левого угла исходного прямоугольника.  
  
 `nSrcWidth`  
 Ширина в логических единицах исходного прямоугольника.  
  
 `nSrcHeight`  
 Высота в логических единицах исходного прямоугольника.  
  
 `rectDest`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, определение назначения.  
  
 `rectSrc`  
 Ссылку на `RECT` структуры, определение источника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Растровые изображения альфа смешение поддерживает смешение цвета на основе каждого пикселя.  
  
 Когда `bBlendOp` задано значение по умолчанию **AC_SRC_OVER**, помещении исходный точечный рисунок в точечный рисунок назначения на основе значений альфа-пикселей источника.  

##  <a name="attach"></a>  CImage::Attach  
 Присоединяет `hBitmap` для `CImage` объекта.  
  
```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hBitmap`  
 Дескриптор `HBITMAP`.  
  
 *eOrientation*  
 Задает ориентацию растрового изображения. Ниже указаны доступные значения.  
  
- **DIBOR_DEFAULT** ориентацию точечного рисунка определяется операционной системой. Однако это не всегда может получить нужные результаты во всех операционных системах. Дополнительные сведения об этом см. в следующей статье базы знаний ( **Q186586**): PRB: GetObject() всегда возвращает положительное высоту для DIB разделов.  
  
- **DIBOR_BOTTOMUP** строки точечного рисунка, представлены в обратном порядке. В результате [CImage::GetBits](#getbits) для возврата указателя в конец буфера растрового изображения и [CImage::GetPitch](#getpitch) для возврата отрицательное число.  
  
- **DIBOR_TOPDOWN** строки точечного рисунка, находятся в порядке сверху вниз. В результате [CImage::GetBits](#getbits) для возврата указателя до получения первого байта буфера растрового изображения и [CImage::GetPitch](#getpitch) для возврата положительное число.  
  
### <a name="remarks"></a>Примечания  
 Растровое изображение может быть растровое изображение не DIB раздел или раздел DIB растрового изображения. В разделе [IsDIBSection](#isdibsection) список методов, которые можно использовать только с DIB статьи растровые изображения.  
  
##  <a name="bitblt"></a>  CImage::BitBlt  
 Копирует растровое изображение из контекста исходного устройства это текущий контекст устройства.  
  
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
 `hDestDC`  
 Назначение **HDC**.  
  
 `xDest`  
 Логический Координата x верхнего левого угла прямоугольника назначения.  
  
 `yDest`  
 Логический Координата y верхнего левого угла прямоугольника назначения.  
  
 `dwROP`  
 Растровые выполняемой операции. Коды растровых операций определяют, как объединяются в битах источника, назначения и шаблон (как определено выбранной кисти) назначения. В разделе [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) в Windows SDK список другие коды растровых операций и их описания.  
  
 `pointDest`  
 Объект [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру указывая верхнего левого угла прямоугольника назначения.  
  
 `nDestWidth`  
 Ширина в логических единицах прямоугольника назначения.  
  
 `nDestHeight`  
 Высота в логических единицах прямоугольника назначения.  
  
 `xSrc`  
 Логический Координата x верхнего левого угла исходного прямоугольника.  
  
 `ySrc`  
 Логический Координата y верхнего левого угла исходного прямоугольника.  
  
 `rectDest`  
 Объект [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру указывая прямоугольника назначения.  
  
 `pointSrc`  
 Объект **ТОЧКИ** структуры, позволяющее определить, в верхнем левом углу исходного прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) в Windows SDK.  
  
##  <a name="cimage"></a>  CImage::CImage  
 Создает объект `CImage`.  
  
```
CImage() throw();
```  
  
### <a name="remarks"></a>Примечания  
 После создания объекта вызовите [создать](#create), [нагрузки](#load), [LoadFromResource](#loadfromresource), или [присоединение](#attach) для прикрепления к объекту растрового изображения.  
  
 **Примечание** в Visual Studio этот класс отслеживает количество число `CImage` объекты, созданные. Каждый раз, когда счетчик становится равным 0, функция **GdiplusShutdown** вызывается автоматически для освобождения ресурсов, используемых в GDI +. Это гарантирует, что любой `CImage` уничтожения объектов, созданных DLL прямо или косвенно всегда правильно и что **GdiplusShutdown** не вызывается из функции DllMain.  
  
 С помощью глобального `CImage` объектов в библиотеке DLL не рекомендуется. Если необходимо использовать глобальный `CImage` объектов в библиотеке DLL, вызов [CImage::ReleaseGDIPlus](#releasegdiplus) явно освободить ресурсы, используемые в GDI +.  
  
##  <a name="create"></a>  CImage::Create  
 Создает `CImage` растрового изображения и присоединить ее к ранее созданные `CImage` объекта.  
  
```
BOOL Create(
 int nWidth,
 int nHeight,
 int nBPP,
 DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nWidth`  
 Ширина `CImage` растрового изображения в пикселях.  
  
 `nHeight`  
 Высота `CImage` растрового изображения в пикселях. Если `nHeight` положительное, растрового изображения является DIB сверху вниз и его источником является нижнего левого угла. Если `nHeight` имеет отрицательное значение, растрового изображения — DIB сверху вниз, которая его происхождения верхнего левого угла.  
  
 `nBPP`  
 Количество бит на пиксель в битовой карте. Обычно 4, 8, 16, 24 или 32. Может иметь значение 1 для монохромный растровые изображения или маски.  
  
 `dwFlags`  
 Указывает, если объект точечный рисунок имеет альфа-канала. Может представлять собой сочетание нуля или более из следующих значений:  
  
- **createAlphaChannel** можно использовать, только если `nBPP` — 32, и `eCompression` — **BI_RGB**. Если указано, созданный образ имеет значение альфа-прозрачности каждого пикселя, хранящихся в четвертый байт каждый пиксель (не используется в 32-разрядного образа отличные от буквенно-). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).  
  
> [!NOTE]
>  В вызовах [CImage::Draw](#draw), изображений с альфа-канал выполняется автоматически альфа-смешение в место назначения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="createex"></a>  CImage::CreateEx  
 Создает `CImage` растрового изображения и присоединить ее к ранее созданные `CImage` объекта.  
  
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
 `nWidth`  
 Ширина `CImage` растрового изображения в пикселях.  
  
 `nHeight`  
 Высота `CImage` растрового изображения в пикселях. Если `nHeight` положительное, растрового изображения является DIB сверху вниз и его источником является нижнего левого угла. Если `nHeight` имеет отрицательное значение, растрового изображения — DIB сверху вниз, которая его происхождения верхнего левого угла.  
  
 `nBPP`  
 Количество бит на пиксель в битовой карте. Обычно 4, 8, 16, 24 или 32. Может иметь значение 1 для монохромный растровые изображения или маски.  
  
 `eCompression`  
 Указывает тип сжатия для сжатых растровое изображение сверху вниз (не могут быть сжаты изображения DIB сверху вниз). Может принимать одно из следующих значений:  
  
- **BI_RGB** формат без сжатия. Указание этого значения при вызове `CImage::CreateEx` эквивалентно вызову метода `CImage::Create`.  
  
- **BI_BITFIELDS** формат без сжатия, а таблица цветов состоит из трех `DWORD` цвет маски, указывающие красный, зеленый и синий компоненты, соответственно, каждой точки. Это допустимо, при использовании с точечными рисунками 16 - и 32-бит.  
  
 *pdwBitfields*  
 Используется, только если `eCompression` равно **BI_BITFIELDS**, в противном случае он должен быть **NULL**. Указатель на массив из трех `DWORD` битовой маски, указав, какие биты каждой точки используются для красного, зеленого и синего компонентов цвета соответственно. Сведения об ограничениях для битовые поля в разделе [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) в Windows SDK.  
  
 `dwFlags`  
 Указывает, если объект точечный рисунок имеет альфа-канала. Может представлять собой сочетание нуля или более из следующих значений:  
  
- **createAlphaChannel** можно использовать, только если `nBPP` — 32, и `eCompression` — **BI_RGB**. Если указано, созданный образ имеет значение альфа-прозрачности каждого пикселя, хранящихся в четвертый байт каждый пиксель (не используется в 32-разрядного образа отличные от буквенно-). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).  
  
    > [!NOTE]
    >  В вызовах [CImage::Draw](#draw), изображений с альфа-канал выполняется автоматически альфа-смешение в место назначения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** в случае успешного выполнения. В противном случае **FALSE**.  
  
### <a name="example"></a>Пример  
 В следующем примере создается 100 x 100 пикселов растрового изображения, с помощью 16 бит для кодирования каждого пикселя. В необходимом 16-разрядное биты 0-3 кодирования красного компонента, бит 4-7 кодирования зеленый и 8 11 бит кодируют синий. Оставшиеся биты 4 не используются.  

```cpp  
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```


##  <a name="destroy"></a>  CImage::Destroy  
 Отсоединяет точечный рисунок из `CImage` объекта и уничтожает растрового изображения.  
  
```
void Destroy() throw();
```  
  
##  <a name="detach"></a>  CImage::Detach  
 Отсоединяет точечный рисунок из `CImage` объекта.  
  
```
HBITMAP Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор к растровому изображению отсоединении или **NULL** Если подключен не растрового изображения.  
  
##  <a name="draw"></a>  CImage::Draw  
 Копирует растровое изображение из контекста исходного устройства текущий контекст устройства.  
  
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
 `hDestDC`  
 Дескриптор контекста устройства назначения.  
  
 `xDest`  
 Координата x, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `yDest`  
 Координата y, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `nDestWidth`  
 Ширина в логических единицах прямоугольника назначения.  
  
 `nDestHeight`  
 Высота в логических единицах прямоугольника назначения.  
  
 `xSrc`  
 Координата x, в логических единицах верхнего левого угла исходного прямоугольника.  
  
 `ySrc`  
 Координата y, в логических единицах верхнего левого угла исходного прямоугольника.  
  
 `nSrcWidth`  
 Ширина в логических единицах исходного прямоугольника.  
  
 `nSrcHeight`  
 Высота в логических единицах исходного прямоугольника.  
  
 `rectDest`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, определение назначения.  
  
 `rectSrc`  
 Ссылку на `RECT` структуры, определение источника.  
  
 `pointDest`  
 Ссылку на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структура, определяющая верхнего левого угла прямоугольника назначения в логических единицах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **Рисование** выполняет те же функции, как [StretchBlt](#stretchblt), если изображение не содержит прозрачный цвет или альфа-канала. В этом случае **нарисовать** выполняет те же функции, либо как [TransparentBlt](#transparentblt) или [AlphaBlend](#alphablend) при необходимости.  
  
 Для версий **нарисовать** исходного прямоугольника, в которых не указан, по умолчанию — всего исходного изображения. Для версии **рисовать** , для целевого прямоугольника размер не задан, размер образа источника, значение по умолчанию и без растяжения или возникает сжатие.  
  
##  <a name="getbits"></a>  CImage::GetBits  
 Извлекает указатель на фактическое битовых значений произвольной точки в точечном рисунке.  
  
```
void* GetBits() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер растрового изображения. Если растровое изображение DIB снизу вверх, указывают указатели вблизи конца буфера. Если растровое изображение DIB сверху вниз, указатель указывает на первый байт буфера.  
  
### <a name="remarks"></a>Примечания  
 Используя этот указатель, а также значение, возвращаемое [GetPitch](#getpitch), можно найти и изменить отдельные точки изображения.  
  
> [!NOTE]
>  Этот метод поддерживает только DIB раздел точечных рисунков; Следовательно, доступ к пикселов `CImage` объекта так же, как пикселей DIB раздела. Возвращенный указатель указывает на пиксель в расположении (0, 0).  
  
##  <a name="getbpp"></a>  CImage::GetBPP  
 Возвращает значение бита на пиксель.  
  
```
int GetBPP() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число битов на пиксель.  
  
### <a name="remarks"></a>Примечания  
 Это значение определяет количество битов, определяющих каждого пикселя и максимальное число цветов в рисунке.  
  
 Бит на пиксель, обычно является 1, 4, 8, 16, 24 или 32. В разделе **biBitCount** членом [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) в Windows SDK, Дополнительные сведения об этом значении.  
  
##  <a name="getcolortable"></a>  CImage::GetColorTable  
 Извлекает красный, зеленый, синий цветовых значений (RGB) из диапазона записей в палитре DIB раздела.  
  
```
void GetColorTable(UINT iFirstColor,
 UINT nColors,
 RGBQUAD* prgbColors) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `iFirstColor`  
 Таблица цветовой индекс первой операции для получения.  
  
 `nColors`  
 Количество записей таблицы цвет для извлечения.  
  
 `prgbColors`  
 Указатель на массив [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) структуры для получения цвет таблицы записей.  
  
##  <a name="getdc"></a>  CImage::GetDC  
 Извлекает контекст устройства, который в настоящее время имеет образ, выбранный в него.  
  
```
HDC GetDC() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для контекста устройства.  
  
### <a name="remarks"></a>Примечания  
 Для каждого вызова `GetDC`, необходимо иметь в последующем вызове [ReleaseDC](#releasedc).  
  
##  <a name="getexporterfilterstring"></a>  CImage::GetExporterFilterString  
 Поиск доступных форматов изображения для сохранения изображений.  
  
```
static HRESULT GetExporterFilterString(CSimpleString& strExporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultSave,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>Параметры  
 *strExporters*  
 Ссылку на **CSimpleString** объекта. В разделе **примечания** для получения дополнительной информации.  
  
 `aguidFileTypes`  
 Массив идентификаторов GUID, при этом каждый элемент, соответствующий одному из типов файлов в строке. В примере в `pszAllFilesDescription` ниже `aguidFileTypes`[0] является `GUID_NULL` , а остальные значения массива — форматов файлов изображений, поддерживаемых текущей операционной системы.  
  
> [!NOTE]
>  Полный список констант см. в разделе **константы формат файла изображения** в Windows SDK.  
  
 `pszAllFilesDescription`  
 Если этот параметр не является **NULL**, строка будет иметь один дополнительный фильтр в начале списка. Этот фильтр будет иметь значение текущей `pszAllFilesDescription` ее описание и принимает файлы из любого расширения, поддерживаемых другими программа экспорта в списке.  
  
 Пример:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Набор битовые флаги, определяющие, какие типы файлов, чтобы исключить из списка. Ниже приведены допустимые флаги.  
  
- **excludeGIF** = 0x01 GIF исключает файлы.  
  
- **excludeBMP** = 0x02 файлы исключает BMP (растрового изображения Windows).  
  
- **excludeEMF** = 0x04 исключает EMF (Enhanced Metafile)-файлы.  
  
- **excludeWMF** = 0x08 файлы исключает WMF (метафайл Windows).  
  
- **excludeJPEG** = файлы JPEG исключает 0x10.  
  
- **excludePNG** = файлы PNG исключает 0x20.  
  
- **excludeTIFF** = 0x40 исключает TIFF файлы.  
  
- **excludeIcon** = файлы 0x80 исключает ICO (значок Windows).  
  
- **excludeOther** = 0x80000000 исключает любые другие типы файлов, не перечисленные выше.  
  
- **excludeDefaultLoad** = 0 для загрузки всех файлов, типы должны быть включены по умолчанию  
  
- **excludeDefaultSave** = **excludeIcon &#124; excludeEMF &#124; excludeWMF** для сохранения, эти файлы были исключены по умолчанию, поскольку они обычно имеют особые требования.  
  
 `chSeparator`  
 Разделитель, используемый между форматы изображений. В разделе **примечания** для получения дополнительной информации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
### <a name="remarks"></a>Примечания  
 Результирующая строка формата можно передать в MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) форматы объекта для предоставления расширений имен файлов изображений, доступных в диалоговое окно «Сохранить как».  
  
 Параметр *strExporter* имеет следующий формат:  
  
 файл description0 &#124; \*.ext0 &#124; filedescription1 &#124; \*.ext1 &#124;... описание файла  *n* &#124;\*. ext  *n* &#124; &#124;  
  
 где "&#124;" указан разделитель `chSeparator`. Пример:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Разделитель по умолчанию "&#124;", если передать эту строку с MFC `CFileDialog` объекта. Используйте null разделитель '\0', если передать эту строку на общее сохранения файла диалоговое окно.  
  
##  <a name="getheight"></a>  CImage::GetHeight  
 Получает высоту в пикселях.  
  
```
int GetHeight() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях.  
  
##  <a name="getimporterfilterstring"></a>  CImage::GetImporterFilterString  
 Находит форматы изображений, доступные для загрузки изображений.  
  
```
static HRESULT GetImporterFilterString(CSimpleString& strImporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultLoad,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>Параметры  
 *strImporters*  
 Ссылку на **CSimpleString** объекта. В разделе **примечания** для получения дополнительной информации.  
  
 `aguidFileTypes`  
 Массив идентификаторов GUID, при этом каждый элемент, соответствующий одному из типов файлов в строке. В примере в `pszAllFilesDescription` ниже `aguidFileTypes`[0] имеет `GUID_NULL` массивом остальные значения — форматов файлов изображений, поддерживаемых текущей операционной системы.  
  
> [!NOTE]
>  Полный список констант см. в разделе **константы формат файла изображения** в Windows SDK.  
  
 `pszAllFilesDescription`  
 Если этот параметр не является **NULL**, строка будет иметь один дополнительный фильтр в начале списка. Этот фильтр будет иметь значение текущей `pszAllFilesDescription` ее описание и принимает файлы из любого расширения, поддерживаемых другими программа экспорта в списке.  
  
 Пример:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Набор битовые флаги, определяющие, какие типы файлов, чтобы исключить из списка. Ниже приведены допустимые флаги.  
  
- **excludeGIF** = 0x01 GIF исключает файлы.  
  
- **excludeBMP** = 0x02 файлы исключает BMP (растрового изображения Windows).  
  
- **excludeEMF** = 0x04 исключает EMF (Enhanced Metafile)-файлы.  
  
- **excludeWMF** = 0x08 файлы исключает WMF (метафайл Windows).  
  
- **excludeJPEG** = файлы JPEG исключает 0x10.  
  
- **excludePNG** = файлы PNG исключает 0x20.  
  
- **excludeTIFF** = 0x40 исключает TIFF файлы.  
  
- **excludeIcon** = файлы 0x80 исключает ICO (значок Windows).  
  
- **excludeOther** = 0x80000000 исключает любые другие типы файлов, не перечисленные выше.  
  
- **excludeDefaultLoad** = 0 для загрузки всех файлов, типы должны быть включены по умолчанию  
  
- **excludeDefaultSave** = **excludeIcon &#124; excludeEMF &#124; excludeWMF** для сохранения, эти файлы были исключены по умолчанию, поскольку они обычно имеют особые требования.  
  
 `chSeparator`  
 Разделитель, используемый между форматы изображений. В разделе **примечания** для получения дополнительной информации.  
  
### <a name="remarks"></a>Примечания  
 Результирующая строка формата можно передать в MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) форматы объекта для предоставления расширений имен файлов изображений, доступных в **Открытие файла** диалоговое окно.  
  
 Параметр *strImporter* имеет следующий формат:  
  
 файл description0 &#124; \*.ext0 &#124; filedescription1 &#124; \*.ext1 &#124;... описание файла  *n* &#124;\*. ext  *n* &#124; &#124;  
  
 где "&#124;" указан разделитель `chSeparator`. Пример:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Разделитель по умолчанию "&#124;", если передать эту строку с MFC `CFileDialog` объекта. Используйте null разделитель '\0', если передать эту строку в общую **Открытие файла** диалоговое окно.  
  
##  <a name="getmaxcolortableentries"></a>  CImage::GetMaxColorTableEntries  
 Получает максимальное количество записей в таблице цветов.  
  
```
int GetMaxColorTableEntries() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество записей в таблице цветов.  
  
### <a name="remarks"></a>Примечания  
 Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="getpitch"></a>  CImage::GetPitch  
 Получает высоту изображения.  
  
```
int GetPitch() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота изображения. Если возвращаемое значение является отрицательным, растрового изображения является DIB снизу вверх, и его источником является нижнего левого угла. Если возвращаемое значение является положительным, растрового изображения является DIB сверху вниз, и его источником является верхний левый угол.  
  
### <a name="remarks"></a>Примечания  
 Угол наклона будет расстояние в байтах между в начало следующей строки точечного рисунка и два адреса памяти, представляющие начала одной строки точечного рисунка. Поскольку тон измеряется в байтах, высота изображения поможет вам определить формат пикселей. Голос можно также включить дополнительную память, зарезервирована для битовой карты.  
  
 Используйте `GetPitch` с [GetBits](#getbits) для поиска отдельных пикселей изображение.  
  
> [!NOTE]
>  Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="getpixel"></a>  CImage::GetPixel  
 Получает цвет пикселя в расположении, заданном *x* и *y*.  
  
```
COLORREF GetPixel(int x,int y) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Координата x точки.  
  
 *y*  
 Координата y точки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Красный, зеленый, синий (RGB) значение пикселя. Если точка находится вне текущей области обрезки, возвращаемое значение равно **CLR_INVALID**.  
  
##  <a name="getpixeladdress"></a>  CImage::GetPixelAddress  
 Извлекает адрес точки.  
  
```
void* GetPixelAddress(int x,int y) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Координата x точки.  
  
 *y*  
 Координата y точки.  
  
### <a name="remarks"></a>Примечания  
 Адрес определяется в соответствии с координаты точки, высота растрового изображения и бита на пиксель.  
  
 Для форматов, которые имеют меньше 8 бит на пиксель этот метод возвращает адрес байт, содержащий пикселя. Например, если формат изображения содержит 4 бита на пиксель `GetPixelAddress` возвращает адрес первого пикселя в байт и необходимо вычислить для 2 пикселя в байте.  
  
> [!NOTE]
>  Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="gettransparentcolor"></a>  CImage::GetTransparentColor  
 Извлекает индекс прозрачного цвета в цветовой палитре.  
  
```
LONG GetTransparentColor() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс прозрачный цвет.  
  
##  <a name="getwidth"></a>  CImage::GetWidth  
 Получает ширину в пикселях.  
  
```
int GetWidth() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина растрового изображения в пикселях.  
  
##  <a name="isdibsection"></a>  CImage::IsDIBSection  
 Определяет, является ли вложенный растрового изображения DIB раздела.  
  
```
bool IsDIBSection() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если точечный рисунок вложенного раздела DIB. В противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Если растровое изображение не раздел DIB, нельзя использовать следующие `CImage` методы, которые поддерживают только растровые изображения DIB раздела:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
##  <a name="isindexed"></a>  CImage::IsIndexed  
 Определяет, является ли пиксели сопоставляются с цветовой палитры.  
  
```
bool IsIndexed() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если индексированные; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает **true** только в том случае, если точечный рисунок 8-разрядное (256 цветов) или менее.  
  
> [!NOTE]
>  Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="isnull"></a>  CImage::IsNull  
 Определяет, если в данный момент загружен растрового изображения.  
  
```
bool IsNull() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает **True** Если растровое изображение не загружен; в противном случае **False**.  
  
##  <a name="istransparencysupported"></a>  CImage::IsTransparencySupported  
 Указывает, поддерживает ли приложение прозрачными точечными рисунками.  
  
```
static BOOL IsTransparencySupported() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если текущая платформа поддерживает прозрачность. В противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение не равно нулю, а также поддерживается прозрачность, вызов [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt), или [нарисовать](#draw) обрабатывающий прозрачные цвета.  
  

##  <a name="load"></a>  CImage::Load  
 Загружает изображение.  
  
```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszFileName`  
 Указатель на строку, содержащую имя файла изображения для загрузки.  
  
 `pStream`  
 Указатель на поток, содержащий имя файла изображения для загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
### <a name="remarks"></a>Примечания  
 Загружает изображение, указанное свойством *pszFileName* или `pStream`.  
  
 Типы допустимых изображений, BMP, GIF, JPEG, PNG и TIFF.  
  
##  <a name="loadfromresource"></a>  CImage::LoadFromResource  
 Загружает изображение из `BITMAP` ресурсов.  
  
```
void LoadFromResource(
 HINSTANCE hInstance,
 LPCTSTR pszResourceName) throw();

void LoadFromResource(
 HINSTANCE hInstance,
 UINT nIDResource) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 Дескриптор экземпляра модуля, содержащего изображение для загрузки.  
  
 `pszResourceName`  
 Указатель на строку, содержащую имя ресурса, содержащего изображение для загрузки.  
  
 `nIDResource`  
 Идентификатор ресурса для загрузки.  
  
### <a name="remarks"></a>Примечания  
 Ресурс должен быть типа `BITMAP`.  
  
##  <a name="maskblt"></a>  CImage::MaskBlt  
 Объединяет данные о цвете для исходного и конечного точечных рисунков, с помощью указанной маске и выполнению растровую операцию.  
  
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
 `hDestDC`  
 Дескриптор модуля, которого исполняемый файл содержит ресурс.  
  
 `xDest`  
 Координата x, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `yDest`  
 Координата y, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `nDestWidth`  
 Ширина в логических единицах прямоугольник и исходный точечный рисунок назначения.  
  
 `nDestHeight`  
 Высота в логических единицах прямоугольник и исходный точечный рисунок назначения.  
  
 `xSrc`  
 Логический Координата x верхнего левого угла исходного точечного рисунка.  
  
 `ySrc`  
 Логический Координата y верхнего левого угла исходного точечного рисунка.  
  
 `hbmMask`  
 Дескриптор точечного рисунка монохромный маски, в сочетании с цветной точечный рисунок в контекст исходного устройства.  
  
 `xMask`  
 Смещение пикселей горизонтальная маска растровое изображение, указанное по `hbmMask` параметр.  
  
 `yMask`  
 Смещение вертикальной пикселей для маски битовой карты, заданные `hbmMask` параметра.  
  
 `dwROP`  
 Указывает переднего плана и фона коды троичный растровых операций, которые метод использует для управления сочетание исходных и целевых данных. Код операции растровых фона хранится в старший байт, старшие слова этого значения; Код операции растровых переднего плана хранится в младший байт, старшие слова этого значения; младшее слово это значение игнорируется и должно быть равно нулю. Обсуждение переднего плана и фона в контексте данного метода см. в разделе `MaskBlt` в Windows SDK. Список общих коды растровых операций см. в разделе `BitBlt` в Windows SDK.  
  
 `rectDest`  
 Ссылку на `RECT` структуры, определение назначения.  
  
 `pointSrc`  
 Объект `POINT` структуры, позволяющее определить, в верхнем левом углу исходного прямоугольника.  
  
 `pointMask`  
 Объект **ТОЧКИ** структуры, позволяющее определить, в верхнем левом углу растрового изображения маски.  
  
 `pointDest`  
 Ссылку на **ТОЧКИ** структура, определяющая верхнего левого угла прямоугольника назначения в логических единицах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод применим к Windows NT версии 4.0 и более поздних версий.  
  
##  <a name="operator_hbitmap"></a>  CImage::operator HBITMAP  
 Этот оператор используется для получения вложенного дескриптор Windows GDI `CImage` объекта. Этот оператор — оператор приведения, который поддерживает прямое использование `HBITMAP` объекта.  
  
##  <a name="plgblt"></a>  CImage::PlgBlt  
 Выполняет перемещение набора битов с прямоугольник в контексте устройства источника параллелограмма в контексте устройства назначения.  
  
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
 `hDestDC`  
 Дескриптор контекста устройства назначения.  
  
 *pPoints*  
 Указатель на массив из трех точек место на логическом, определяющие трех углов конечного параллелограмма. Первая точка в этот массив, правого верхнего угла до второй точки в этом массиве и левый нижний угол в третью точку сопоставляется верхнем левом углу исходного прямоугольника. Неявные четвертой точки параллелограмма сопоставляется нижнего правого угла исходного прямоугольника.  
  
 `hbmMask`  
 Дескриптор Дополнительно монохромный точечный рисунок, используемыми в маске цвета исходного прямоугольника.  
  
 `xSrc`  
 Координата x, в логических единицах верхнего левого угла исходного прямоугольника.  
  
 `ySrc`  
 Координата y, в логических единицах верхнего левого угла исходного прямоугольника.  
  
 `nSrcWidth`  
 Ширина в логических единицах исходного прямоугольника.  
  
 `nSrcHeight`  
 Высота в логических единицах исходного прямоугольника.  
  
 `xMask`  
 Координата по оси x верхнего левого угла монохромный точечный рисунок.  
  
 `yMask`  
 Координата по оси y верхнего левого угла монохромный точечный рисунок.  
  
 `rectSrc`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, указав координаты исходного прямоугольника.  
  
 `pointMask`  
 Объект [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуры, позволяющее определить, в верхнем левом углу растрового изображения маски.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `hbmMask` определяет допустимый монохромный точечный рисунок, **PlgBit** использует это растровое изображение для маскировки биты данных о цвете из исходного прямоугольника.  
  
 Этот метод применим к Windows NT версии 4.0 и более поздних версий. В разделе [PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804) в Windows SDK для получения дополнительных сведений.  
  
##  <a name="releasedc"></a>  CImage::ReleaseDC  
 Освобождает контекст устройства.  
  
```
void ReleaseDC() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку одновременно можно выбрать только один точечный рисунок в контексте устройства, необходимо вызвать метод `ReleaseDC` для каждого вызова [GetDC](#getdc).  
  
##  <a name="releasegdiplus"></a>  CImage::ReleaseGDIPlus  
 Освобождает ресурсы, используемые в GDI +.  
  
```
void ReleaseGDIPlus() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться для освобождения ресурсов, выделенных глобальный `CImage` объекта. В разделе [CImage::CImage](#cimage).  
  
##  <a name="save"></a>  CImage::Save  
 Сохраняет изображение в указанный поток или файл на диске.  
  
```
HRESULT Save(IStream* pStream,
 REFGUID guidFileType) const throw();

HRESULT Save(LPCTSTR pszFileName,
 REFGUID guidFileType= GUID_NULL) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 Указатель на объект COM IStream, который содержит данные файла изображения.  
  
 *pszFileName*  
 Указатель на имя файла изображения.  
  
 `guidFileType`  
 Тип файла, чтобы сохранить изображение в виде. Ниже указаны доступные значения.  
  
- **ImageFormatBMP** несжатого точечного рисунка.  
  
- **ImageFormatPNG** сжатый образ переносимой сетевой графики (PNG).  
  
- **ImageFormatJPEG** сжатые в формате JPEG.  
  
- **ImageFormatGIF** сжатый образ GIF.  
  
> [!NOTE]
>  Полный список констант см. в разделе **константы формат файла изображения** в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы сохранить изображение с указанным именем и типом. Если `guidFileType` не указан, расширение имени файла будет использоваться для определения формата изображения. Если расширение не указано, изображение будет сохранено в формате BMP.  
  
##  <a name="setcolortable"></a>  CImage::SetColorTable  
 Задает значения цвет красный, зеленый, синий (RGB) для диапазона записей в палитре DIB раздела.  
  
```
void SetColorTable(
  UINT iFirstColor, 
  UINT nColors,
  const RGBQUAD* prgbColors) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `iFirstColor`  
 Индекс таблицы цвет первой записи для задания.  
  
 `nColors`  
 Количество записей таблицы цветов для задания.  
  
 `prgbColors`  
 Указатель на массив [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) структуры, чтобы задать цвет таблицы записей.  
  
### <a name="remarks"></a>Примечания  
 Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="setpixel"></a>  CImage::SetPixel  
 Задает цвет пикселя в заданную позицию в битовой карте.  
  
```
void SetPixel(int x, int y, COLORREF color) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Горизонтальное расположение устанавливаемой точки.  
  
 *y*  
 Вертикальное расположение устанавливаемой точки.  
  
 `color`  
 Цвет, который назначен пикселя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если пикселя координирует лежит за пределами области обрезки выбранного.  
  
##  <a name="setpixelindexed"></a>  CImage::SetPixelIndexed  
 Задает цвет, расположенной на цвет пикселя `iIndex` в цветовой палитре.  
  
```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Горизонтальное расположение устанавливаемой точки.  
  
 *y*  
 Вертикальное расположение устанавливаемой точки.  
  
 `iIndex`  
 Индекс цвета в цветовой палитре.  
  
##  <a name="setpixelrgb"></a>  CImage::SetPixelRGB  
 Задает пикселя в расположениях, указанных в *x* и *y* к цветам, обозначенном *r*, *g*, и *b*, в красного, зеленого и синего (RGB) образа.  
  
```
void SetPixelRGB(  
 int x,
 int y,
 BYTE r,
 BYTE g,
 BYTE b) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Горизонтальное расположение устанавливаемой точки.  
  
 *y*  
 Вертикальное расположение устанавливаемой точки.  
  
 *r*  
 Интенсивность красного цвета.  
  
 *g*  
 Интенсивность зеленым цветом.  
  
 *b*  
 Интенсивность синий цвет.  
  
### <a name="remarks"></a>Примечания  
 Параметры красного, зеленого и синего выражается числом от 0 до 255. Если все три параметра задать значение 0, объединенный итоговый цвет является black. Если все три параметра равным 255, объединенный итоговый цвет отображается белый цвет.  
  
##  <a name="settransparentcolor"></a>  CImage::SetTransparentColor  
 Задает цвет в заданную позицию индексированных как прозрачный.  
  
```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *iTransparentColor*  
 Индекс в цветовой палитре, задаваемое для прозрачного цвета. Если значение-1, то цвет не присваивается прозрачным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ранее индекс цвета набора как прозрачный.  
  
##  <a name="stretchblt"></a>  CImage::StretchBlt  
 Копирует растровое изображение из контекста исходного устройства это текущий контекст устройства.  
  
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
 `hDestDC`  
 Дескриптор контекста устройства назначения.  
  
 `xDest`  
 Координата x, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `yDest`  
 Координата y, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `nDestWidth`  
 Ширина в логических единицах прямоугольника назначения.  
  
 `nDestHeight`  
 Высота в логических единицах прямоугольника назначения.  
  
 `dwROP`  
 Растровые выполняемой операции. Коды растровых операций определяют, как объединяются в битах источника, назначения и шаблон (как определено выбранной кисти) назначения. В разделе [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) в Windows SDK список другие коды растровых операций и их описания.  
  
 `rectDest`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, определение назначения.  
  
 `xSrc`  
 Координата x, в логических единицах верхнего левого угла исходного прямоугольника.  
  
 `ySrc`  
 Координата y, в логических единицах верхнего левого угла исходного прямоугольника.  
  
 `nSrcWidth`  
 Ширина в логических единицах исходного прямоугольника.  
  
 `nSrcHeight`  
 Высота в логических единицах исходного прямоугольника.  
  
 `rectSrc`  
 Ссылку на `RECT` структуры, определение источника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120) в Windows SDK.  
  
##  <a name="transparentblt"></a>  CImage::TransparentBlt  
 Копирует растровое изображение из контекста исходного устройства это текущий контекст устройства.  
  
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
 `hDestDC`  
 Дескриптор контекста устройства назначения.  
  
 `xDest`  
 Координата x, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `yDest`  
 Координата y, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `nDestWidth`  
 Ширина в логических единицах прямоугольника назначения.  
  
 `nDestHeight`  
 Высота в логических единицах прямоугольника назначения.  
  
 *crTransparent*  
 Цвет в исходный точечный рисунок должен рассматриваться как прозрачный. По умолчанию **CLR_INVALID**, указывающее, что следует использовать как прозрачный цвет изображения в настоящее время набор цветов.  
  
 `rectDest`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, определение назначения.  
  
 `xSrc`  
 Координата x, в логических единицах верхнего левого угла исходного прямоугольника.  
  
 `ySrc`  
 Координата y, в логических единицах верхнего левого угла исходного прямоугольника.  
  
 `nSrcWidth`  
 Ширина в логических единицах исходного прямоугольника.  
  
 `nSrcHeight`  
 Высота в логических единицах исходного прямоугольника.  
  
 `rectSrc`  
 Ссылку на `RECT` структуры, определение источника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** в случае успеха, в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 `TransparentBlt`поддерживается для точечные рисунки источника 4 битов на пиксель и 8 бит на пиксель. Используйте [CImage::AlphaBlend](#alphablend) указание 32 бита на пиксель растровые изображения с прозрачностью.  
  
  
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
 [Образец MMXSwarm](../../visual-cpp-samples.md)   
 [Образце SimpleImage](../../visual-cpp-samples.md)   
 [Аппаратно независимые точечные рисунки](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md) [аппаратно независимые точечные рисунки](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   









