---
title: "Класс unorm | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::unorm"
  - "amp/Concurrency::graphics::unorm"
dev_langs: 
  - "C++"
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
caps.latest.revision: 8
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс unorm
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Представляет число unorm.  Каждый элемент является числом с плавающей запятой в диапазоне \[0.0f, 1.0f\].  
  
## Синтаксис  
  
```  
class unorm;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор unorm::unorm](../Topic/unorm::unorm%20Constructor.md)|Перегружен.  Конструктор по умолчанию.  Инициализация значением 0.0f.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|Оператор unorm::operator\-\-||  
|Оператор unorm::operator float|Оператор преобразования.  Преобразует число unorm в значение с плавающей запятой.|  
|Оператор unorm::operator\*\=||  
|Оператор unorm::operator\/\=||  
|Оператор unorm::operator\+\+||  
|Оператор unorm::operator\+\=||  
|Оператор unorm::operator\=||  
|Оператор unorm::operator\-\=||  
  
## Иерархия наследования  
 `unorm`  
  
## Требования  
 **Заголовок:** amp\_short\_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
## См. также  
 [Пространство имен Concurrency::graphics](../../../parallel/amp/reference/concurrency-graphics-namespace.md)