---
title: "Конструктор EventTargetArray::EventTargetArray | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventTargetArray, конструктор"
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Конструктор EventTargetArray::EventTargetArray
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### Параметры  
 `hr`  
 После этих операций конструктора параметр `hr` показывает, было ли успешным или закончилось неудачей размещение массива.  В следующей таблице описаны все возможные значения для `hr`.  
  
 S\_OK  
 Операция выполнена успешно.  
  
 E\_OUTOFMEMORY  
 Для этого массива не может быть выделена память.  
  
 S\_FALSE  
 Параметр `items` меньше или равен нулю.  
  
 `items`  
 Число размещаемых элементов массива.  
  
## Примечания  
 Инициализирует новый экземпляр класса EventTargetArray.  
  
 EventTargetArray используется для хранения массива обработчиков событий в объекте EventSource.  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Класс EventTargetArray](../windows/eventtargetarray-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)