---
title: "Vector::IndexOf - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::IndexOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::IndexOf - метод"
ms.assetid: 4a965992-3858-4e3f-992a-b94c0580b2f7
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::IndexOf - метод
Выполняет поиск указанного элемента в текущем объекте Vector и возвращает его индекс, если он найден.  
  
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
  
## Заметки  
 IndexOf использует std::find\_if для поиска элемента. Таким образом, типы настраиваемых элементов должны перегрузить оператор \=\= и \!\= для включения сравнений на равенство, которое требуется для find\_if.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)