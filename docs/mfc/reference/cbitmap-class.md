---
title: "CBitmap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBitmap class"
  - "рисование, средства"
  - "GDI bitmap"
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CBitmap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инкапсулирует растровое изображение приборного графического интерфейса Windows \(GDI\) и предоставляет функции\-члены для управления растровое изображение.  
  
## Синтаксис  
  
```  
class CBitmap : public CGdiObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBitmap::CBitmap](../Topic/CBitmap::CBitmap.md)|Создает объект `CBitmap`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBitmap::CreateBitmap](../Topic/CBitmap::CreateBitmap.md)|Инициализирует объект с растровым изображением памяти устройство\- зависимых, который содержит указанные ширину, высоту и битовый шаблон.|  
|[CBitmap::CreateBitmapIndirect](../Topic/CBitmap::CreateBitmapIndirect.md)|Инициализирует объект с растровым изображением, ширина, высота и битовый шаблон \(если задание\), то указанный в структура **BITMAP**.|  
|[CBitmap::CreateCompatibleBitmap](../Topic/CBitmap::CreateCompatibleBitmap.md)|Инициализирует объект с растровым изображением, чтобы оно будет совместимо с определенным устройством.|  
|[CBitmap::CreateDiscardableBitmap](../Topic/CBitmap::CreateDiscardableBitmap.md)|Инициализирует объект с выгружаемая растровым изображением, совместимо с определенным устройством.|  
|[CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md)|Возвращает указатель на объект `CBitmap` заданный дескриптор растровое изображение Windows `HBITMAP`.|  
|[CBitmap::GetBitmap](../Topic/CBitmap::GetBitmap.md)|Заполняет структуру **BITMAP** сведения о растровом изображении.|  
|[CBitmap::GetBitmapBits](../Topic/CBitmap::GetBitmapBits.md)|Копирует биты указанного растрового изображения в заданный буфер.|  
|[CBitmap::GetBitmapDimension](../Topic/CBitmap::GetBitmapDimension.md)|Возвращает ширину и высоту растрового изображения.  Предполагается, что установлены высота и ширина ранее функцией\-членом [SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md).|  
|[CBitmap::LoadBitmap](../Topic/CBitmap::LoadBitmap.md)|Инициализирует объект с загрузкой именованный ресурс растрового изображения из исполняемого файла приложения и вложить растровое изображение для объекта.|  
|[CBitmap::LoadMappedBitmap](../Topic/CBitmap::LoadMappedBitmap.md)|Загружает растровое изображение и сопоставления цветов с текущим цветам системы.|  
|[CBitmap::LoadOEMBitmap](../Topic/CBitmap::LoadOEMBitmap.md)|Инициализирует объект с загрузкой предопределенное растровое изображение Windows и вложить растровое изображение для объекта.|  
|[CBitmap::SetBitmapBits](../Topic/CBitmap::SetBitmapBits.md)|Задает биты растрового изображения к заданным значениям бит.|  
|[CBitmap::SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md)|Присвоит ширину и высоту в растровое изображение миллиметров в единицах 0,1.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBitmap::operator HBITMAP](../Topic/CBitmap::operator%20HBITMAP.md)|Возвращает вложенный маркер Windows на объект `CBitmap`.|  
  
## Заметки  
 Чтобы использовать объект `CBitmap`, создайте объект, вложите дескриптор растрового изображения к нему с одним из функции\-члены инициализации, а затем вызвать функции\-члены объекта.  
  
 Дополнительные сведения об использовании графических объектов, такими как `CBitmap`, " см. [графические объекты](../../mfc/graphic-objects.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Примеры MFC с интерфейсом MDI](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)