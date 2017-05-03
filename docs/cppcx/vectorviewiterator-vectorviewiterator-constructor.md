---
title: "VectorViewIterator::VectorViewIterator - конструктор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::VectorViewIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::VectorViewIterator - конструктор"
ms.assetid: 30bf643a-4100-4547-b34c-ce16c89f78ed
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::VectorViewIterator - конструктор
Инициализирует новый экземпляр класса VectorViewIterator.  
  
## Синтаксис  
  
```  
  
VectorViewIterator();  
  
explicit VectorViewIterator(  
   Windows::Foundation::Collections::IVectorView<T>^ v  
);  
```  
  
#### Параметры  
 `v`  
 Объект IVectorView\<T\>.  
  
## Заметки  
 Первый пример синтаксиса является конструктором по умолчанию. Второй пример синтаксиса является явным конструктором, используемым для создания экземпляра класса VectorViewIterator из объекта IVectorView\<T\>.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)