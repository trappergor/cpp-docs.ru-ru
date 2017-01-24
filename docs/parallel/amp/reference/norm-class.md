---
title: "Класс norm | Microsoft Docs"
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
  - "amp_short_vectors/Concurrency::graphics::norm"
dev_langs: 
  - "C++"
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: 8
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс norm
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Представляет норму комплексного числа.  Каждый элемент является числом с плавающей точкой в диапазоне \[\- 1.0f, 1.0f\].  
  
## Синтаксис  
  
```  
class norm;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор norm::norm](../Topic/norm::norm%20Constructor.md)|Перегружен.  Конструктор по умолчанию.  Инициализация значением 0.0f.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|Оператор norm::operator\-||  
|Оператор norm::operator\-\-||  
|Оператор norm::operator float|Оператор преобразования.  Преобразование нормы комплексного числа в значение с плавающей точкой.|  
|Оператор norm::operator\*\=||  
|Оператор norm::operator\/\=||  
|Оператор norm::operator\+\+||  
|Оператор norm::operator\+\=||  
|Оператор norm::operator\=||  
|Оператор norm::operator\-\=||  
  
## Иерархия наследования  
 `norm`  
  
## Требования  
 **Заголовок:** amp\_short\_vectors.h  
  
 **Пространство имен:** Concurrency::graphics  
  
## См. также  
 [Пространство имен Concurrency::graphics](../../../parallel/amp/reference/concurrency-graphics-namespace.md)