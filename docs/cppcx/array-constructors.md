---
title: "Конструкторы массивов | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::Array"
ms.assetid: befb8088-3915-4b5c-b7fd-90f79961412d
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Конструкторы массивов
Инициализирует одномерный изменяемый массив типов, указанных в параметре шаблона класса *T*.  
  
## Синтаксис  
  
```  
  
Array(unsigned int size);  
Array(T* data, unsigned int size);  
  
```  
  
#### Параметры  
 `T`  
 Параметр шаблона класса.  
  
 `size`  
 Количество элементов в массиве.  
  
 `data`  
 Указатель на массив данных типа `T`, используемый для инициализации данного объекта Array.  
  
## Заметки  
 Дополнительные сведения о том, как создавать экземпляры Platform::Array, см. в разделе [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Platform::Array \- класс](../cppcx/platform-array-class.md)