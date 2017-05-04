---
title: "Метод MapView::HasKey | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::HasKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод MapView::HasKey"
ms.assetid: c1a24f63-e6fd-4cfd-90ce-b89352b98324
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод MapView::HasKey
Определяет, содержит ли текущий объект MapView указанный ключ.  
  
## Синтаксис  
  
```  
  
bool HasKey(  
   K key  
);  
```  
  
#### Параметры  
 `key`  
 Ключ, используемый для поиска элемента MapView. Тип `key` является именем типа *K*.  
  
## Возвращаемое значение  
 Значение `true`, если ключ найден; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)