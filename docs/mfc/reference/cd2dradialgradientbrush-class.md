---
title: "Класс CD2DRadialGradientBrush | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DRadialGradientBrush"
  - "afxrendertarget/CD2DRadialGradientBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRadialGradientBrush - класс"
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс CD2DRadialGradientBrush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1RadialGradientBrush.  
  
## Синтаксис  
  
```  
class CD2DRadialGradientBrush : public CD2DGradientBrush;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](../Topic/CD2DRadialGradientBrush::CD2DRadialGradientBrush.md)|Создает объект CD2DLinearGradientBrush.|  
|[CD2DRadialGradientBrush::~CD2DRadialGradientBrush](../Topic/CD2DRadialGradientBrush::~CD2DRadialGradientBrush.md)|Деструктор.  Вызывается при уничтожении объекта радиальной градиентной кисти D2D.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DRadialGradientBrush::Attach](../Topic/CD2DRadialGradientBrush::Attach.md)|Присоединяет интерфейс существующего ресурса к объекту|  
|[CD2DRadialGradientBrush::Create](../Topic/CD2DRadialGradientBrush::Create.md)|Создает объект CD2DRadialGradientBrush.  \(Переопределяет [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DRadialGradientBrush::Destroy](../Topic/CD2DRadialGradientBrush::Destroy.md)|Уничтожает объект CD2DRadialGradientBrush.  \(Переопределяет [CD2DGradientBrush::Destroy](../Topic/CD2DGradientBrush::Destroy.md).\)|  
|[CD2DRadialGradientBrush::Detach](../Topic/CD2DRadialGradientBrush::Detach.md)|Отсоединяет интерфейс ресурса от объекта|  
|[CD2DRadialGradientBrush::Get](../Topic/CD2DRadialGradientBrush::Get.md)|Возвращает интерфейс ID2D1RadialGradientBrush|  
|[CD2DRadialGradientBrush::GetCenter](../Topic/CD2DRadialGradientBrush::GetCenter.md)|Извлекает центр градиентного эллипса|  
|[CD2DRadialGradientBrush::GetGradientOriginOffset](../Topic/CD2DRadialGradientBrush::GetGradientOriginOffset.md)|Извлекает смещение начала градиента относительно центра градиентного эллипса.|  
|[CD2DRadialGradientBrush::GetRadiusX](../Topic/CD2DRadialGradientBrush::GetRadiusX.md)|Извлекает радиус градиентного эллипса по оси X|  
|[CD2DRadialGradientBrush::GetRadiusY](../Topic/CD2DRadialGradientBrush::GetRadiusY.md)|Извлекает радиус градиентного эллипса по оси Y|  
|[CD2DRadialGradientBrush::SetCenter](../Topic/CD2DRadialGradientBrush::SetCenter.md)|Задает центр градиентного эллипса в пространстве координат кисти|  
|[CD2DRadialGradientBrush::SetGradientOriginOffset](../Topic/CD2DRadialGradientBrush::SetGradientOriginOffset.md)|Задает смещение начала градиента относительно центра градиентного эллипса.|  
|[CD2DRadialGradientBrush::SetRadiusX](../Topic/CD2DRadialGradientBrush::SetRadiusX.md)|Задает радиус по оси X градиентного эллипса в пространстве координат кисти|  
|[CD2DRadialGradientBrush::SetRadiusY](../Topic/CD2DRadialGradientBrush::SetRadiusY.md)|Задает радиус по оси Y градиентного эллипса в пространстве координат кисти|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush\*](../Topic/CD2DRadialGradientBrush::operator%20ID2D1RadialGradientBrush*.md)|Возвращает интерфейс ID2D1RadialGradientBrush|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DRadialGradientBrush::m\_pRadialGradientBrush](../Topic/CD2DRadialGradientBrush::m_pRadialGradientBrush.md)|Указатель на ID2D1RadialGradientBrush.|  
|[CD2DRadialGradientBrush::m\_RadialGradientBrushProperties](../Topic/CD2DRadialGradientBrush::m_RadialGradientBrushProperties.md)|Центр, смещение начала градиента и радиусы по осям X и Y кисти градиента.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 [CD2DRadialGradientBrush](../../mfc/reference/cd2dradialgradientbrush-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)