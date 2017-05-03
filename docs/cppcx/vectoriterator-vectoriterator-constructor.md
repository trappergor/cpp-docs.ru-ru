---
title: "VectorIterator::VectorIterator - конструктор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::VectorIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::VectorIterator - конструктор"
ms.assetid: 93286731-9499-4bfb-a24b-b302479c38cc
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::VectorIterator - конструктор
Инициализирует новый экземпляр класса VectorIterator.  
  
## Синтаксис  
  
```  
  
VectorIterator();  
  
explicit VectorIterator(  
   Windows::Foundation::Collections::IVector<T>^ v  
);  
```  
  
#### Параметры  
 `v`  
 Объект IVector\<T\>.  
  
## Заметки  
 Первый пример синтаксиса является конструктором по умолчанию. Второй пример синтаксиса является явным конструктором, используемым для создания экземпляра класса VectorIterator из объекта IVector\<T\>.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)