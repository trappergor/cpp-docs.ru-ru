---
title: "CBrush Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "кисти, CBrush class"
  - "CBrush class"
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CBrush Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует кисть приборного графического интерфейса Windows \(GDI\).  
  
## Синтаксис  
  
```  
class CBrush : public CGdiObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBrush::CBrush](../Topic/CBrush::CBrush.md)|Создает объект `CBrush`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBrush::CreateBrushIndirect](../Topic/CBrush::CreateBrushIndirect.md)|Инициализирует кисть с стиль, цвет и шаблон, указанный в структуре [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035).|  
|[CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)|Инициализирует кисть с шаблон указанного файла DIB \(DIB\).|  
|[CBrush::CreateHatchBrush](../Topic/CBrush::CreateHatchBrush.md)|Инициализирует кисть с заданным шаблоном насиженными и цветом.|  
|[CBrush::CreatePatternBrush](../Topic/CBrush::CreatePatternBrush.md)|Инициализирует указанный шаблон кисть с растровым изображением.|  
|[CBrush::CreateSolidBrush](../Topic/CBrush::CreateSolidBrush.md)|Инициализирует кисть с указанным сплошным цветом.|  
|[CBrush::CreateSysColorBrush](../Topic/CBrush::CreateSysColorBrush.md)|Создает кисть, которая по умолчанию является системный цвет.|  
|[CBrush::FromHandle](../Topic/CBrush::FromHandle.md)|Возвращает указатель на объект `CBrush` заданный дескриптор объекта Windows `HBRUSH`.|  
|[CBrush::GetLogBrush](../Topic/CBrush::GetLogBrush.md)|Возвращает структуру [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035).|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBrush::operator HBRUSH](../Topic/CBrush::operator%20HBRUSH.md)|Возвращает вложенный маркер Windows на объект `CBrush`.|  
  
## Заметки  
 Чтобы использовать объект `CBrush`, создайте объект `CBrush` и передать его к любому функции\-члену `CDC`, требующий кисти.  
  
 Кисти могут быть тверды, насижены или выполняются по образцу.  
  
 Дополнительные сведения о `CBrush` см. в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [MFC просматривает PROPDLG](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CBitmap Class](../../mfc/reference/cbitmap-class.md)   
 [Класс CDC](../Topic/CDC%20Class.md)