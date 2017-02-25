---
title: "CDrawingManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDrawingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDrawingManager class"
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CDrawingManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CDrawingManager` реализует сложные алгоритмы документа.  
  
## Синтаксис  
  
```  
class CDrawingManager : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDrawingManager::CDrawingManager](../Topic/CDrawingManager::CDrawingManager.md)|Создает объект `CDrawingManager`.|  
|`CDrawingManager::~CDrawingManager`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDrawingManager::CreateBitmap\_32](../Topic/CDrawingManager::CreateBitmap_32.md)|Создает 32 разрядное файла DIB \(DIB\), приложения могут записывать в напрямую.|  
|[CDrawingManager::DrawAlpha](../Topic/CDrawingManager::DrawAlpha.md)|Указывает растровые изображения, имеющих прозрачные и полупрозрачных точки.|  
|[CDrawingManager::DrawRotated](../Topic/CDrawingManager::DrawRotated.md)|Выполняет циклический сдвиг внутри содержимого контроллера домена источника заданный прямоугольник \+\/\- 90 градусами|  
|[CDrawingManager::DrawEllipse](../Topic/CDrawingManager::DrawEllipse.md)|Рисует эллипс с предоставленными цветами заливки и границы.|  
|[CDrawingManager::DrawGradientRing](../Topic/CDrawingManager::DrawGradientRing.md)|Рисует вызов и заполняет его с цветным градиентом.|  
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](../Topic/CDrawingManager::DrawLine,%20CDrawingManager::DrawLineA.md)|Рисуется линия.|  
|[CDrawingManager::DrawRect](../Topic/CDrawingManager::DrawRect.md)|Рисует прямоугольник с предоставленными цветами заливки и границы.|  
|[CDrawingManager::DrawShadow](../Topic/CDrawingManager::DrawShadow.md)|Рисует тень для прямоугольной области.|  
|[CDrawingManager::Fill4ColorsGradient](../Topic/CDrawingManager::Fill4ColorsGradient.md)|Заполнить прямоугольную область с 2 градиентом цвета.|  
|[CDrawingManager::FillGradient](../Topic/CDrawingManager::FillGradient.md)|Заполнить прямоугольную область с указанным цветным градиентом.|  
|[CDrawingManager::FillGradient2](../Topic/CDrawingManager::FillGradient2.md)|Заполнить прямоугольную область с указанным цветным градиентом.  Направление изменения цвета градиента также задан.|  
|[CDrawingManager::GrayRect](../Topic/CDrawingManager::GrayRect.md)|Выполняет заливку прямоугольника с указанным серым цветом.|  
|[CDrawingManager::HighlightRect](../Topic/CDrawingManager::HighlightRect.md)|Выбирает прямоугольная область.|  
|[CDrawingManager::HLStoRGB\_ONE](../Topic/CDrawingManager::HLStoRGB_ONE.md)|Преобразует цвет из представления HLS к представлению RGB.|  
|[CDrawingManager::HLStoRGB\_TWO](../Topic/CDrawingManager::HLStoRGB_TWO.md)|Преобразует цвет из представления HLS к представлению RGB.|  
|[CDrawingManager::HSVtoRGB](../Topic/CDrawingManager::HSVtoRGB.md)|Преобразует цвет из представления HSV к представлению RGB.|  
|[CDrawingManager::HuetoRGB](../Topic/CDrawingManager::HuetoRGB.md)|Вспомогательный метод, который выполняет преобразование значение оттенка в красный, зеленого и голубому компоненту.|  
|[CDrawingManager::MirrorRect](../Topic/CDrawingManager::MirrorRect.md)|Перевернет прямоугольная область.|  
|[CDrawingManager::PixelAlpha](../Topic/CDrawingManager::PixelAlpha.md)|Вспомогательный метод, который задает конечный цвет пикселя semitransparent.|  
|[CDrawingManager::PrepareShadowMask](../Topic/CDrawingManager::PrepareShadowMask.md)|Создает растровое изображение, которое может использоваться как тень.|  
|[CDrawingManager::RGBtoHSL](../Topic/CDrawingManager::RGBtoHSL.md)|Преобразует цвет из представления RGB к представлению HSL.|  
|[CDrawingManager::RGBtoHSV](../Topic/CDrawingManager::RGBtoHSV.md)|Преобразует цвет из представления RGB в представление HSV.|  
|[CDrawingManager::SetAlphaPixel](../Topic/CDrawingManager::SetAlphaPixel.md)|Вспомогательный метод, который рисует частично прозрачными пиксель в растровом изображении.|  
|[CDrawingManager::SetPixel](../Topic/CDrawingManager::SetPixel.md)|Вспомогательный метод, который изменяет один пиксель в растровом изображении в указанный цвет.|  
|[CDrawingManager::SmartMixColors](../Topic/CDrawingManager::SmartMixColors.md)|Зернокомбайны 2 цветов, основываясь на коэффициенте взвешенного.|  
  
## Заметки  
 Класс `CDrawingManager` предоставляет функции для отрисовки тени градиент цвета и выбранные прямоугольники.  Он также выполняет альфа\-смешение.  Этот класс можно использовать для непосредственного изменения пользовательского интерфейса приложения.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md)  
  
## Требования  
 **заголовок:** afxdrawmanager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)