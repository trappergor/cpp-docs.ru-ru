---
title: "VectorView::GetAt - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::GetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::GetAt - метод"
ms.assetid: 01c5feda-2a97-4429-ae15-4aced96ce332
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::GetAt - метод
Извлекает элемент текущего VectorView, указанный заданным индексом.  
  
## Синтаксис  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
#### Параметры  
 `index`  
 Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте VectorView.  
  
## Возвращаемое значение  
 Элемент, заданный параметром `index`. Тип элемента указан параметром шаблона VectorView *T*.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [VectorView Class](http://msdn.microsoft.com/ru-ru/79697692-ae58-40e0-958f-cf1be6347994)