---
title: "Метод Map::Lookup | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Lookup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод Map::Lookup"
ms.assetid: c56773ae-2df0-4d21-a6ab-9603529547b0
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Map::Lookup
Возвращает значение типа V, связанное с указанным ключом типа K, если ключ существует.  
  
## Синтаксис  
  
```  
V Lookup(  
   K key  
);  
```  
  
#### Параметры  
 `key`  
 Ключ, используемый для поиска элемента в сопоставлении. Тип `key` является именем типа *K*.  
  
## Возвращаемое значение  
 Значение, связанное с ключом `key`. Тип возвращаемого значения является именем типа *V*.  
  
## Заметки  
 Если ключ не существует, создается исключение [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md).  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)   
 [Коллекции \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)