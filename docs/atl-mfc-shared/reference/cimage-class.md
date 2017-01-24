---
title: "CImage Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CImage"
  - "ATL.CImage"
  - "ATL::CImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GIF-файлы, ATL and MFC support"
  - "растровые изображения [C++], ATL and MFC support for"
  - "CImage class"
  - "GIF-файлы, ATL and MFC support"
  - "изображения [C++], ATL and MFC support for"
  - "JPEG-файлы"
  - "PNG-файлы, ATL and MFC support"
  - "transparent color"
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
caps.latest.revision: 20
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CImage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CImage` обеспечивает поддержку растрового изображения, включая возможность загрузки и сохранения изображений в BMP, JPEG, GIF и PNG \(PNG форматах\).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CImage  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CImage::CImage](../Topic/CImage::CImage.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CImage::AlphaBlend](../Topic/CImage::AlphaBlend.md)|Указывает растровые изображения, имеющих прозрачные и полупрозрачных точки.|  
|[CImage::Attach](../Topic/CImage::Attach.md)|Вложение `HBITMAP` к объекту `CImage`.  Может использоваться с растровыми изображениями растровых изображений раздела non\-DIB или раздела DIB.|  
|[CImage::BitBlt](../Topic/CImage::BitBlt.md)|Копирует растровое изображение из контекста устройства источника к этому текущий контекст устройства.|  
|[CImage::Create](../Topic/CImage::Create.md)|Создает растровое изображение раздела DIB и вложение его на ранее созданный объект `CImage`.|  
|[CImage::CreateEx](../Topic/CImage::CreateEx.md)|Создает растровое изображение раздела DIB \(с дополнительными параметрами\) и привязывает его на ранее созданный объект `CImage`.|  
|[CImage::Destroy](../Topic/CImage::Destroy.md)|Наконец удаляет растровое изображение из объекта `CImage` и уничтожает растровое изображение.|  
|[CImage::Detach](../Topic/CImage::Detach.md)|Наконец удаляет растровое изображение из объекта `CImage`.|  
|[CImage::Draw](../Topic/CImage::Draw.md)|Копирует растровое изображение из прямоугольника источника в прямоугольник назначения.  **Ничья** растянет или сжимает растровое изображение для приспособления измерений прямоугольника назначения, если необходимый и обрабатывает альфа\-смешения и прозрачного цвета.|  
|[CImage::GetBits](../Topic/CImage::GetBits.md)|Извлекает указатель на фактические значения пикселей растрового изображения.|  
|[CImage::GetBPP](../Topic/CImage::GetBPP.md)|Извлекает бит на точку.|  
|[CImage::GetColorTable](../Topic/CImage::GetColorTable.md)|Извлекает красного, зеленого и синего \(RGB\) из диапазона записей таблицы цветов.|  
|[CImage::GetDC](../Topic/CImage::GetDC.md)|Получает контекст устройства, в котором текущее растровое изображение выделен.|  
|[CImage::GetExporterFilterString](../Topic/CImage::GetExporterFilterString.md)|Находит доступные форматы изображения и их описания.|  
|[CImage::GetHeight](../Topic/CImage::GetHeight.md)|Получает высоту текущего изображения в пикселях.|  
|[CImage::GetImporterFilterString](../Topic/CImage::GetImporterFilterString.md)|Находит доступные форматы изображения и их описания.|  
|[CImage::GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)|Получает максимальное количество записей в таблице цвета.|  
|[CImage::GetPitch](../Topic/CImage::GetPitch.md)|Получает шаг шрифта текущего изображения в байтах.|  
|[CImage::GetPixel](../Topic/CImage::GetPixel.md)|Получает цвет пикселя заданного *x* и *Y.*|  
|[CImage::GetPixelAddress](../Topic/CImage::GetPixelAddress.md)|Получает адрес заданного в пикселях.|  
|[CImage::GetTransparentColor](../Topic/CImage::GetTransparentColor.md)|Получает положение прозрачного цветов в таблице цвета.|  
|[CImage::GetWidth](../Topic/CImage::GetWidth.md)|Получает ширину текущего изображения в пикселях.|  
|[CImage::IsDIBSection](../Topic/CImage::IsDIBSection.md)|Определяет, является ли вложенное растровое изображение раздел DIB.|  
|[CImage::IsIndexed](../Topic/CImage::IsIndexed.md)|Указывает, что цвета растрового изображения в индексированной сопоставлены палитры.|  
|[CImage::IsNull](../Topic/CImage::IsNull.md)|Указывает, является ли растровое изображение источника в данный момент загружен.|  
|[CImage::IsTransparencySupported](../Topic/CImage::IsTransparencySupported.md)|Указывает, поддерживает ли приложение прозрачные растровые изображения и компилировать для Windows 2000 или более поздней версии.|  
|[CImage::Load](../Topic/CImage::Load.md)|Загружает образ из указанного файла.|  
|[CImage::LoadFromResource](../Topic/CImage::LoadFromResource.md)|Загружает образ из заданного ресурса.|  
|[CImage::MaskBlt](../Topic/CImage::MaskBlt.md)|Объединяет данные о цвете для растровых изображений источника и назначения, используя указанную операцию и маски растровый.|  
|[CImage::PlgBlt](../Topic/CImage::PlgBlt.md)|Выполняет передачу бит\- блока из прямоугольника в контексте устройства источника в параллелограмм в контексте устройства назначения.|  
|[CImage::ReleaseDC](../Topic/CImage::ReleaseDC.md)|Освобождает контекст устройства, который был получить с [CImage::GetDC](../Topic/CImage::GetDC.md).|  
|[CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md)|Освобождает ресурсы, используемые GDI\+.  Быть вызываются для освобождения ресурсов, созданные глобальным объектом `CImage`.|  
|[CImage::Save](../Topic/CImage::Save.md)|Сохраняет изображение как значение указанного типа.  **Сохранить** не может определить параметры образа.|  
|[CImage::SetColorTable](../Topic/CImage::SetColorTable.md)|Устанавливает красного, зеленого и синего цвета RGB\) в диапазоне записей в таблице цветов раздела DIB.|  
|[CImage::SetPixel](../Topic/CImage::SetPixel.md)|Устанавливает точку на указанные координаты в указанный цвет.|  
|[CImage::SetPixelIndexed](../Topic/CImage::SetPixelIndexed.md)|Устанавливает точку на указанные координаты к цвету палитры по указанному индексу.|  
|[CImage::SetPixelRGB](../Topic/CImage::SetPixelRGB.md)|Устанавливает точку на указанные координаты к определенному красный, зеленого, голубому значение \(RGB\).|  
|[CImage::SetTransparentColor](../Topic/CImage::SetTransparentColor.md)|Устанавливает индекс цвета, который должен рассматриваться как прозрачный.  Только один цвет в палитре может быть прозрачным.|  
|[CImage::StretchBlt](../Topic/CImage::StretchBlt.md)|Копирует растровое изображение из прямоугольника источника в прямоугольник назначения, растянуть или сжать растровое изображение для приспособления измерений прямоугольника назначения, если требуемый.|  
|[CImage::TransparentBlt](../Topic/CImage::TransparentBlt.md)|Копирует растровое изображение с прозрачный цвет из контекста устройства источника к этому текущий контекст устройства.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CImage::operator HBITMAP](../Topic/CImage::operator%20HBITMAP.md)|Возвращает вложенный маркер Windows на объект `CImage`.|  
  
## Заметки  
 `CImage` принимает растровые изображения или разделы файла DIB \(DIB\) или нет. однако можно использовать [Создание](../Topic/CImage::Create.md) или [CImage::Load](../Topic/CImage::Load.md) только с разделами DIB.  Можно вложить растровое изображение раздела non\-DIB к объекту `CImage` с помощью [Вложение](../Topic/CImage::Attach.md), но с другой стороны, нельзя использовать следующие методы `CImage`, которые поддерживают только растровые изображения DIB раздела:  
  
-   [GetBits](../Topic/CImage::GetBits.md)  
  
-   [GetColorTable](../Topic/CImage::GetColorTable.md)  
  
-   [GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)  
  
-   [GetPitch](../Topic/CImage::GetPitch.md)  
  
-   [GetPixelAddress](../Topic/CImage::GetPixelAddress.md)  
  
-   [IsIndexed](../Topic/CImage::IsIndexed.md)  
  
-   [SetColorTable](../Topic/CImage::SetColorTable.md)  
  
 Для определения, является ли вложенное растровое изображение раздел, DIB, вызовите [IsDibSection](../Topic/CImage::IsDIBSection.md)**.**  
  
> [!NOTE]
>  **Примечание**  В Visual Studio .NET 2003, этот класс содержит количество объектов `CImage` созданный.  , Если счетчик становится равным 0, функция [GdiplusShutdown](_gdiplus_func_gdiplusshutdown_) автоматически называется для освобождения ресурсов, используемых GDI\+.  Это гарантирует, что все объекты, созданные `CImage` прямо или косвенно библиотеки DLL всегда уничтожены указано правильно и что **GdiplusShutdown** не вызываются из `DllMain`.  
  
> [!NOTE]
>  С помощью глобальной `CImage` не рекомендуется использовать объекты из библиотеки DLL.  Если необходимо использовать глобальный объект `CImage` в dll\-библиотеке, вызовите [CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md), чтобы явно освобождение ресурсов, используемых GDI\+.  
  
 `CImage` не могут быть выбраны в новое [CDC](../Topic/CDC%20Class.md).  `CImage` создать собственное **HDC** для образа.  Поскольку `HBITMAP` можно выбрать только один раз в **HDC**`HBITMAP`, связанное с `CImage` не могут быть выбраны в другое **HDC**.  Если необходимо `CDC`, то восстановление **HDC** из `CImage` и присвойте ему значение [CDC::FromHandle](../Topic/CDC::FromHandle.md).  
  
## Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#70](../../atl-mfc-shared/codesnippet/CPP/cimage-class_1.cpp)]  
  
 При использовании `CImage` в проекте MFC, обратите внимание, функции\-члены в проекте ожидающие указатель на объект [CBitmap](../../mfc/reference/cbitmap-class.md).  Если нужно использовать `CImage` с такой функции, как [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md), используйте [CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md), передав ему в `CImage``HBITMAP` и использовать возвращаемое `CBitmap*`.  
  
## Пример  
 [!code-cpp[NVC_ATLMFC_Utilities#71](../../atl-mfc-shared/codesnippet/CPP/cimage-class_2.cpp)]  
  
 С помощью `CImage`, имеется доступ к реальным битам раздела DIB.  Можно использовать объект `CImage` везде, где ранее использовать раздел Win32 HBITMAP или DIB.  
  
> [!NOTE]
>  Следующие методы `CImage` имеют ограничения на их использование.  
  
|Метод|Ограничение|  
|-----------|-----------------|  
|[PlgBlt](../Topic/CImage::PlgBlt.md)|Рабочие только с Windows NT 4.0 или более поздней версии.  В приложениях не работать под управлением Windows 95, \/98 или более поздней версии.|  
|[MaskBlt](../Topic/CImage::MaskBlt.md)|Рабочие только с Windows NT 4.0 или более поздней версии.  В приложениях не работать под управлением Windows 95, \/98 или более поздней версии.|  
|[AlphaBlend](../Topic/CImage::AlphaBlend.md)|Рабочие только с Windows 2000, Windows 98 и более последним системами.|  
|[TransparentBlt](../Topic/CImage::TransparentBlt.md)|Рабочие только с Windows 2000, Windows 98 и более последним системами.|  
|[Рисование](../Topic/CImage::Draw.md)|Поддерживает прозрачность только с Windows 2000, Windows 98 и более последним системами.|  
  
 См. раздел [Ограничения CImage с более ранними операционными системами](../../mfc/cimage-limitations-with-earlier-operating-systems.md) дополнительные сведения об ограничениях на этих методах.  
  
 Можно использовать `CImage` из MFC и библиотеки ATL.  
  
> [!NOTE]
>  При создании проекта с помощью `CImage` необходимо указать `CString` прежде чем включать `atlimage.h`.  Если в проекте используется библиотека ATL без MFC, включите `atlstr.h` прежде чем включать `atlimage.h`.  Если в проекте используется MFC \(или если проект библиотеки ATL с поддержкой MFC\), включайте `afxstr.h` прежде чем включать `atlimage.h`.  
>   
>  Кроме того, необходимо включить `atlimage.h` прежде чем включать `atlimpl.cpp`.  Для выполнения этого легко включить `atlimage.h` в `stdafx.h`.  
  
## Требования  
 **Header:**  atlimage.h  
  
## См. также  
 [Образец MMXSwarm](../../top/visual-cpp-samples.md)   
 [Образец SimpleImage](../../top/visual-cpp-samples.md)   
 [Device\-Independent Bitmaps](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)