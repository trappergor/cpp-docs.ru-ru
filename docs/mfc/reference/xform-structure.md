---
title: "Структура XFORM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "XFORM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XFORM - структура"
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Структура XFORM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `XFORM` имеет следующую форму:  
  
## Синтаксис  
  
```  
  
      typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## Заметки  
 Структура `XFORM` задается преобразование страницей пространства возможности пространства.  Элементы **eDx** и **eDy** определяют горизонтальные и вертикальные компоненты преобразования соответственно.  В следующей таблице показано, как другие элементы используются в зависимости от операции:  
  
|Операция|eM11|eM12|eM21|eM22|  
|--------------|----------|----------|----------|----------|  
|`Rotation`|Косинус угла поворота|Синус угла поворота|Отрицательный синус угла поворота|Косинус угла поворота|  
|**Масштабирование**|Компонент горизонтального масштабирования|Nothing|Nothing|Вертикальный компонент масштабирования|  
|**Ножницы**|Nothing|Горизонтальная константа соразмерности|Вертикальная константа соразмерности|Nothing|  
|**Отражение**|Горизонтальный компонент отражения|Nothing|Nothing|Вертикальный компонент отражения|  
  
## Требования  
 **Header:** wingdi.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../Topic/CRgn::CreateFromData.md)