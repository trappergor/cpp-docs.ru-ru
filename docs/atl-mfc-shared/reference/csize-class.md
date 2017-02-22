---
title: "CSize Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSize class"
  - "измерения"
  - "измерения, MFC - библиотека"
  - "SIZE"
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CSize Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Похожий на структуру Windows [РАЗМЕР](http://msdn.microsoft.com/library/windows/desktop/dd145106), которая реализует относительную координату или положение.  
  
## Синтаксис  
  
```  
class CSize : public tagSIZE  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSize::CSize](../Topic/CSize::CSize.md)|Создает объект `CSize`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSize::operator \-](../Topic/CSize::operator%20-.md)|Вычитает 2 размера.|  
|[CSize::operator \!\=](../Topic/CSize::operator%20!=.md)|Проверяет неравенство между `CSize` и размером.|  
|[CSize::operator \+](../Topic/CSize::operator%20+.md)|Добавляет 2 размера.|  
|[CSize::operator \+\=](../Topic/CSize::operator%20+=.md)|Добавляет размер в `CSize`.|  
|[CSize::operator \-\=](../Topic/CSize::operator%20-=.md)|Вычитает размер из `CSize`.|  
|[CSize::operator \=\=](../Topic/CSize::operator%20==.md)|Проверяет равенство между `CSize` и размером.|  
  
## Заметки  
 Этот класс является производным от структуры **SIZE**.  Это означает, что можно передать `CSize` в параметре который вызывается для **SIZE** и элементы данных структуры **SIZE** доступные элементы данных `CSize`.  
  
 Члены **cx** и **cySIZE** \(и `CSize`\) открытыми.  Кроме того, `CSize` реализуют функции\-члены для обработки структуры **SIZE**.  
  
> [!NOTE]
>  Дополнительные сведения об общих служебных классов \(например, `CSize`\) см. в разделе [Общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## Иерархия наследования  
 `tagSIZE`  
  
 `CSize`  
  
## Требования  
 **Header:** atltypes.h  
  
## См. также  
 [MFC, пытается интерфейс MDI](../../top/visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint Class](../Topic/CPoint%20Class.md)