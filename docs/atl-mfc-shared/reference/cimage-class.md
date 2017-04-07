---
title: "Класс CImage | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 20
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: f74e5952401d6f9608425681cd91120b648e7b13
ms.lasthandoff: 02/24/2017

---
# <a name="cimage-class"></a>CImage-класс
`CImage`предоставляет поддержку расширенного растровых изображений, включая возможность загрузки и сохранения изображений в формате JPEG, GIF, BMP и Portable Network Graphics (PNG).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CImage
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CImage::CImage](#cimage)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CImage::AlphaBlend](#alphablend)|Отображает точечным рисункам, имеющим прозрачным или полупрозрачным пикселей.|  
|[CImage::Attach](#attach)|Присоединяет `HBITMAP` для `CImage` объектов. Может использоваться с точечные рисунки не DIB раздела или растровые изображения DIB раздела.|  
|[CImage::BitBlt](#bitblt)|Копирует точечный рисунок из исходного контекста устройства это текущий контекст устройства.|  
|[CImage::Create](#create)|Создает раздел растровое изображение DIB и присоединяет его к ранее сформированный `CImage` объекта.|  
|[CImage::CreateEx](#createex)|Создает раздел растровое изображение DIB (с дополнительными параметрами) и присоединяет его к ранее сформированный `CImage` объекта.|  
|[CImage::Destroy](#destroy)|Отсоединяет точечный рисунок из `CImage` объекта и уничтожает точечного рисунка.|  
|[CImage::Detach](#detach)|Отсоединяет точечный рисунок из `CImage` объекта.|  
|[CImage::Draw](#draw)|Копирует точечный рисунок из исходного прямоугольника в прямоугольник назначения. **Рисование** растягивает или сжимает точечный рисунок в соответствии с размерами прямоугольника назначения, при необходимости и обрабатывает альфа-смешение и прозрачного цвета.|  
|[CImage::GetBits](#getbits)|Извлекает указатель на фактическое пикселов точечного рисунка.|  
|[CImage::GetBPP](#getbpp)|Извлекает бита на пиксель.|  
|[CImage::GetColorTable](#getcolortable)|Получает красный, зеленый, синий (RGB) цветовых значений из диапазона записей в таблице цветов.|  
|[CImage::GetDC](#getdc)|Получает контекст устройства, в котором выбран текущий точечного рисунка.|  
|[CImage::GetExporterFilterString](#getexporterfilterstring)|Поиск доступных изображениями и их описания.|  
|[CImage::GetHeight](#getheight)|Получает высоту текущего изображения в пикселях.|  
|[CImage::GetImporterFilterString](#getimporterfilterstring)|Поиск доступных изображениями и их описания.|  
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|Получает максимальное число записей в таблице цветов.|  
|[CImage::GetPitch](#getpitch)|Получает высоту текущего изображения, в байтах.|  
|[CImage::GetPixel](#getpixel)|Получает цвет пикселя, определяемое *x* и *y*.|  
|[CImage::GetPixelAddress](#getpixeladdress)|Получает адрес заданной точки.|  
|[CImage::GetTransparentColor](#gettransparentcolor)|Получает положение прозрачный цвет в таблице цветов.|  
|[CImage::GetWidth](#getwidth)|Получает ширину текущего изображения в пикселях.|  
|[CImage::IsDIBSection](#isdibsection)|Определяет, является ли вложенное растрового изображения DIB раздела.|  
|[CImage::IsIndexed](#isindexed)|Указывает, что цветов точечного рисунка, сопоставляются индексированную палитру.|  
|[CImage::IsNull](#isnull)|Указывает, если в данный момент загружен исходный точечный рисунок.|  
|[CImage::IsTransparencySupported](#istransparencysupported)|Указывает, поддерживает прозрачными точечными рисунками, скомпилированного для Windows 2000 или более поздней версии приложения.|  
|[CImage::Load](#load)|Загружает изображение из указанного файла.|  
|[CImage::LoadFromResource](#loadfromresource)|Загружает изображение из указанного ресурса.|  
|[CImage::MaskBlt](#maskblt)|Объединяет данные о цвете для исходного и конечного точечных рисунков с помощью указанной маске и растровая операция.|  
|[CImage::PlgBlt](#plgblt)|Выполняет перемещение набора битов с прямоугольник в контекста исходного устройства в параллелограмм, в контексте устройства назначения.|  
|[CImage::ReleaseDC](#releasedc)|Освобождает контекст устройства, который был извлечен с [CImage::GetDC](#getdc).|  
|[CImage::ReleaseGDIPlus](#releasegdiplus)|Освобождает ресурсы, используемые GDI +. Необходимо вызвать для освобождения ресурсов, созданных глобальный `CImage` объекта.|  
|[CImage::Save](#save)|Сохраняет изображение в указанный тип. **Сохранить** нельзя указать параметры изображения.|  
|[CImage::SetColorTable](#setcolortable)|Задает RGB красный, зеленый, синий) значения в диапазоне элементов в таблице цветов в разделе DIB цветов.|  
|[CImage::SetPixel](#setpixel)|Задает пикселя по указанным координатам на указанный цвет.|  
|[CImage::SetPixelIndexed](#setpixelindexed)|Задает пикселя по указанным координатам цвет палитры по указанному индексу.|  
|[CImage::SetPixelRGB](#setpixelrgb)|Задает пикселя по указанным координатам значение указанного красный, зеленый, синего (RGB).|  
|[CImage::SetTransparentColor](#settransparentcolor)|Задает индекс цвет, который будет рассматриваться как прозрачный. Можно быть только один цвет в палитре.|  
|[CImage::StretchBlt](#stretchblt)|Копирует точечный рисунок из исходного прямоугольника в прямоугольник назначения, растягивая или сжимая точечный рисунок в соответствии с размерами прямоугольника назначения, при необходимости.|  
|[CImage::TransparentBlt](#transparentblt)|Копирует точечный рисунок и прозрачный цвет из контекста исходного устройства это текущий контекст устройства.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CImage::operator HBITMAP](#operator_hbitmap)|Возвращает дескриптор Windows, присоединенные к `CImage` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CImage`принимает точечные рисунки, которые либо разделы аппаратно независимым точечным рисунком (DIB) или нет; Тем не менее, можно использовать [создать](#create) или [CImage::Load](#load) с только разделы DIB. Можно присоединить раздел не DIB растровое изображение, чтобы `CImage` с помощью [присоединить](#attach), но его нельзя использовать следующие `CImage` методы, которые поддерживают только растровые изображения DIB раздела:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
 Чтобы определить, является ли вложенное растрового изображения DIB раздел, вызовите [IsDibSection](#isdibsection)**.**  
  
> [!NOTE]
> **Примечание** в Visual Studio .NET 2003, этот класс отслеживает количество число `CImage` объекты, созданные. Каждый раз, когда число становится равным 0, функция **GdiplusShutdown** вызывается автоматически для освобождения ресурсов, используемых в GDI +. Это гарантирует, что любой `CImage` уничтожения объектов, прямо или косвенно созданные библиотеки DLL всегда правильно и что **GdiplusShutdown** не вызывается из `DllMain`.  
  
> [!NOTE]
>  С помощью глобального `CImage` объектов в библиотеке DLL не рекомендуется. Если необходимо использовать глобальный `CImage` объектов в библиотеке DLL, вызов [CImage::ReleaseGDIPlus](#releasegdiplus) явно освободить ресурсы, используемые GDI +.  
  
 `CImage`не могут быть выбраны в новую [CDC](../../mfc/reference/cdc-class.md). `CImage`создает собственный **HDC** для изображения. Поскольку `HBITMAP` может быть выбран только в одну **HDC** одновременно, `HBITMAP` связанных с `CImage` не могут быть выбраны в другой **HDC**. Если вам требуется `CDC`, получить **HDC** из `CImage` и присвойте ему [CDC::FromHandle] (.. /.. /MFC/Reference/CDC-Class.md#cdc__fromhandle.  
  
## <a name="example"></a>Пример  
```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```  
  
 При использовании `CImage` в проекте MFC Обратите внимание на то, какие функции-члены в проекте ожидают, что указатель [CBitmap](../../mfc/reference/cbitmap-class.md) объекта. Если вы хотите использовать `CImage` с помощью функции как [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu), используйте [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), передайте его в своей `CImage` `HBITMAP`и использовать возвращенный `CBitmap*`.  

  
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

  
 Через `CImage`, у вас есть доступ к реальные биты раздела DIB. Можно использовать `CImage` объекта ранее использовали раздел Win32 HBITMAP или DIB.  
  
> [!NOTE]
>  Следующие `CImage` методы имеют ограничения на их использование:  
  
|Метод|Ограничение|  
|------------|----------------|  
|[PlgBlt](#plgblt)|Работает только в Windows NT 4.0 или более поздней версии. Не будет работать для приложений, работающих в Windows 95/98 или более поздней версии.|  
|[MaskBlt](#maskblt)|Работает только в Windows NT 4.0 или более поздней версии. Не будет работать для приложений, работающих в Windows 95/98 или более поздней версии.|  
|[AlphaBlend](#alphablend)|Работа с только Windows 2000, Windows 98 и более поздних системах.|  
|[TransparentBlt](#transparentblt)|Работа с только Windows 2000, Windows 98 и более поздних системах.|  
|[Рисование](#draw)|Поддерживает прозрачность с помощью только Windows 2000, Windows 98 и более поздних системах.|  
  
 Можно использовать `CImage` от MFC или библиотеки ATL.  
  
> [!NOTE]
>  При создании проекта с использованием `CImage`, необходимо определить `CString` перед включением `atlimage.h`. Если в проекте используется ATL без использования MFC, включают `atlstr.h` перед включением `atlimage.h`. Если проект использует MFC (или если это проект ATL с поддержкой MFC), включают `afxstr.h` перед включением `atlimage.h`.  
>   
>  Аналогичным образом, необходимо включить `atlimage.h` перед включением `atlimpl.cpp`. Для этого легко включить `atlimage.h` в своей `stdafx.h`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlimage.h  
  
##  <a name="alphablend"></a>CImage::AlphaBlend  
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
 `hDestDC`  
 Дескриптор контекста устройства назначения.  
  
 `xDest`  
 Координата x, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `yDest`  
 Координата y, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 *bSrcAlpha*  
 Значение альфа-прозрачность для использования на весь исходный точечный рисунок. По умолчанию 0xff (255) предполагается, что образ непрозрачен и что вы хотите использовать только альфа-значения каждого пикселя.  
  
 `bBlendOp`  
 Функция альфа смешения для источника и точечные рисунки назначения, глобальное значение альфа-канала для применения к весь исходный точечный рисунок, а также сведения о формате для исходного точечного рисунка. Функции совмещенного источника и назначения, в настоящее время ограничены **AC_SRC_OVER**.  
  
 `pointDest`  
 Ссылку на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структура, определяющая в верхнем левом углу конечного прямоугольника, в логических единицах.  
  
 `nDestWidth`  
 Ширина в логических единицах прямоугольника назначения.  
  
 `nDestHeight`  
 Высота в логических единицах прямоугольника назначения.  
  
 `xSrc`  
 Логическую координату x верхнем левом углу исходного прямоугольника.  
  
 `ySrc`  
 Логический Координата y верхнего левого угла исходного прямоугольника.  
  
 `nSrcWidth`  
 Ширина в логических единицах исходного прямоугольника.  
  
 `nSrcHeight`  
 Высота в логических единицах исходного прямоугольника.  
  
 `rectDest`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, определение назначения.  
  
 `rectSrc`  
 Ссылку на `RECT` структура, определение источника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Точечные рисунки с альфа смешение поддерживает наложение цвета на основе каждого пикселя.  
  
 Когда `bBlendOp` задано значение по умолчанию **AC_SRC_OVER**, помещении исходный точечный рисунок в точечный рисунок назначения на основе альфа-значений исходного изображения.  

##  <a name="attach"></a>CImage::Attach  
 Присоединяет `hBitmap` для `CImage` объектов.  
  
```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hBitmap`  
 Дескриптор `HBITMAP`.  
  
 *eOrientation*  
 Задает ориентацию растрового изображения. Ниже указаны доступные значения.  
  
- **DIBOR_DEFAULT** ориентацию растрового изображения определяется операционной системой. Тем не менее это может не всегда имеют ожидаемые результаты для всех операционных систем. Дополнительные сведения об этом см. в следующей статье базы знаний ( **Q186586**): PRB: GetObject() всегда возвращает положительное высоту для DIB разделов.  
  
- **DIBOR_BOTTOMUP** строки растрового изображения не в обратном порядке. В результате [CImage::GetBits](#getbits) для возврата указателя в конец буфера точечного рисунка и [CImage::GetPitch](#getpitch) для возврата отрицательное число.  
  
- **DIBOR_TOPDOWN** строки растрового изображения находятся в порядке сверху вниз. В результате [CImage::GetBits](#getbits) для возврата указателя на первый байт в буфер точечного рисунка и [CImage::GetPitch](#getpitch) для возврата положительное число.  
  
### <a name="remarks"></a>Примечания  
 Точечный рисунок может быть точечный рисунок не DIB раздела или раздела растрового изображения DIB. В разделе [IsDIBSection](#isdibsection) список методов, которые можно использовать только с DIB статьи точечных рисунков.  
  
##  <a name="bitblt"></a>CImage::BitBlt  
 Копирует точечный рисунок из исходного контекста устройства это текущий контекст устройства.  
  
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
 Выполняемая операция растровые. Коды растровых операций определяют, как будут объединены биты источника, назначения и шаблон (в соответствии с выбранной кисти) назначения. В разделе [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) в [!INCLUDE[winSDK](./includes/winsdk_md.md)] список другие коды растровых операций и их описания.  
  
 `pointDest`  
 Объект [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру указывая верхнего левого угла прямоугольника назначения.  
  
 `nDestWidth`  
 Ширина в логических единицах прямоугольника назначения.  
  
 `nDestHeight`  
 Высота в логических единицах прямоугольника назначения.  
  
 `xSrc`  
 Логическую координату x верхнем левом углу исходного прямоугольника.  
  
 `ySrc`  
 Логический Координата y верхнего левого угла исходного прямоугольника.  
  
 `rectDest`  
 Объект [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуру указывая прямоугольника назначения.  
  
 `pointSrc`  
 Объект **ТОЧКИ** структуру указывая верхнем левом углу исходного прямоугольника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) в [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
##  <a name="cimage"></a>CImage::CImage  
 Создает объект `CImage`.  
  
```
CImage() throw();
```  
  
### <a name="remarks"></a>Примечания  
 После создания объекта вызова [создать](#create), [нагрузки](#load), [LoadFromResource](#loadfromresource), или [присоединить](#attach) присоединить объект точечного рисунка.  
  
 **Примечание** в Visual Studio этот класс отслеживает количество число `CImage` объекты, созданные. Каждый раз, когда число становится равным 0, функция **GdiplusShutdown** вызывается автоматически для освобождения ресурсов, используемых в GDI +. Это гарантирует, что любой `CImage` уничтожения объектов, прямо или косвенно созданные библиотеки DLL всегда правильно и что **GdiplusShutdown** из DllMain не вызывается.  
  
 С помощью глобального `CImage` объектов в библиотеке DLL не рекомендуется. Если необходимо использовать глобальный `CImage` объектов в библиотеке DLL, вызов [CImage::ReleaseGDIPlus](#releasegdiplus) явно освободить ресурсы, используемые GDI +.  
  
##  <a name="create"></a>CImage::Create  
 Создает `CImage` bitmap и присоединить ее к ранее сформированный `CImage` объекта.  
  
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
 Высота `CImage` растрового изображения в пикселях. Если `nHeight` положителен, точечный рисунок является DIB снизу вверх и его источником является левый нижний угол. Если `nHeight` является отрицательным, растрового изображения DIB сверху вниз и исходному верхнего левого угла.  
  
 `nBPP`  
 Число бит на пиксель в битовой карте. Обычно 4, 8, 16, 24 или 32. Может быть 1 монохромный растровые изображения или маски.  
  
 `dwFlags`  
 Указывает, если объект точечный рисунок имеет альфа-канала. Может представлять собой сочетание из нуля или более из следующих значений:  
  
- **createAlphaChannel** можно использовать, только если `nBPP` — 32, и `eCompression` — **BI_RGB**. Если указано, созданного образа имеет значение альфа-канала (прозрачности) для каждого пиксела, хранящихся в четвертый байт каждый пиксель (не используется в образе небуквенных 32-разрядных). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).  
  
> [!NOTE]
>  В вызовах [CImage::Draw](#draw), рисунки с альфа-каналом выполняется автоматически альфа-смешение в место назначения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="createex"></a>CImage::CreateEx  
 Создает `CImage` bitmap и присоединить ее к ранее сформированный `CImage` объекта.  
  
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
 Высота `CImage` растрового изображения в пикселях. Если `nHeight` положителен, точечный рисунок является DIB снизу вверх и его источником является левый нижний угол. Если `nHeight` является отрицательным, растрового изображения DIB сверху вниз и исходному верхнего левого угла.  
  
 `nBPP`  
 Число бит на пиксель в битовой карте. Обычно 4, 8, 16, 24 или 32. Может быть 1 монохромный растровые изображения или маски.  
  
 `eCompression`  
 Указывает тип сжатия для сжатого битовой карты сверху вниз (не могут быть сжаты изображения DIB сверху вниз). Может принимать одно из следующих значений:  
  
- **BI_RGB** формат без сжатия. Указание этого значения при вызове `CImage::CreateEx` эквивалентно вызову метода `CImage::Create`.  
  
- **BI_BITFIELDS** формат без сжатия, а таблица цветов состоит из трех `DWORD` цвет маски, которые указывают, красный, зеленый и синий компоненты, соответственно, каждого пикселя. Это допустимо, при использовании с 16 и 32 bpp точечных рисунков.  
  
 *pdwBitfields*  
 Используется только если `eCompression` равен **BI_BITFIELDS**, в противном случае он должен быть **NULL**. Указатель на массив из трех `DWORD` битовой маски, указав битов из каждого пиксела используются для красного, зеленого и синего компонентов цвета соответственно. Дополнительные сведения об ограничениях для битовые поля в разделе [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) в [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
 `dwFlags`  
 Указывает, если объект точечный рисунок имеет альфа-канала. Может представлять собой сочетание из нуля или более из следующих значений:  
  
- **createAlphaChannel** можно использовать, только если `nBPP` — 32, и `eCompression` — **BI_RGB**. Если указано, созданного образа имеет значение альфа-канала (прозрачности) для каждого пиксела, хранящихся в четвертый байт каждый пиксель (не используется в образе небуквенных 32-разрядных). Этот альфа-канал автоматически используется при вызове [CImage::AlphaBlend](#alphablend).  
  
    > [!NOTE]
    >  В вызовах [CImage::Draw](#draw), рисунки с альфа-каналом выполняется автоматически альфа-смешение в место назначения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** в случае успешного выполнения. В противном случае **FALSE**.  
  
### <a name="example"></a>Пример  
 В следующем примере создается 100 x 100 пикселов точечного рисунка, с помощью 16 бит для кодирования каждого пиксела. В необходимом 16-разрядных биты 0-3 кодирования красного компонента, бит 4-7 кодирования зеленого и 8 11 бит кодируют синий. Оставшиеся биты 4 не используются.  

```cpp  
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```


##  <a name="destroy"></a>CImage::Destroy  
 Отсоединяет точечный рисунок из `CImage` объекта и уничтожает точечного рисунка.  
  
```
void Destroy() throw();
```  
  
##  <a name="detach"></a>CImage::Detach  
 Отсоединяет точечный рисунок из `CImage` объекта.  
  
```
HBITMAP Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор точечного рисунка отсоединения или **NULL** Если присоединен не точечного рисунка.  
  
##  <a name="draw"></a>CImage::Draw  
 Копирует точечный рисунок из исходного контекста устройства для текущего контекста устройства.  
  
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
 Координата x, в логических единицах верхнем левом углу исходного прямоугольника.  
  
 `ySrc`  
 Координата y, в логических единицах верхнем левом углу исходного прямоугольника.  
  
 `nSrcWidth`  
 Ширина в логических единицах исходного прямоугольника.  
  
 `nSrcHeight`  
 Высота в логических единицах исходного прямоугольника.  
  
 `rectDest`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, определение назначения.  
  
 `rectSrc`  
 Ссылку на `RECT` структура, определение источника.  
  
 `pointDest`  
 Ссылку на [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структура, определяющая в верхнем левом углу конечного прямоугольника, в логических единицах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **Рисование** выполняет те же функции, как [StretchBlt](#stretchblt), если изображение содержит прозрачный цвет или альфа-канала. В этом случае **рисовать** выполняет те же функции, как [TransparentBlt](#transparentblt) или [AlphaBlend](#alphablend) при необходимости.  
  
 Для версий **рисовать** не указан исходный прямоугольник, всего исходного изображения используется по умолчанию. Для версии **рисовать** , для которого не указан размер конечного прямоугольника, размер исходного изображения — по умолчанию и не растяжение или сжатие происходит.  
  
##  <a name="getbits"></a>CImage::GetBits  
 Извлекает указатель на фактическое битовые значения заданной точки в точечном рисунке.  
  
```
void* GetBits() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на буфер точечного рисунка. Если точечный рисунок DIB снизу вверх, указатель точки в конце буфера. Если точечный рисунок DIB сверху вниз, указатель указывает на первый байт буфера.  
  
### <a name="remarks"></a>Примечания  
 Используя этот указатель, а также значение, возвращаемое [GetPitch](#getpitch), можно найти и изменить отдельные точки на изображении.  
  
> [!NOTE]
>  Этот метод поддерживает только DIB раздел растровых изображений; Следовательно, доступ к пикселы `CImage` объекта так же, как пиксели раздел DIB. Возвращенный указатель указывает на пиксель на месте (0, 0).  
  
##  <a name="getbpp"></a>CImage::GetBPP  
 Получает значение бита на пиксел.  
  
```
int GetBPP() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество битов на пиксел.  
  
### <a name="remarks"></a>Примечания  
 Это значение определяет количество битов, определяющих каждый пиксель и максимальное число цветов в точечном рисунке.  
  
 Бит на пиксель, обычно является 1, 4, 8, 16, 24 или 32. В разделе **biBitCount** членом [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) в [!INCLUDE[winSDK](./includes/winsdk_md.md)] Дополнительные сведения об этом значении.  
  
##  <a name="getcolortable"></a>CImage::GetColorTable  
 Получает красный, зеленый, синий (RGB) цветовых значений из диапазона записей в палитре в разделе DIB.  
  
```
void GetColorTable(UINT iFirstColor,
 UINT nColors,
 RGBQUAD* prgbColors) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `iFirstColor`  
 Индекс таблицы цвет первой операции для получения.  
  
 `nColors`  
 Количество извлекаемых записей таблицы цвета.  
  
 `prgbColors`  
 Указатель на массив [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) записи таблицы структур для извлечения цвета.  
  
##  <a name="getdc"></a>CImage::GetDC  
 Получает контекст устройства, в данный момент находится в него изображение.  
  
```
HDC GetDC() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для контекста устройства.  
  
### <a name="remarks"></a>Примечания  
 Для каждого вызова `GetDC`, должен иметь следующий вызов [ReleaseDC](#releasedc).  
  
##  <a name="getexporterfilterstring"></a>CImage::GetExporterFilterString  
 Находит доступные форматы изображения для сохранения изображений.  
  
```
static HRESULT GetExporterFilterString(CSimpleString& strExporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultSave,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>Параметры  
 *strExporters*  
 Ссылку на **CSimpleString** объекта. В разделе **примечания** подробнее.  
  
 `aguidFileTypes`  
 Массив идентификаторов GUID, при этом каждый элемент, соответствующий одному из типов файлов в строке. В примере в `pszAllFilesDescription` ниже, `aguidFileTypes`[0] является `GUID_NULL` , а остальные массива располагаются форматов файлов изображений, поддерживаемых текущей операционной системы.  
  
> [!NOTE]
>  Полный список констант см. в разделе **константы формат файла изображения** в [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
 `pszAllFilesDescription`  
 Если этот параметр не **NULL**, строка будет иметь один дополнительный фильтр в начале списка. Этот фильтр будет иметь значение текущей `pszAllFilesDescription` его описание и принимает файлы модуля, поддерживаемых другими экспорта в списке.  
  
 Пример:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Набор битовые флаги, определяющие, какие типы файлов, чтобы исключить из списка. Ниже перечислены допустимые флаги  
  
- **excludeGIF** = 0x01 GIF исключает файлы.  
  
- **excludeBMP** = 0x02 файлы исключает BMP (точечный рисунок Windows).  
  
- **excludeEMF** = 0x04 исключает EMF (Enhanced Metafile) файлы.  
  
- **excludeWMF** = 0x08 файлы исключает WMF (метафайлы Windows).  
  
- **excludeJPEG** = файлы JPEG исключает 0x10.  
  
- **excludePNG** = файлы PNG исключает 0x20.  
  
- **excludeTIFF** = 0x40 исключает TIFF файлы.  
  
- **excludeIcon** = файлы 0x80 исключает ICO (значка Windows).  
  
- **excludeOther** = 0x80000000 исключает любые другие типы файлов, не перечисленные выше.  
  
- **excludeDefaultLoad** = 0 для загрузки всех файлов, типы, включены по умолчанию  
  
- **excludeDefaultSave** = **excludeIcon | excludeEMF | excludeWMF** для сохранения, эти файлы исключаются по умолчанию, поскольку они обычно имеют особые требования.  
  
 `chSeparator`  
 Разделитель, используемый между форматами изображения. В разделе **примечания** подробнее.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
### <a name="remarks"></a>Примечания  
 Результирующая строка формата можно передать вашей MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) форматы объекту предоставлять расширения файлов изображения, доступных в диалоговом окне Сохранить как файл.  
  
 Параметр *strExporter* имеет формат:  
  
 файл description0 | \*.ext0 | filedescription1 | \*.ext1 |... описание файла *n*|\*. ext *n*||  
  
 где "|" знак разделителя задается `chSeparator`. Например:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Разделитель по умолчанию ' |' Если передать эту строку в MFC `CFileDialog` объекта. Используйте null разделитель '\0', если передать эту строку распространенных диалоговому окну сохранения файла.  
  
##  <a name="getheight"></a>CImage::GetHeight  
 Получает высоту в пикселях изображения.  
  
```
int GetHeight() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях изображения.  
  
##  <a name="getimporterfilterstring"></a>CImage::GetImporterFilterString  
 Находит форматы изображений, доступные для загрузки изображения.  
  
```
static HRESULT GetImporterFilterString(CSimpleString& strImporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultLoad,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>Параметры  
 *strImporters*  
 Ссылку на **CSimpleString** объекта. В разделе **примечания** подробнее.  
  
 `aguidFileTypes`  
 Массив идентификаторов GUID, при этом каждый элемент, соответствующий одному из типов файлов в строке. В примере в `pszAllFilesDescription` ниже, `aguidFileTypes`[0] является `GUID_NULL` с массивом остальные значения — форматы файлов изображений, поддерживаемых текущей операционной системы.  
  
> [!NOTE]
>  Полный список констант см. в разделе **константы формат файла изображения** в [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
 `pszAllFilesDescription`  
 Если этот параметр не **NULL**, строка будет иметь один дополнительный фильтр в начале списка. Этот фильтр будет иметь значение текущей `pszAllFilesDescription` его описание и принимает файлы модуля, поддерживаемых другими экспорта в списке.  
  
 Пример:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 Набор битовые флаги, определяющие, какие типы файлов, чтобы исключить из списка. Ниже перечислены допустимые флаги  
  
- **excludeGIF** = 0x01 GIF исключает файлы.  
  
- **excludeBMP** = 0x02 файлы исключает BMP (точечный рисунок Windows).  
  
- **excludeEMF** = 0x04 исключает EMF (Enhanced Metafile) файлы.  
  
- **excludeWMF** = 0x08 файлы исключает WMF (метафайлы Windows).  
  
- **excludeJPEG** = файлы JPEG исключает 0x10.  
  
- **excludePNG** = файлы PNG исключает 0x20.  
  
- **excludeTIFF** = 0x40 исключает TIFF файлы.  
  
- **excludeIcon** = файлы 0x80 исключает ICO (значка Windows).  
  
- **excludeOther** = 0x80000000 исключает любые другие типы файлов, не перечисленные выше.  
  
- **excludeDefaultLoad** = 0 для загрузки всех файлов, типы, включены по умолчанию  
  
- **excludeDefaultSave** = **excludeIcon | excludeEMF | excludeWMF** для сохранения, эти файлы исключаются по умолчанию, поскольку они обычно имеют особые требования.  
  
 `chSeparator`  
 Разделитель, используемый между форматами изображения. В разделе **примечания** подробнее.  
  
### <a name="remarks"></a>Примечания  
 Результирующая строка формата можно передать вашей MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md) объекту предоставлять расширения файлов образа, доступные форматы в **Открытие файла** диалоговое окно.  
  
 Параметр *strImporter* имеет формат:  
  
 файл description0 | \*.ext0 | filedescription1 | \*.ext1 |... описание файла *n*|\*. ext *n*||  
  
 где "|" знак разделителя задается `chSeparator`. Например:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 Разделитель по умолчанию ' |' Если передать эту строку в MFC `CFileDialog` объекта. Используйте null разделитель '\0', если передать эту строку в общий **Открытие файла** диалоговое окно.  
  
##  <a name="getmaxcolortableentries"></a>CImage::GetMaxColorTableEntries  
 Получает максимальное число записей в таблице цветов.  
  
```
int GetMaxColorTableEntries() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество записей в таблице цветов.  
  
### <a name="remarks"></a>Примечания  
 Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="getpitch"></a>CImage::GetPitch  
 Получает высоту изображения.  
  
```
int GetPitch() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота изображения. Если возвращаемое значение является отрицательным, точечный рисунок является DIB снизу вверх, и его источником является левый нижний угол. Если возвращаемое значение будет положительным, растрового изображения DIB сверху вниз и начала координат верхнего левого угла.  
  
### <a name="remarks"></a>Примечания  
 Шаг — это расстояние в байтах между два адреса памяти, представляющие начала одной строки точечного рисунка и в начало следующей строки точечного рисунка. Поскольку тон измеряется в байтах, высота изображения помогает определить формат пикселей. Шаг может также включать дополнительной памяти, зарезервированный для точечного рисунка.  
  
 Используйте `GetPitch` с [GetBits](#getbits) для поиска отдельных точек изображения.  
  
> [!NOTE]
>  Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="getpixel"></a>CImage::GetPixel  
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
 Красный, зеленый, синий (RGB) значение пикселя. Если точка находится за пределами текущей области обрезки, возвращаемое значение не **CLR_INVALID**.  
  
##  <a name="getpixeladdress"></a>CImage::GetPixelAddress  
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
 Адрес определяется согласно координаты точки, голос точечного рисунка и бита на пиксель.  
  
 Для форматов с менее чем 8 битами на пиксел этот метод возвращает адрес байтов, содержащий пикселя. Например, если формат изображения содержит 4 битов на пиксел `GetPixelAddress` возвращает адрес первого пикселя в байт и необходимо вычислить для 2 точки в байте.  
  
> [!NOTE]
>  Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="gettransparentcolor"></a>CImage::GetTransparentColor  
 Извлекает индекс прозрачный цвет в палитре цветов.  
  
```
LONG GetTransparentColor() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс прозрачный цвет.  
  
##  <a name="getwidth"></a>CImage::GetWidth  
 Получает ширину в пикселях изображения.  
  
```
int GetWidth() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ширина растрового изображения в пикселях.  
  
##  <a name="isdibsection"></a>CImage::IsDIBSection  
 Определяет, является ли вложенное растрового изображения DIB раздела.  
  
```
bool IsDIBSection() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если точечный рисунок вложенный раздел DIB. В противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Если точечный рисунок не раздел DIB, нельзя использовать следующие `CImage` методы, которые поддерживают только растровые изображения DIB раздела:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
##  <a name="isindexed"></a>CImage::IsIndexed  
 Определяет, является ли пикселов точечного рисунка сопоставляются с цветовой палитры.  
  
```
bool IsIndexed() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если индексированные; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает **true** только в том случае, если точечный рисунок 8-разрядное (256 цветов) или меньше.  
  
> [!NOTE]
>  Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="isnull"></a>CImage::IsNull  
 Определяет, если точечный рисунок в данный момент загружен.  
  
```
bool IsNull() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает **True** Если точечный рисунок не загружен; в противном случае **False**.  
  
##  <a name="istransparencysupported"></a>CImage::IsTransparencySupported  
 Указывает, поддерживает прозрачными точечными рисунками, скомпилированного для Windows 2000 или более поздней версии приложения.  
  
```
static BOOL IsTransparencySupported() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если текущей платформы поддерживает прозрачность. В противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если возвращаемое значение не равно нулю, а поддерживается прозрачность вызов [AlphaBlend](#alphablend), [TransparentBlt](#transparentblt), или [рисовать](#draw) обрабатывающий прозрачного цвета.  
  
 При компиляции приложения для использования с операционных систем до Windows 2000 или Windows 98, этот метод всегда возвращает значение 0, даже на более новых операционных системах.  
  

##  <a name="load"></a>CImage::Load  
 Загрузка изображения.  
  
```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pszFileName`  
 Указатель на строку, содержащую имя файла образа загрузки.  
  
 `pStream`  
 Указатель на поток, содержащий имя файла образа загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
### <a name="remarks"></a>Примечания  
 Загружает изображение, указанное в *pszFileName* или `pStream`.  
  
 Типы допустимых изображений, BMP, GIF, JPEG, PNG и TIFF.  
  
##  <a name="loadfromresource"></a>CImage::LoadFromResource  
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
  
##  <a name="maskblt"></a>CImage::MaskBlt  
 Объединяет данные о цвете для исходного и конечного точечных рисунков с помощью указанной маске и растровая операция.  
  
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
 Дескриптор модуля, чьи исполняемый файл содержит ресурс.  
  
 `xDest`  
 Координата x, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `yDest`  
 Координата y, в логических единицах верхнего левого угла прямоугольника назначения.  
  
 `nDestWidth`  
 Ширина в логические блоки, прямоугольник и исходный точечный рисунок назначения.  
  
 `nDestHeight`  
 Высота в логические блоки, прямоугольник и исходный точечный рисунок назначения.  
  
 `xSrc`  
 Логическую координату x левого верхнего исходного растрового изображения.  
  
 `ySrc`  
 Логический Координата y верхнего левого угла исходного растрового изображения.  
  
 `hbmMask`  
 Дескриптор точечного рисунка одноцветную маску, в сочетании с битовой карты цвета в контекст исходного устройства.  
  
 `xMask`  
 Смещение в пикселях горизонтальной для маски растровое изображение, указанное в `hbmMask` параметр.  
  
 `yMask`  
 Смещение в пикселях вертикальной для маски растровое изображение, указанное в `hbmMask` параметр.  
  
 `dwROP`  
 Указывает переднего плана и фона коды троичный растровых операций, которые метод использует для управления сочетание исходных и целевых данных. Код операции растрового фона хранится в старший байт из старшее слово этого значения; Код операции растровых переднего плана хранится в младший байт из старшее слово этого значения; младшее слово, это значение игнорируется и должно быть равно нулю. Обсуждение переднего плана и фона в контексте этого метода см. в разделе `MaskBlt` в [!INCLUDE[winSDK](./includes/winsdk_md.md)]. Список общих коды растровых операций см `BitBlt` в [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
 `rectDest`  
 Ссылку на `RECT` структура, определение назначения.  
  
 `pointSrc`  
 A `POINT` структуру указывая верхнем левом углу исходного прямоугольника.  
  
 `pointMask`  
 Объект **ТОЧКИ** структуру указывая верхнем левом углу точечного рисунка маски.  
  
 `pointDest`  
 Ссылку на **ТОЧКИ** структура, определяющая в верхнем левом углу конечного прямоугольника, в логических единицах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод применим к Windows NT версии 4.0 и более поздних версий.  
  
##  <a name="operator_hbitmap"></a>CImage::operator HBITMAP  
 Этот оператор используется получить дескриптор вложенного Windows GDI `CImage` объекта. Этот оператор — оператор приведения, который поддерживает непосредственное использование `HBITMAP` объекта.  
  
##  <a name="plgblt"></a>CImage::PlgBlt  
 Выполняет перемещение набора битов с прямоугольник в контекста исходного устройства в параллелограмм, в контексте устройства назначения.  
  
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
 Указатель на массив из трех точек логического пространства, определяющие трех углов конечного параллелограмма. Первая точка в этот массив, правого верхнего угла до второй точки в этом массиве и правом нижнем углу в третью точку сопоставляется верхнем левом углу исходного прямоугольника. Четвертый неявные точки параллелограмма сопоставляется в правом нижнем углу исходного прямоугольника.  
  
 `hbmMask`  
 Дескриптор Дополнительно монохромный точечный рисунок, используемый для маскировки цвета исходного прямоугольника.  
  
 `xSrc`  
 Координата x, в логических единицах верхнем левом углу исходного прямоугольника.  
  
 `ySrc`  
 Координата y, в логических единицах верхнем левом углу исходного прямоугольника.  
  
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
 Объект [ТОЧКИ](http://msdn.microsoft.com/library/windows/desktop/dd162805) структуру указывая верхнем левом углу точечного рисунка маски.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `hbmMask` определяет допустимые монохромный точечный рисунок, **PlgBit** использует этот рисунок в маске биты данных о цвете из исходного прямоугольника.  
  
 Этот метод применим к Windows NT версии 4.0 и более поздних версий. В разделе [PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804) в [!INCLUDE[winSDK](./includes/winsdk_md.md)] более подробные сведения.  
  
##  <a name="releasedc"></a>CImage::ReleaseDC  
 Освобождает контекст устройства.  
  
```
void ReleaseDC() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку можно выбрать только одно растровое изображение в контексте устройства одновременно, необходимо вызвать `ReleaseDC` для каждого вызова [GetDC](#getdc).  
  
##  <a name="releasegdiplus"></a>CImage::ReleaseGDIPlus  
 Освобождает ресурсы, используемые GDI +.  
  
```
void ReleaseGDIPlus() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться для освобождения ресурсов, выделенных в глобальный `CImage` объекта. В разделе [CImage::CImage](#cimage).  
  
##  <a name="save"></a>CImage::Save  
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
  
- **ImageFormatBMP** несжатый растрового изображения.  
  
- **ImageFormatPNG** сжатый образ переносимой сетевой графики (PNG).  
  
- **ImageFormatJPEG** сжатые в формате JPEG.  
  
- **ImageFormatGIF** GIF сжатого образа.  
  
> [!NOTE]
>  Полный список констант см. в разделе **константы формат файла изображения** в [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для сохранения изображения, с помощью указанного имени и типа. Если `guidFileType` параметр не указан, расширение имени файла будет использоваться для определения формата изображения. Если расширение не указано, изображение будет сохранено в формате BMP.  
  
##  <a name="setcolortable"></a>CImage::SetColorTable  
 Задает значения цвета красный, зеленый, синий (RGB) для диапазона записей в палитре в разделе DIB.  
  
```
void SetColorTable(
  UINT iFirstColor, 
  UINT nColors,
  const RGBQUAD* prgbColors) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `iFirstColor`  
 Цвет таблицы индекс первой записи.  
  
 `nColors`  
 Количество записей таблицы цветов для задания.  
  
 `prgbColors`  
 Указатель на массив [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) структуры, чтобы задать цвет таблицы записей.  
  
### <a name="remarks"></a>Примечания  
 Этот метод поддерживает только растровые изображения DIB раздела.  
  
##  <a name="setpixel"></a>CImage::SetPixel  
 Задает цвет пикселя в заданную позицию в точечном рисунке.  
  
```
void SetPixel(int x, int y, COLORREF color) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Горизонтальное расположение устанавливаемого пиксела.  
  
 *y*  
 Вертикальное расположение устанавливаемого пиксела.  
  
 `color`  
 Цвет, который назначен пикселя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняется, если лежит за пределами области отсечения выбранного координаты пикселя.  
  
##  <a name="setpixelindexed"></a>CImage::SetPixelIndexed  
 Задает цвет пикселя в цвет, расположенный в `iIndex` в цветовой палитре.  
  
```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Горизонтальное расположение устанавливаемого пиксела.  
  
 *y*  
 Вертикальное расположение устанавливаемого пиксела.  
  
 `iIndex`  
 Индекс цвета в цветовой палитре.  
  
##  <a name="setpixelrgb"></a>CImage::SetPixelRGB  
 Задает пикселя в расположениях, указанных в *x* и *y* цветами, обозначенными *r*, *g*, и *b*, в красный, зеленый, синий изображение (RGB).  
  
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
 Горизонтальное расположение устанавливаемого пиксела.  
  
 *y*  
 Вертикальное расположение устанавливаемого пиксела.  
  
 *r*  
 Интенсивность красного цвета.  
  
 *g*  
 Интенсивность зеленого цвета.  
  
 *b*  
 Интенсивность синий цвет.  
  
### <a name="remarks"></a>Примечания  
 Параметры красного, зеленого и синего представляются число от 0 до 255. Если все три параметра задать значение&0;, объединенный итоговый цвет будет черным. Если все три параметра равным 255, объединенный итоговый цвет белый.  
  
##  <a name="settransparentcolor"></a>CImage::SetTransparentColor  
 Задает цвет в заданную позицию индексированных как прозрачный.  
  
```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *iTransparentColor*  
 Индекс в цветовой палитре, задайте для прозрачного цвета. Если-1, то цвет не присваивается прозрачным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс цвета ранее набора как прозрачный.  
  
##  <a name="stretchblt"></a>CImage::StretchBlt  
 Копирует точечный рисунок из исходного контекста устройства это текущий контекст устройства.  
  
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
 Выполняемая операция растровые. Коды растровых операций определяют, как будут объединены биты источника, назначения и шаблон (в соответствии с выбранной кисти) назначения. В разделе [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) в [!INCLUDE[winSDK](./includes/winsdk_md.md)] список другие коды растровых операций и их описания.  
  
 `rectDest`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, определение назначения.  
  
 `xSrc`  
 Координата x, в логических единицах верхнем левом углу исходного прямоугольника.  
  
 `ySrc`  
 Координата y, в логических единицах верхнем левом углу исходного прямоугольника.  
  
 `nSrcWidth`  
 Ширина в логических единицах исходного прямоугольника.  
  
 `nSrcHeight`  
 Высота в логических единицах исходного прямоугольника.  
  
 `rectSrc`  
 Ссылку на `RECT` структура, определение источника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120) в [!INCLUDE[winSDK](./includes/winsdk_md.md)].  
  
##  <a name="transparentblt"></a>CImage::TransparentBlt  
 Копирует точечный рисунок из исходного контекста устройства это текущий контекст устройства.  
  
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
 В исходный точечный рисунок должен рассматриваться как прозрачный цвет. По умолчанию **CLR_INVALID**, указывающее, что следует использовать цвет, установленный как прозрачный цвет изображения.  
  
 `rectDest`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, определение назначения.  
  
 `xSrc`  
 Координата x, в логических единицах верхнем левом углу исходного прямоугольника.  
  
 `ySrc`  
 Координата y, в логических единицах верхнем левом углу исходного прямоугольника.  
  
 `nSrcWidth`  
 Ширина в логических единицах исходного прямоугольника.  
  
 `nSrcHeight`  
 Высота в логических единицах исходного прямоугольника.  
  
 `rectSrc`  
 Ссылку на `RECT` структура, определение источника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** в случае успешного выполнения, в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 `TransparentBlt`поддерживается для точечных рисунков источника 4 битов на пиксел и 8 бит на пиксел. Используйте [CImage::AlphaBlend](#alphablend) указание 32 бита на пиксель растровые изображения с прозрачностью.  
  
  
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
 [Компоненты COM Desktop ATL](../../atl/atl-com-desktop-components.md)
 [аппаратно независимые точечные рисунки](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   










