---
title: "Purpose of Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], about attributes"
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Purpose of Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Атрибуты расширяют C\+\+ в направлениях не в данный момент возможно, не нарушая классического структуру языка.  Атрибуты позволяют поставщикам \(отдельных библиотек DLL\), чтобы расширить функциональные возможности языка динамически.  Основное назначение атрибутов упростить создание компонентов COM, в дополнение к увеличению производительность разработчиков уровня компонента.  Атрибуты можно применять к практически любой конструкции C\+\+, например, классы, элементы данных или функции\-члены.  Следующее выделение преимуществ, предоставляемых этой новой технологии.  
  
-   Предоставляет простое знакомое и соглашение о вызовах.  
  
-   Использует вставленный код, который, в отличие от макросы, отладчиком.  
  
-   Обеспечивает удобный наследование от базовых классов, не отяготительных подробности реализации.  
  
-   Заменяет большие объемы необходимого кода IDL компонентом COM, в которых число сжатых атрибутов.  
  
 Например, чтобы реализовать простой приемник событий для универсального класса библиотеки ATL можно применить [event\_receiver](../windows/event-receiver.md) атрибут к определенному классу как  `CMyReceiver`.   Event\_receiver атрибут затем компилироваться компилятором Visual C\+\+, который представляет правильный код в объектный файл.  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 Затем можно настроить **CMyReceiver** методы  `handler1` и  `handler2` обработка событий \(с помощью функции внутреннеприсущую  [\_\_hook](../cpp/hook.md)\) из источника событий, которые можно создать с помощью  [event\_source](../windows/event-source.md).  
  
## См. также  
 [Concepts](../windows/attributed-programming-concepts.md)