---
title: "Класс CD2DBitmapBrush | Microsoft Docs"
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
  - "CD2DBitmapBrush"
  - "afxrendertarget/CD2DBitmapBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmapBrush - класс"
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CD2DBitmapBrush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1BitmapBrush.  
  
## Синтаксис  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](../Topic/CD2DBitmapBrush::CD2DBitmapBrush.md)|Перегружен.  Создает объект CD2DBitmapBrush из файла.|  
|[CD2DBitmapBrush::~CD2DBitmapBrush](../Topic/CD2DBitmapBrush::~CD2DBitmapBrush.md)|Деструктор.  Вызывается при уничтожении объекта растровой кисти D2D.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmapBrush::Attach](../Topic/CD2DBitmapBrush::Attach.md)|Присоединяет интерфейс существующего ресурса к объекту|  
|[CD2DBitmapBrush::Create](../Topic/CD2DBitmapBrush::Create.md)|Создает объект CD2DBitmapBrush.  \(Переопределяет [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DBitmapBrush::Destroy](../Topic/CD2DBitmapBrush::Destroy.md)|Уничтожает объект CD2DBitmapBrush.  \(Переопределяет [CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md).\)|  
|[CD2DBitmapBrush::Detach](../Topic/CD2DBitmapBrush::Detach.md)|Отсоединяет интерфейс ресурса от объекта|  
|[CD2DBitmapBrush::Get](../Topic/CD2DBitmapBrush::Get.md)|Возвращает интерфейс ID2D1BitmapBrush|  
|[CD2DBitmapBrush::GetBitmap](../Topic/CD2DBitmapBrush::GetBitmap.md)|Получает источник растрового изображения, используемого данной кистью для окрашивания|  
|[CD2DBitmapBrush::GetExtendModeX](../Topic/CD2DBitmapBrush::GetExtendModeX.md)|Получает способ заполнения кистью мозаичными элементами области, выходящей за ее растровое изображение, по горизонтали.|  
|[CD2DBitmapBrush::GetExtendModeY](../Topic/CD2DBitmapBrush::GetExtendModeY.md)|Получает способ заполнения кистью мозаичными элементами области, выходящей за ее растровое изображение, по вертикали.|  
|[CD2DBitmapBrush::GetInterpolationMode](../Topic/CD2DBitmapBrush::GetInterpolationMode.md)|Получает метод интерполяции, используемый при масштабировании или повороте растрового изображения кисти|  
|[CD2DBitmapBrush::SetBitmap](../Topic/CD2DBitmapBrush::SetBitmap.md)|Задает источник растрового изображения, используемого данной кистью для окрашивания|  
|[CD2DBitmapBrush::SetExtendModeX](../Topic/CD2DBitmapBrush::SetExtendModeX.md)|Указывает, как кисть заполняет мозаичными элементами области, выходящие за ее растровое изображение, по горизонтали.|  
|[CD2DBitmapBrush::SetExtendModeY](../Topic/CD2DBitmapBrush::SetExtendModeY.md)|Указывает, как кисть заполняет мозаичными элементами области, выходящие за ее растровое изображение, по вертикали.|  
|[CD2DBitmapBrush::SetInterpolationMode](../Topic/CD2DBitmapBrush::SetInterpolationMode.md)|Задает режим интерполяции, используемый при масштабировании или повороте растрового изображения кисти|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmapBrush::CommonInit](../Topic/CD2DBitmapBrush::CommonInit.md)|Инициализирует объект|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush\*](../Topic/CD2DBitmapBrush::operator%20ID2D1BitmapBrush*.md)|Возвращает интерфейс ID2D1BitmapBrush|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBitmapBrush::m\_pBitmap](../Topic/CD2DBitmapBrush::m_pBitmap.md)|Хранит указатель на объект CD2DBitmap.|  
|[CD2DBitmapBrush::m\_pBitmapBrush](../Topic/CD2DBitmapBrush::m_pBitmapBrush.md)|Хранит указатель на объект ID2D1BitmapBrush.|  
|[CD2DBitmapBrush::m\_pBitmapBrushProperties](../Topic/CD2DBitmapBrush::m_pBitmapBrushProperties.md)|Свойства растровой кисти.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DBitmapBrush](../../mfc/reference/cd2dbitmapbrush-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)