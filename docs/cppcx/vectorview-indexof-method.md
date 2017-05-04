---
title: "VectorView::IndexOf - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::IndexOf - метод"
ms.assetid: 848117ec-ad4a-4a0b-9c1e-9076e5188869
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::IndexOf - метод
Выполняет поиск указанного элемента в текущем объекте VectorView и возвращает его индекс, если он найден.  
  
## Синтаксис  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
#### Параметры  
 `value`  
 Элемент, который нужно найти.  
  
 `index`  
 Отсчитываемый от нуля индекс элемента, если параметр `value` найден; в противном случае — 0.  
  
 Параметр `index` имеет значение 0, если элемент является первым элементом объекта VectorView или элемент не найден. Если возвращаемое значение — `true`, элемент найден и является первым элементом; в противном случае элемент не найден.  
  
## Возвращаемое значение  
 Значение `true`, если указанный элемент найден; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [VectorView Class](http://msdn.microsoft.com/ru-ru/79697692-ae58-40e0-958f-cf1be6347994)