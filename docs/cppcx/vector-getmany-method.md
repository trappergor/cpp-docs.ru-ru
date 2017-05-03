---
title: "Vector::GetMany - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetMany - метод"
ms.assetid: e2d5ccf4-101a-47e5-a0d8-56f65a7ff28d
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetMany - метод
Извлекает последовательность элементов из текущего объекта Vector, начиная с определенного индекса, и копирует их в выделенный вызывающим объектом массив.  
  
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
 Выделенный вызывающим объектом массив элементов, которые начинается с элемента, заданного параметром `startIndex`, и заканчивается последним элементом объекта Vector.  
  
## Возвращаемое значение  
 Количество извлеченных элементов.  
  
## Заметки  
 Эта функция не предназначена для прямого использования в клиентском коде. Она предназначена для внутреннего использования в [to\_vector Function](../cppcx/to-vector-function.md), обеспечивая эффективное преобразование экземпляров Platform::Vector в экземпляры std::vector.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)