---
title: "Vector::GetView - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetView - метод"
ms.assetid: dad9f0b5-b75e-4b20-b63f-40d09591dcd5
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetView - метод
Возвращает доступное только для чтения представление объекта Vector, то есть интерфейс IVectorView.  
  
## Синтаксис  
  
```  
  
Windows::Foundation::Collections::IVectorView<T>^   
   GetView();  
```  
  
## Возвращаемое значение  
 Объект IVectorView.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)