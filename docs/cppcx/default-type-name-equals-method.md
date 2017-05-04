---
title: "Метод default::(type_name)::Equals | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::Equals"
dev_langs: 
  - "C++"
ms.assetid: 4450f835-06fc-4758-8d0a-72cf00007873
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод default::(type_name)::Equals
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
  
 **Пространство имен:** по умолчанию  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Пространство имен default](../cppcx/default-namespace.md)