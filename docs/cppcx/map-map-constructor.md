---
title: "Map::Map - конструктор | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Map - конструктор"
ms.assetid: 4cd314eb-e3e3-4fa7-8c58-96e48d167246
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Map - конструктор
Инициализирует новый экземпляр класса Map.  
  
## Синтаксис  
  
```  
explicit Map(  
   const C& comp = C()  
);  
explicit Map(  
   const StdMap& m  
);  
explicit Map(  
   StdMap&& m  
);  
template <  
   typename InIt  
>  
Map(  
   InItfirst,  
   InItlast,  
   const C& comp = C()  
);  
```  
  
#### Параметры  
 `InIt`  
 Имя типа текущего объекта Map.  
  
 `comp`  
 Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map.  
  
 `m`  
 Ссылка или [Значения Lvalue и Rvalue](http://msdn.microsoft.com/library/a8843344-cccc-40be-b701-b71f7b5cdcaf) на [Класс map](../standard-library/map-class.md), используемый для инициализации текущего объекта Map.  
  
 `first`  
 Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта Map.  
  
 `last`  
 Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта Map.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)