---
title: "Метод MapView::Split | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::Split"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод MapView::Split"
ms.assetid: b863e223-2282-4d1a-b995-77a690120542
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод MapView::Split
Разделяет текущий объект MapView на два объекта MapView. Этот метод не выполняет никаких действий.  
  
## Синтаксис  
  
```  
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
 Первая часть исходного объекта MapView.  
  
 `secondPartition`  
 Вторая часть исходного объекта MapView.  
  
## Заметки  
 Этот метод не выполняет никаких действий.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)