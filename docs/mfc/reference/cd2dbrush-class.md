---
title: "Класс CD2DBrush | Microsoft Docs"
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
  - "CD2DBrush"
  - "afxrendertarget/CD2DBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBrush - класс"
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CD2DBrush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1Brush.  
  
## Синтаксис  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBrush::CD2DBrush](../Topic/CD2DBrush::CD2DBrush.md)|Создает объект CD2DBrush.|  
|[CD2DBrush::~CD2DBrush](../Topic/CD2DBrush::~CD2DBrush.md)|Деструктор.  Вызывается при уничтожении объекта кисти D2D.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBrush::Attach](../Topic/CD2DBrush::Attach.md)|Присоединяет интерфейс существующего ресурса к объекту|  
|[CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md)|Уничтожает объект CD2DBrush.  \(Переопределяет [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DBrush::Detach](../Topic/CD2DBrush::Detach.md)|Отсоединяет интерфейс ресурса от объекта|  
|[CD2DBrush::Get](../Topic/CD2DBrush::Get.md)|Возвращает интерфейс ID2D1Brush|  
|[CD2DBrush::GetOpacity](../Topic/CD2DBrush::GetOpacity.md)|Получает степень прозрачности данной кисти|  
|[CD2DBrush::GetTransform](../Topic/CD2DBrush::GetTransform.md)|Получает текущее преобразование целевого буфера визуализации|  
|[CD2DBrush::IsValid](../Topic/CD2DBrush::IsValid.md)|Проверяет допустимость ресурса \(переопределяет [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DBrush::SetOpacity](../Topic/CD2DBrush::SetOpacity.md)|Устанавливает степень прозрачности данной кисти|  
|[CD2DBrush::SetTransform](../Topic/CD2DBrush::SetTransform.md)|Применяет заданное преобразование к целевому объекту визуализации, замещая существующее преобразование.  Все последующие операции рисования имеют место в преобразованном пространстве|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBrush::operator ID2D1Brush\*](../Topic/CD2DBrush::operator%20ID2D1Brush*.md)|Возвращает интерфейс ID2D1Brush|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DBrush::m\_pBrush](../Topic/CD2DBrush::m_pBrush.md)|Хранит указатель на объект ID2D1Brush.|  
|[CD2DBrush::m\_pBrushProperties](../Topic/CD2DBrush::m_pBrushProperties.md)|Свойства кисти.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)