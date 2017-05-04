---
title: "VectorView::GetMany - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetMany - метод"
ms.assetid: 67d9348f-66fe-417e-9e25-5de0a3cd306c
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetMany - метод
Извлекает последовательность элементов из текущего объекта VectorView, начиная с указанного индекса.  
  
## Синтаксис  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
#### Параметры  
 `startIndex`  
 Отсчитываемый от нуля индекс начала элементов для извлечения.  
  
 `dest`  
 Когда эта операция завершается, массив элементов начинается с элемента, заданного `startIndex`, и заканчивается последним элементом объекта VectorView.  
  
## Возвращаемое значение  
 Количество извлеченных элементов.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [VectorView Class](http://msdn.microsoft.com/ru-ru/79697692-ae58-40e0-958f-cf1be6347994)