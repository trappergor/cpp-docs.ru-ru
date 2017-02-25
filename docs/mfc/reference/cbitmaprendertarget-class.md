---
title: "Класс CBitmapRenderTarget | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CBitmapRenderTarget"
  - "CBitmapRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBitmapRenderTarget - класс"
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс CBitmapRenderTarget
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1BitmapRenderTarget.  
  
## Синтаксис  
  
```  
class CBitmapRenderTarget : public CRenderTarget;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBitmapRenderTarget::CBitmapRenderTarget](../Topic/CBitmapRenderTarget::CBitmapRenderTarget.md)|Создает объект CBitmapRenderTarget.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBitmapRenderTarget::Attach](../Topic/CBitmapRenderTarget::Attach.md)|Присоединяет интерфейс существующего целевого буфера визуализации к объекту|  
|[CBitmapRenderTarget::Detach](../Topic/CBitmapRenderTarget::Detach.md)|Отсоединяет интерфейс целевого буфера визуализации от объекта|  
|[CBitmapRenderTarget::GetBitmap](../Topic/CBitmapRenderTarget::GetBitmap.md)|Извлекает растровое изображение для данного целевого объекта визуализации.  Возвращаемое растровое изображение может использоваться для операций рисования.|  
|[CBitmapRenderTarget::GetBitmapRenderTarget](../Topic/CBitmapRenderTarget::GetBitmapRenderTarget.md)|Возвращает интерфейс ID2D1BitmapRenderTarget|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget\*](../Topic/CBitmapRenderTarget::operator%20ID2D1BitmapRenderTarget*.md)|Возвращает интерфейс ID2D1BitmapRenderTarget|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CBitmapRenderTarget::m\_pBitmapRenderTarget](../Topic/CBitmapRenderTarget::m_pBitmapRenderTarget.md)|Указатель на объект ID2D1BitmapRenderTarget.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CBitmapRenderTarget](../../mfc/reference/cbitmaprendertarget-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)