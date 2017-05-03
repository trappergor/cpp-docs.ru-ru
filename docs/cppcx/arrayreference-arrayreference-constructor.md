---
title: "Конструктор ArrayReference::ArrayReference | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::ArrayReference"
dev_langs: 
  - "C++"
ms.assetid: 9fc7dfcf-47af-40ba-a697-da476fb90efc
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Конструктор ArrayReference::ArrayReference
Инициализирует новый экземпляр класса [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md).  
  
## Синтаксис  
  
```cpp  
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);  
ArrayReference(ArrayReference&& otherArg)  
  
```  
  
#### Параметры  
 `dataArg`  
 Указатель на данные массива.  
  
 `sizeArg`  
 Количество элементов в исходном массиве.  
  
 `otherArg`  
 Объект `ArrayReference`, данные которого будут перемещены для инициализации нового экземпляра.  
  
## Заметки  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::ArrayReference](../cppcx/platform-arrayreference-class.md)   
 [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)