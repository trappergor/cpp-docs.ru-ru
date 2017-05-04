---
title: "Метод Object::ReferenceEquals | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::ReferenceEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform, Object::ReferenceEquals"
ms.assetid: a179e74a-46c7-4bfd-b848-b89ef3ff7197
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Object::ReferenceEquals
Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.  
  
## Синтаксис  
  
```cpp  
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2)  
```  
  
## Параметры  
 obj1  
 Первый из сравниваемых объектов.  
  
 obj2  
 Второй из сравниваемых объектов.  
  
## Возвращаемое значение  
 Значение `true`, если объекты совпадают; в противном случае — значение `false`.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::Object](../cppcx/platform-object-class.md)