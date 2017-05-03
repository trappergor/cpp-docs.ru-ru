---
title: "Метод Map::HasKey | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::HasKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод Map::HasKey"
ms.assetid: ba7864af-056a-4b7b-843d-08c45b7f7394
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Map::HasKey
Определяет, содержит ли текущий объект Map указанный ключ.  
  
## Синтаксис  
  
```  
  
bool HasKey(  
   K key  
);  
```  
  
#### Параметры  
 `key`  
 Ключ, используемый для поиска элемента Map. Тип `key` является именем типа *K*.  
  
## Возвращаемое значение  
 Значение `true`, если ключ найден; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)