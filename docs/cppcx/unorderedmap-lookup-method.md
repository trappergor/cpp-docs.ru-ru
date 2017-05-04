---
title: "Метод UnorderedMap::Lookup | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::Lookup"
ms.assetid: 6f9bb393-3791-423d-bfee-925e0531e1a5
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод UnorderedMap::Lookup
Возвращает значение типа V, связанное с указанным ключом типа K.  
  
## Синтаксис  
  
```scr  
V Lookup(  
   K key  
);  
```  
  
#### Параметры  
 `key`  
 Ключ, используемый для поиска элемента в объекте UnorderedMap. Тип `key` является именем типа *K*.  
  
## Возвращаемое значение  
 Значение, связанное с ключом `key`. Тип возвращаемого значения является именем типа *V*.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Коллекции](../cppcx/collections-c-cx.md)   
 [Класс Platform::Collections::UnorderedMap](../cppcx/platform-collections-unorderedmap-class.md)