---
title: "Класс CD2DSizeF | Microsoft Docs"
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
  - "afxrendertarget/CD2DSizeF"
  - "CD2DSizeF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DSizeF - класс"
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CD2DSizeF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для D2D1\_SIZE\_F.  
  
## Синтаксис  
  
```  
class CD2DSizeF : public D2D1_SIZE_F;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DSizeF::CD2DSizeF](../Topic/CD2DSizeF::CD2DSizeF.md)|Перегружен.  Создает объект `CD2DSizeF` из объекта `D2D1_SIZE_F`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DSizeF::IsNull](../Topic/CD2DSizeF::IsNull.md)|Возвращает значение `boolean`, указывающее, содержит ли выражение нет допустимых данных \(`null`\).|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DSizeF::operator CSize](../Topic/CD2DSizeF::operator%20CSize.md)|Новообращенные `CD2DSizeF` к объекту `CSize`.|  
  
## Иерархия наследования  
 `D2D1_SIZE_F`  
  
 [CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)