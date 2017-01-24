---
title: "Класс CD2DLayer | Microsoft Docs"
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
  - "afxrendertarget/CD2DLayer"
  - "CD2DLayer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DLayer - класс"
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CD2DLayer
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1Layer.  
  
## Синтаксис  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DLayer::CD2DLayer](../Topic/CD2DLayer::CD2DLayer.md)|Создает объект CD2DLayer.|  
|[CD2DLayer::~CD2DLayer](../Topic/CD2DLayer::~CD2DLayer.md)|Деструктор.  Вызывается при уничтожении объекта слоя D2D.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DLayer::Attach](../Topic/CD2DLayer::Attach.md)|Присоединяет интерфейс существующего ресурса к объекту|  
|[CD2DLayer::Create](../Topic/CD2DLayer::Create.md)|Создает объект CD2DLayer.  \(Переопределяет [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DLayer::Destroy](../Topic/CD2DLayer::Destroy.md)|Уничтожает объект CD2DLayer.  \(Переопределяет [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DLayer::Detach](../Topic/CD2DLayer::Detach.md)|Отсоединяет интерфейс ресурса от объекта|  
|[CD2DLayer::Get](../Topic/CD2DLayer::Get.md)|Возвращает интерфейс ID2D1Layer|  
|[CD2DLayer::GetSize](../Topic/CD2DLayer::GetSize.md)|Возвращает размер целевого буфера визуализации в аппаратно\-независимых пикселях|  
|[CD2DLayer::IsValid](../Topic/CD2DLayer::IsValid.md)|Проверяет допустимость ресурса \(переопределяет [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DLayer::operator ID2D1Layer\*](../Topic/CD2DLayer::operator%20ID2D1Layer*.md)|Возвращает интерфейс ID2D1Layer|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CD2DLayer::m\_pLayer](../Topic/CD2DLayer::m_pLayer.md)|Хранит указатель на объект ID2D1Layer.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DLayer](../../mfc/reference/cd2dlayer-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)