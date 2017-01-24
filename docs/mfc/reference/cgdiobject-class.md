---
title: "CGdiObject Class | Microsoft Docs"
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
  - "CGdiObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "кисти, base class for"
  - "CGdiObject class"
  - "шрифты, base class for"
  - "GDI-объекты, base class for"
  - "палитры, base class for"
  - "перья, base class for"
  - "области, base class for"
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGdiObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет базовый класс для различных типов объектов приборного графического интерфейса Windows \(GDI\) как растровые изображения, области кисти, пера, цветов и шрифты.  
  
## Синтаксис  
  
```  
class CGdiObject : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CGdiObject::CGdiObject](../Topic/CGdiObject::CGdiObject.md)|Создает объект `CGdiObject`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CGdiObject::Attach](../Topic/CGdiObject::Attach.md)|Вложение объект GDI Windows на объект `CGdiObject`.|  
|[CGdiObject::CreateStockObject](../Topic/CGdiObject::CreateStockObject.md)|Извлекает маркер на один из стандартных Windows ручек, кистей или шрифтов стандартное.|  
|[CGdiObject::DeleteObject](../Topic/CGdiObject::DeleteObject.md)|Удаляет объект GDI Windows, вложенный в объект `CGdiObject` из памяти, освобождение все хранилище системы, связанное с объектом.|  
|[CGdiObject::DeleteTempMap](../Topic/CGdiObject::DeleteTempMap.md)|Удаляет все временные объекты `CGdiObject`, созданные `FromHandle`.|  
|[CGdiObject::Detach](../Topic/CGdiObject::Detach.md)|Наконец удаляет объект из объекта `CGdiObject` GDI Windows и возвращает дескриптор объекта GDI Windows.|  
|[CGdiObject::FromHandle](../Topic/CGdiObject::FromHandle.md)|Возвращает указатель на объект `CGdiObject` заданный дескриптор объекта GDI Windows.|  
|[CGdiObject::GetObject](../Topic/CGdiObject::GetObject.md)|Заполняет буфер с данными, которые описывают вложенный объект GDI Windows на объект `CGdiObject`.|  
|[CGdiObject::GetObjectType](../Topic/CGdiObject::GetObjectType.md)|Возвращает тип объекта GDI.|  
|[CGdiObject::GetSafeHandle](../Topic/CGdiObject::GetSafeHandle.md)|Возвращает `m_hObject` если `this` не будет `NULL` в этом случае возвращается `NULL`.|  
|[CGdiObject::UnrealizeObject](../Topic/CGdiObject::UnrealizeObject.md)|Сбросить начало координат кистей или сбросить логической палитры.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CGdiObject::operator \!\=](../Topic/CGdiObject::operator%20!=.md)|Определяет, 2 объекта GDI логическое не равны.|  
|[CGdiObject::operator \=\=](../Topic/CGdiObject::operator%20==.md)|Определяет, 2 объекта GDI логически равны.|  
|[CGdiObject::operator HGDIOBJ](../Topic/CGdiObject::operator%20HGDIOBJ.md)|Извлекает `HANDLE` вложенному объекту GDI Windows.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CGdiObject::m\_hObject](../Topic/CGdiObject::m_hObject.md)|`HANDLE`, содержащий `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN` или вложенном `HFONT` к данному объекту.|  
  
## Заметки  
 Никогда не создаются `CGdiObject` напрямую.  Вместо этого необходимо создать объект из одного из его производных классов, как `CPen` или `CBrush`.  
  
 Дополнительные сведения по `CGdiObject` см. в разделе [Графические объекты](../../mfc/graphic-objects.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CGdiObject`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CBitmap Class](../../mfc/reference/cbitmap-class.md)   
 [CBrush Class](../../mfc/reference/cbrush-class.md)   
 [CFont Class](../../mfc/reference/cfont-class.md)   
 [CPalette Class](../../mfc/reference/cpalette-class.md)   
 [CPen Class](../Topic/CPen%20Class.md)   
 [Класс CRgn](../../mfc/reference/crgn-class.md)