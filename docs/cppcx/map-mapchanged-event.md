---
title: "Событие Map::MapChanged | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::MapChanged"
ms.assetid: d14b5b93-36ff-47a5-b588-dd1dc6ea4364
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Событие Map::MapChanged
Возникает, когда элемент вставляется в сопоставление или удаляется из него.  
  
## Синтаксис  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
## Значение свойства, возвращаемое значение  
 Объект [MapChangedEventHandler\<K,V](http://msdn.microsoft.com/library/windows/apps/br206644.aspx), содержащий сведения о вызвавшем событие объекте и типе произошедшего изменения. См. также [IMapChangedEventArgs\<K](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) и [CollectionChange Enumeration](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).  
  
## Эквивалент в .NET Framework  
 Приложения для Магазина Windows, использующие проект C\# или Visual Basic IMap\<K,V\> в качестве IDictionary\<K,V\>.  
  
## Требования  
 Windows 8.0 или выше  
  
## См. также  
 [Коллекции](../cppcx/collections-c-cx.md)