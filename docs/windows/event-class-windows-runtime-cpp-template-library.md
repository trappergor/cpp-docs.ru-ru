---
title: "Класс Event (библиотека шаблонов C++ среды выполнения Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Event"
dev_langs: 
  - "C++"
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс Event (библиотека шаблонов C++ среды выполнения Windows)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет событие.  
  
## Синтаксис  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор Event::Event \(библиотека шаблонов C\+\+ среды выполнения Windows\)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Инициализирует новый экземпляр класса Event.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор Event::operator\=](../windows/event-operator-assign-operator.md)|Присваивает указанную ссылку на событие текущему экземпляру Event.|  
  
## Иерархия наследования  
 `HandleT`  
  
 `Event`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)