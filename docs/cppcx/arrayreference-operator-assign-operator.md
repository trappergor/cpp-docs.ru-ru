---
title: "Оператор ArrayReference::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 131a4612-d66b-48e4-90af-c665ccc0cce4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор ArrayReference::operator=
Присваивает указанный объект текущему объекту [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) с помощью семантики перемещения.  
  
## Синтаксис  
  
```cpp  
  
ArrayReference& operator=(ArrayReference&& __otherArg);  
  
```  
  
#### Параметры  
 `__ otherArg`  
 Присваивает перемещенный объект текущему объекту `ArrayReference`.  
  
## Возвращаемое значение  
 Ссылка на объект типа `ArrayReference`.  
  
## Заметки  
 `Platform::ArrayReference` — это стандартный шаблон класса C\+\+, а не ссылочный класс.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::ArrayReference](../cppcx/platform-arrayreference-class.md)