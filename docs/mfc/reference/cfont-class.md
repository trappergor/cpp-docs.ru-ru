---
title: "CFont Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFont"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFont class"
  - "шрифты, MFC - классы"
  - "GDI, font classes"
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CFont Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует шрифт приборного графического интерфейса Windows \(GDI\) и предоставляет функции\-члены для управления шрифт.  
  
## Синтаксис  
  
```  
class CFont : public CGdiObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFont::CFont](../Topic/CFont::CFont.md)|Создает объект `CFont`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFont::CreateFont](../Topic/CFont::CreateFont.md)|Инициализирует `CFont` с заданными характеристиками.|  
|[CFont::CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md)|Инициализирует объект `CFont` с характеристиками уступанные структура `LOGFONT`.|  
|[CFont::CreatePointFont](../Topic/CFont::CreatePointFont.md)|Инициализирует `CFont` с указанной высоты, измеряемый в десятых точки и шрифт.|  
|[CFont::CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md)|То же, что и `CreateFontIndirect` за исключением того, что высота шрифта измеряться в десятых точки, а не на логические единицы.|  
|[CFont::FromHandle](../Topic/CFont::FromHandle.md)|Возвращает указатель на объект `CFont` заданный Windows **HFONT**.|  
|[CFont::GetLogFont](../Topic/CFont::GetLogFont.md)|Заполняет `LOGFONT` с сведения о логических шрифте вложенном в объект `CFont`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFont::operator HFONT](../Topic/CFont::operator%20HFONT.md)|Возвращает вложенный дескриптор шрифта GDI Windows на объект `CFont`.|  
  
## Заметки  
 Использование объекта `CFont`, создание объекта `CFont` и вложить шрифт Windows на него с [CreateFont](../Topic/CFont::CreateFont.md), [CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md), [CreatePointFont](../Topic/CFont::CreatePointFont.md) или [CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md), а затем использовать функций\-членов объектов для обработки шрифт.  
  
 Функции `CreatePointFont` и `CreatePointFontIndirect` часто проще в использовании, чем `CreateFont` или `CreateFontIndirect` поскольку они делают преобразование для высоты шрифта от размера точки к логическим модули автоматически.  
  
 Дополнительные сведения о `CFont` см. в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [MFC просматривает HIERSVR](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)