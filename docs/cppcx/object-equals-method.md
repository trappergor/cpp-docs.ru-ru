---
title: "Метод Object::Equals | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Платформа, Object::Equals"
ms.assetid: 263ccd41-2a29-4716-a47e-4bf2883f3403
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Object::Equals
Определяет, равен ли заданный объект текущему объекту.  
  
## Синтаксис  
  
```cpp  
  
bool Equals(  
    Object^ obj  
)  
```  
  
## Параметры  
 obj  
 Объект для сравнения.  
  
## Возвращаемое значение  
 Значение `true`, если объекты равны; в противном случае — значение `false`.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Object](../cppcx/platform-object-class.md)