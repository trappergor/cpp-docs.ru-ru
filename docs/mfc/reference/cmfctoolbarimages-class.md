---
title: "CMFCToolBarImages Class | Microsoft Docs"
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
  - "CMFCToolBarImages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarImages class"
ms.assetid: d4e50518-9ffc-406f-9996-f79e5cd38155
caps.latest.revision: 31
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarImages Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Образы на панели инструментов.  Класс `CMFCToolBarImages` управляет образы панели инструментов, загруженные из ресурса приложения или из файлов.  
  
## Синтаксис  
  
```  
class CMFCToolBarImages : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarImages::CMFCToolBarImages](../Topic/CMFCToolBarImages::CMFCToolBarImages.md)|Создает объект `CMFCToolBarImages`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarImages::AdaptColors](../Topic/CMFCToolBarImages::AdaptColors.md)||  
|[CMFCToolBarImages::AddIcon](../Topic/CMFCToolBarImages::AddIcon.md)|Добавляет значок образам панели инструментов.|  
|[CMFCToolBarImages::AddImage](../Topic/CMFCToolBarImages::AddImage.md)|Добавляет растровое изображение в образам панели инструментов.|  
|[CMFCToolBarImages::CleanUp](../Topic/CMFCToolBarImages::CleanUp.md)||  
|[CMFCToolBarImages::Clear](../Topic/CMFCToolBarImages::Clear.md)|Освобождает ресурсы системы, которые были выделены к данному объекту.|  
|[CMFCToolBarImages::ConvertTo32Bits](../Topic/CMFCToolBarImages::ConvertTo32Bits.md)|Новообращенные подчеркнули растровые изображения до 32 образа bpp.|  
|[CMFCToolBarImages::CopyImageToClipboard](../Topic/CMFCToolBarImages::CopyImageToClipboard.md)||  
|[CMFCToolBarImages::CopyTo](../Topic/CMFCToolBarImages::CopyTo.md)||  
|[CMFCToolBarImages::CreateFromImageList](../Topic/CMFCToolBarImages::CreateFromImageList.md)|Инициализирует образы панели инструментов из списка образа \([CImageList Class](../Topic/CImageList%20Class.md)\).|  
|[CMFCToolBarImages::CreateRegionFromImage](../Topic/CMFCToolBarImages::CreateRegionFromImage.md)||  
|[CMFCToolBarImages::DeleteImage](../Topic/CMFCToolBarImages::DeleteImage.md)|Удаляет образ, имеющий указанный индекс из изображений панели инструментов, если данный набор изображений панели инструментов содержит определяемые пользователем изображений.|  
|[CMFCToolBarImages::Draw](../Topic/CMFCToolBarImages::Draw.md)|Рисует один способ панели инструментов \(кнопка\).|  
|[CMFCToolBarImages::DrawEx](../Topic/CMFCToolBarImages::DrawEx.md)||  
|[CMFCToolBarImages::EnableRTL](../Topic/CMFCToolBarImages::EnableRTL.md)||  
|[CMFCToolBarImages::EndDrawImage](../Topic/CMFCToolBarImages::EndDrawImage.md)|Системные ресурсы свободенов после завершения образа панели инструментов нарисована.|  
|[CMFCToolBarImages::ExtractIcon](../Topic/CMFCToolBarImages::ExtractIcon.md)|Возвращает значок, который содержит указанный индекс образа из изображений панели инструментов.|  
|[CMFCToolBarImages::FillDitheredRect](../Topic/CMFCToolBarImages::FillDitheredRect.md)|Выполняет заливку прямоугольника с помощью кисти с цветом фона панели инструментов.|  
|[CMFCToolBarImages::GetAlwaysLight](../Topic/CMFCToolBarImages::GetAlwaysLight.md)||  
|[CMFCToolBarImages::GetBitsPerPixel](../Topic/CMFCToolBarImages::GetBitsPerPixel.md)|Возвращает текущее разрешение подчеркнутых изображений.|  
|[CMFCToolBarImages::GetCount](../Topic/CMFCToolBarImages::GetCount.md)|Возвращает количество изображений на панели инструментов.|  
|[CMFCToolBarImages::GetDisabledImageAlpha](../Topic/CMFCToolBarImages::GetDisabledImageAlpha.md)|Возвращает значение альфа\-канала, используемое для отключенных изображений.|  
|[CMFCToolBarImages::GetFadedImageAlpha](../Topic/CMFCToolBarImages::GetFadedImageAlpha.md)||  
|[CMFCToolBarImages::GetImageSize](../Topic/CMFCToolBarImages::GetImageSize.md)|Извлекает то размер изображений панели инструментов, которые хранятся в памяти \(размера источника\) или размер изображений панели инструментов, нарисована на экране \(размере назначения\).|  
|[CMFCToolBarImages::GetImageWell](../Topic/CMFCToolBarImages::GetImageWell.md)|Возвращает дескриптор растровое изображение, содержащий все образы панели инструментов.|  
|[CMFCToolBarImages::GetImageWellLight](../Topic/CMFCToolBarImages::GetImageWellLight.md)||  
|[CMFCToolBarImages::GetLastImageRect](../Topic/CMFCToolBarImages::GetLastImageRect.md)||  
|[CMFCToolBarImages::GetLightPercentage](../Topic/CMFCToolBarImages::GetLightPercentage.md)||  
|[CMFCToolBarImages::GetMapTo3DColors](../Topic/CMFCToolBarImages::GetMapTo3DColors.md)||  
|[CMFCToolBarImages::GetMask](../Topic/CMFCToolBarImages::GetMask.md)||  
|[CMFCToolBarImages::GetResourceOffset](../Topic/CMFCToolBarImages::GetResourceOffset.md)|Возвращает индекс образа для указанного идентификатора ресурса|  
|[CMFCToolBarImages::GetScale](../Topic/CMFCToolBarImages::GetScale.md)|Коэффициент масштабирования возвращений текущий подчеркнутых изображений.|  
|[CMFCToolBarImages::GetTransparentColor](../Topic/CMFCToolBarImages::GetTransparentColor.md)||  
|[CMFCToolBarImages::GrayImages](../Topic/CMFCToolBarImages::GrayImages.md)|Серые цвета образы панели инструментов, чтобы их выглядеть отключенный.|  
|[CMFCToolBarImages::Is32BitTransparencySupported](../Topic/CMFCToolBarImages::Is32BitTransparencySupported.md)|Определяет, поддерживает ли операционная система 32 разрядное альфа\-смешение.|  
|[CMFCToolBarImages::IsPreMultiplyAutoCheck](../Topic/CMFCToolBarImages::IsPreMultiplyAutoCheck.md)||  
|[CMFCToolBarImages::IsRTL](../Topic/CMFCToolBarImages::IsRTL.md)|Определяет, включена ли поддержка справа налево \(с написанием справа налево\).|  
|[CMFCToolBarImages::IsReadOnly](../Topic/CMFCToolBarImages::IsReadOnly.md)|Определяет, является ли образы панели инструментов только для чтения.|  
|[CMFCToolBarImages::IsScaled](../Topic/CMFCToolBarImages::IsScaled.md)|Указывает, является ли масштабироватьы подчеркнутые изображений или нет.|  
|[CMFCToolBarImages::IsUserImagesList](../Topic/CMFCToolBarImages::IsUserImagesList.md)|Указывает, содержит ли этот набор изображений панели инструментов определяемые пользователем изображений.|  
|[CMFCToolBarImages::IsValid](../Topic/CMFCToolBarImages::IsValid.md)|Указывает, содержит ли этот набор изображений панели инструментов допустимое изображение панели инструментов.|  
|[CMFCToolBarImages::Load](../Topic/CMFCToolBarImages::Load.md)|Образы панели инструментов загрузок из системных ресурсов или из файла.|  
|[CMFCToolBarImages::LoadStr](../Topic/CMFCToolBarImages::LoadStr.md)||  
|[CMFCToolBarImages::MapFromSysColor](../Topic/CMFCToolBarImages::MapFromSysColor.md)||  
|[CMFCToolBarImages::MapTo3dColors](../Topic/CMFCToolBarImages::MapTo3dColors.md)||  
|[CMFCToolBarImages::MapToSysColor](../Topic/CMFCToolBarImages::MapToSysColor.md)||  
|[CMFCToolBarImages::MapToSysColorAlpha](../Topic/CMFCToolBarImages::MapToSysColorAlpha.md)||  
|[CMFCToolBarImages::Mirror](../Topic/CMFCToolBarImages::Mirror.md)|Горизонтальное отражает все образы панели инструментов.|  
|[CMFCToolBarImages::MirrorBitmap](../Topic/CMFCToolBarImages::MirrorBitmap.md)|Горизонтальное отражает растровое изображение.|  
|[CMFCToolBarImages::MirrorBitmapVert](../Topic/CMFCToolBarImages::MirrorBitmapVert.md)||  
|[CMFCToolBarImages::MirrorVert](../Topic/CMFCToolBarImages::MirrorVert.md)||  
|[CMFCToolBarImages::OnSysColorChange](../Topic/CMFCToolBarImages::OnSysColorChange.md)||  
|[CMFCToolBarImages::PrepareDrawImage](../Topic/CMFCToolBarImages::PrepareDrawImage.md)|Выбирает ресурсы, необходимые для выпишут изображение панели инструментов для заданного размера.|  
|[CMFCToolBarImages::Save](../Topic/CMFCToolBarImages::Save.md)|Хранит образы панели инструментов в файле, если данный набор изображений панели инструментов содержит определяемые пользователем изображений.|  
|[CMFCToolBarImages::SetAlwaysLight](../Topic/CMFCToolBarImages::SetAlwaysLight.md)||  
|[CMFCToolBarImages::SetDisabledImageAlpha](../Topic/CMFCToolBarImages::SetDisabledImageAlpha.md)|Задает значение альфа\-канала, используемое для отключенных изображений.|  
|[CMFCToolBarImages::SetFadedImageAlpha](../Topic/CMFCToolBarImages::SetFadedImageAlpha.md)||  
|[CMFCToolBarImages::SetImageSize](../Topic/CMFCToolBarImages::SetImageSize.md)|Задает размер образа панели инструментов \(размера источника\).|  
|[CMFCToolBarImages::SetLightPercentage](../Topic/CMFCToolBarImages::SetLightPercentage.md)||  
|[CMFCToolBarImages::SetMapTo3DColors](../Topic/CMFCToolBarImages::SetMapTo3DColors.md)||  
|[CMFCToolBarImages::SetPreMultiplyAutoCheck](../Topic/CMFCToolBarImages::SetPreMultiplyAutoCheck.md)||  
|[CMFCToolBarImages::SetSingleImage](../Topic/CMFCToolBarImages::SetSingleImage.md)||  
|[CMFCToolBarImages::SetTransparentColor](../Topic/CMFCToolBarImages::SetTransparentColor.md)|Устанавливает прозрачный цвет образов панели инструментов.|  
|[CMFCToolBarImages::SmoothResize](../Topic/CMFCToolBarImages::SmoothResize.md)|Четным размеры подчеркнули изображений.|  
|[CMFCToolBarImages::UpdateImage](../Topic/CMFCToolBarImages::UpdateImage.md)|Обновляет определяемый пользователем образ панели инструментов из растрового изображения.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarImages::PreMultiplyAlpha](../Topic/CMFCToolBarImages::PreMultiplyAlpha.md)||  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarImages::m\_bDisableTrueColorAlpha](../Topic/CMFCToolBarImages::m_bDisableTrueColorAlpha.md)|`TRUE` если truecolor альфа\-смешение \(32\-разрядный цвет\) отключен.|  
  
## Заметки  
 Полное растровое изображение панели инструментов образов управляемых `CMFCToolbarImages` состоит из одного или более мелких изображений кнопок панели инструментов \(\) фиксированного размера.  
  
## Пример  
 В следующем примере показано, как настроить объект `CMFCToolBarImages` с помощью различных методов в классе `CMFCToolBarImages`.  Примере показано, как задать размер образа панели инструментов, загрузки образа и укажите прозрачный цвет образа.  Этот фрагмент кода является частью [Пример demo Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#32](../../mfc/reference/codesnippet/CPP/cmfctoolbarimages-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#33](../../mfc/reference/codesnippet/CPP/cmfctoolbarimages-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md)  
  
## Требования  
 **заголовок:** afxtoolbarimages.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)