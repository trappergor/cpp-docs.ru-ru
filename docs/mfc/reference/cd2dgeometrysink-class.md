---
title: "Класс CD2DGeometrySink | Microsoft Docs"
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
  - "afxrendertarget/CD2DGeometrySink"
  - "CD2DGeometrySink"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGeometrySink - класс"
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CD2DGeometrySink
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1GeometrySink.  
  
## Синтаксис  
  
```  
class CD2DGeometrySink;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DGeometrySink::CD2DGeometrySink](../Topic/CD2DGeometrySink::CD2DGeometrySink.md)|Создает объект CD2DGeometrySink из объекта CD2DPathGeometry.|  
|[CD2DGeometrySink::~CD2DGeometrySink](../Topic/CD2DGeometrySink::~CD2DGeometrySink.md)|Деструктор.  Вызывается при уничтожении объекта приемника геометрии D2D.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DGeometrySink::AddArc](../Topic/CD2DGeometrySink::AddArc.md)|Добавляет в геометрический путь одну дугу|  
|[CD2DGeometrySink::AddBezier](../Topic/CD2DGeometrySink::AddBezier.md)|Создание кривой Безье третьего порядка между текущей точкой и заданной конечной точкой.|  
|[CD2DGeometrySink::AddBeziers](../Topic/CD2DGeometrySink::AddBeziers.md)|Создает последовательность кривых Безье третьего порядка и добавляет их в приемник геометрии.|  
|[CD2DGeometrySink::AddLine](../Topic/CD2DGeometrySink::AddLine.md)|Создает сегмент линии между текущей точкой и заданной конечной точкой и добавляет его в приемник геометрии.|  
|[CD2DGeometrySink::AddLines](../Topic/CD2DGeometrySink::AddLines.md)|Создает последовательность линий по заданным точкам и добавляет их в приемник геометрии.|  
|[CD2DGeometrySink::AddQuadraticBezier](../Topic/CD2DGeometrySink::AddQuadraticBezier.md)|Создание кривой Безье второго порядка между текущей точкой и заданной конечной точкой.|  
|[CD2DGeometrySink::AddQuadraticBeziers](../Topic/CD2DGeometrySink::AddQuadraticBeziers.md)|Добавляет последовательность сегментов Безье второго порядка в виде массива за один вызов.|  
|[CD2DGeometrySink::BeginFigure](../Topic/CD2DGeometrySink::BeginFigure.md)|Начинает новую фигуру в заданной точке.|  
|[CD2DGeometrySink::Close](../Topic/CD2DGeometrySink::Close.md)|Закрывает приемник геометрии|  
|[CD2DGeometrySink::EndFigure](../Topic/CD2DGeometrySink::EndFigure.md)|Завершает текущую фигуру и \(необязательно\) замыкает ее.|  
|[CD2DGeometrySink::Get](../Topic/CD2DGeometrySink::Get.md)|Возвращает интерфейс ID2D1GeometrySink|  
|[CD2DGeometrySink::IsValid](../Topic/CD2DGeometrySink::IsValid.md)|Проверяет допустимость приемника геометрии.|  
|[CD2DGeometrySink::SetFillMode](../Topic/CD2DGeometrySink::SetFillMode.md)|Указывает метод, используемый для определения того, какие из точек лежат внутри геометрии, описанной этим приемником геометрии, а какие за ее пределами.|  
|[CD2DGeometrySink::SetSegmentFlags](../Topic/CD2DGeometrySink::SetSegmentFlags.md)|Задает параметры обводки и соединения для применения к новым сегментам, добавляемым в приемник геометрии.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink\*](../Topic/CD2DGeometrySink::operator%20ID2D1GeometrySink*.md)|Возвращает интерфейс ID2D1GeometrySink|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DGeometrySink::m\_pSink](../Topic/CD2DGeometrySink::m_pSink.md)|Указатель на ID2D1GeometrySink.|  
  
## Иерархия наследования  
 [CD2DGeometrySink](../../mfc/reference/cd2dgeometrysink-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)