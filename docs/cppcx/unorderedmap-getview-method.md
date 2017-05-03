---
title: "Метод UnorderedMap::GetView | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::GetView"
ms.assetid: 41a12802-3f42-461c-a6fc-a35fc34517f2
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод UnorderedMap::GetView
Возвращает доступное только для чтения представление текущего объекта UnorderedMap; то есть класс [Класс Platform::Collections::UnorderedMapView](../cppcx/platform-collections-unorderedmapview-class.md), который реализует интерфейс [Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx).  
  
## Синтаксис  
  
```scr  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## Возвращаемое значение  
 Объект `UnorderedMapView`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Коллекции](../cppcx/collections-c-cx.md)   
 [Класс Platform::Collections::UnorderedMap](../cppcx/platform-collections-unorderedmap-class.md)   
 [Класс Platform::Collections::UnorderedMapView](../cppcx/platform-collections-unorderedmapview-class.md)