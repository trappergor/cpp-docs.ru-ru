---
title: "Метод UnorderedMapView::Split | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::Split"
ms.assetid: b759d254-40c9-40f1-9838-106ffb2c5626
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод UnorderedMapView::Split
Разделяет текущий объект UnorderedMapView на два объекта UnorderedMapView. Этот метод не выполняет никаких действий.  
  
## Синтаксис  
  
```cpp  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,  
                         V>^ * secondPartition  
);  
```  
  
#### Параметры  
 `firstPartition`  
 Первая часть исходного объекта UnorderedMapView.  
  
 `secondPartition`  
 Вторая часть исходного объекта UnorderedMapView.  
  
## Заметки  
 Этот метод не выполняет никаких действий.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::UnorderedMapView](../cppcx/platform-collections-unorderedmapview-class.md)