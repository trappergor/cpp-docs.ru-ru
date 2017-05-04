---
title: "Метод Map::GetView | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::GetView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод Map::GetView"
ms.assetid: d432bb98-d354-4caa-8c2b-794406ac0b0b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Map::GetView
Возвращает доступное только для чтения представление текущего сопоставления, то есть класс [Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md), который реализует интерфейс [Windows::Foundation::Collections::IMapView\<K,V](http://msdn.microsoft.com/library/windows/apps/br226037.aspx).  
  
## Синтаксис  
  
```  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
## Возвращаемое значение  
 Объект `MapView`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapClass](../cppcx/platform-collections-unorderedmap-class.md)   
 [Коллекции \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)