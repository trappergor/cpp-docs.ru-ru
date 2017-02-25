---
title: "CPalette Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPalette"
  - "HPALETTE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "палитры цветов, MFC - библиотека"
  - "CPalette class"
  - "HPALETTE"
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CPalette Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует цветовая палитра Windows.  
  
## Синтаксис  
  
```  
class CPalette : public CGdiObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPalette::CPalette](../Topic/CPalette::CPalette.md)|Создает объект `CPalette` без вложенной палитры Windows.  Необходимо инициализировать объект `CPalette` с одним из функции\-члены инициализации перед использованием.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPalette::AnimatePalette](../Topic/CPalette::AnimatePalette.md)|Заменяет записи в логической палитры, заданной объектом `CPalette`.  Приложению не обязательно обновлять свою клиентскую область, поскольку Windows сопоставляет новые записи в палитру системы немедленно.|  
|[CPalette::CreateHalftonePalette](../Topic/CPalette::CreateHalftonePalette.md)|Создает палитра полутонового изображения для контекста устройства и вложение его к объекту `CPalette`.|  
|[CPalette::CreatePalette](../Topic/CPalette::CreatePalette.md)|Создает цветовую палитру Windows и вложение его к объекту `CPalette`.|  
|[CPalette::FromHandle](../Topic/CPalette::FromHandle.md)|Возвращает указатель на объект `CPalette` заданный дескриптор объекта палитры Windows.|  
|[CPalette::GetEntryCount](../Topic/CPalette::GetEntryCount.md)|Извлекает число записей в логической палитры цветов.|  
|[CPalette::GetNearestPaletteIndex](../Topic/CPalette::GetNearestPaletteIndex.md)|Возвращает индекс записи в логической палитры, в наибольшей степени согласуется со значением цвета.|  
|[CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)|Получает диапазон цветов в палитре логических записей.|  
|[CPalette::ResizePalette](../Topic/CPalette::ResizePalette.md)|Изменяет размер логической палитры, заданный объектом `CPalette` с заданным количеством записей.|  
|[CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)|Устанавливает значение цвета RGB и пометит в диапазоне записей в логической палитры.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPalette::operator HPALETTE](../Topic/CPalette::operator%20HPALETTE.md)|Возвращает значение вложенного `HPALETTE``CPalette`.|  
  
## Заметки  
 Палитра предоставляет интерфейс между приложением и выходным устройством \(как дисплейное устройство\).  Интерфейс позволяет приложению полностью использовать преимущества возможностей устройства вывода строго мешать без цвета, цвета, отображаемые другими приложениями.  Windows использует палитру приложения logical \(список обязательных и палитру цветов\) системы \(которая определяет доступные цвета\), чтобы определить, используемые цвета.  
  
 Объект `CPalette` предоставляет функции\-члены для управления палитру сосланную к объекту.  Создайте объект `CPalette` и используйте его функции\-члены для создания реальной палитру, объект приборного графического интерфейса \(GDI\) и манипулировать ее записи и другие свойства.  
  
 Дополнительные сведения об использовании `CPalette` см. в разделе [графические объекты](../../mfc/graphic-objects.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [MFC просматривает DIBLOOK](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)   
 [CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)