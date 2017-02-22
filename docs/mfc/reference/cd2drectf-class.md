---
title: "Класс CD2DRectF | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DRectF"
  - "CD2DRectF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRectF - класс"
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс CD2DRectF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Программа\-оболочка для `D2D1_RECT_F`.  
  
## Синтаксис  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DRectF::CD2DRectF](../Topic/CD2DRectF::CD2DRectF.md)|Перегружен.  Создает объект `CD2DRectF` из объекта `D2D1_RECT_F`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DRectF::IsNull](../Topic/CD2DRectF::IsNull.md)|Возвращает значение `boolean`, указывающее, содержит ли выражение нет допустимых данных \(`null`\).|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DRectF::operator CRect](../Topic/CD2DRectF::operator%20CRect.md)|Новообращенные `CD2DRectF` к объекту `CRect`.|  
  
## Иерархия наследования  
 `D2D1_RECT_F`  
  
 [CD2DRectF](../../mfc/reference/cd2drectf-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)