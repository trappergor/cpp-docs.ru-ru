---
title: "Класс CD2DPathGeometry | Microsoft Docs"
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
  - "afxrendertarget/CD2DPathGeometry"
  - "CD2DPathGeometry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DPathGeometry - класс"
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CD2DPathGeometry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1PathGeometry.  
  
## Синтаксис  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DPathGeometry::CD2DPathGeometry](../Topic/CD2DPathGeometry::CD2DPathGeometry.md)|Создает объект CD2DPathGeometry.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DPathGeometry::Attach](../Topic/CD2DPathGeometry::Attach.md)|Присоединяет интерфейс существующего ресурса к объекту|  
|[CD2DPathGeometry::Create](../Topic/CD2DPathGeometry::Create.md)|Создает объект CD2DPathGeometry.  \(Переопределяет [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DPathGeometry::Destroy](../Topic/CD2DPathGeometry::Destroy.md)|Уничтожает объект CD2DPathGeometry.  \(Переопределяет [CD2DGeometry::Destroy](../Topic/CD2DGeometry::Destroy.md).\)|  
|[CD2DPathGeometry::Detach](../Topic/CD2DPathGeometry::Detach.md)|Отсоединяет интерфейс ресурса от объекта|  
|[CD2DPathGeometry::GetFigureCount](../Topic/CD2DPathGeometry::GetFigureCount.md)|Извлекает количество фигур в геометрическом пути.|  
|[CD2DPathGeometry::GetSegmentCount](../Topic/CD2DPathGeometry::GetSegmentCount.md)|Извлекает количество сегментов в геометрическом пути.|  
|[CD2DPathGeometry::Open](../Topic/CD2DPathGeometry::Open.md)|Извлекает приемник геометрии, используемый для заполнения геометрического пути фигурами и сегментами.|  
|[CD2DPathGeometry::Stream](../Topic/CD2DPathGeometry::Stream.md)|Копирует содержимое геометрического пути в заданный объект ID2D1GeometrySink.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DPathGeometry::m\_pPathGeometry](../Topic/CD2DPathGeometry::m_pPathGeometry.md)|Указатель на ID2D1PathGeometry.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DGeometry](../Topic/CD2DGeometry%20Class.md)  
  
 [CD2DPathGeometry](../../mfc/reference/cd2dpathgeometry-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)