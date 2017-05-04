---
title: "Метод MapView::Lookup | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::Lookup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод MapView::Lookup"
ms.assetid: 93090ac3-3f1d-4b7e-b80e-164b8c65cd29
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод MapView::Lookup
Возвращает значение типа V, связанное с указанным ключом типа K.  
  
## Синтаксис  
  
```  
V Lookup(  
   K key  
);  
```  
  
#### Параметры  
 `key`  
 Ключ, используемый для поиска элемента в объекте MapView. Тип `key` является именем типа *K*.  
  
## Возвращаемое значение  
 Значение, связанное с ключом `key`. Тип возвращаемого значения является именем типа *V*.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)