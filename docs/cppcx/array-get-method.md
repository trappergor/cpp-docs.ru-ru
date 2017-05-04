---
title: "Array::get - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array::get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Array::get - метод"
ms.assetid: 3bbcd829-35e7-4912-99ba-6ab9de407287
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Array::get - метод
Извлекает ссылку на элемент массива с указанным индексом.  
  
## Синтаксис  
  
```  
  
T& get(  
unsigned int index  
)  const;  
```  
  
#### Параметры  
 `index`  
 Отсчитываемый от нуля индекс, указывающий на элемент в массиве. Минимальный индекс — 0, а максимальный — значение, заданное параметром `size` в [конструкторе массива](../cppcx/array-constructors.md).  
  
## Возвращаемое значение  
 Элемент массива, заданный параметром `index`.  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Platform::Array \- класс](../cppcx/platform-array-class.md)