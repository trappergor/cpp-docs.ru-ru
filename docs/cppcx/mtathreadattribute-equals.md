---
title: "MTAThreadAttribute::Equals | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::MTAThreadAttribute::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MTAThreadAttribute::Equals"
ms.assetid: 9943307a-9bbb-4583-a627-7317123bd3ac
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MTAThreadAttribute::Equals
Определяет, равен ли заданный объект текущему объекту.  
  
## Синтаксис  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
## Параметры  
 obj  
 Объект для сравнения.  
  
## Возвращаемое значение  
 Значение `true`, если объекты равны, в противном случае — значение `false`.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::MTAThreadAttribute](../cppcx/platform-mtathreadattribute-class.md)