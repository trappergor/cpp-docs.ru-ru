---
title: "Управляемые типы (C++/CL) | Microsoft Docs"
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
  - "__gc - типы"
  - "типы [C++], среда CLR"
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Управляемые типы (C++/CL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Синтаксис для объявления управляемых типов, а также создания и использования объектов данных типов претерпел значительные изменения в [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] по сравнению с управляемыми расширениями для C\+\+.  Это было сделано для повышения уровня интеграции этих типов в рамках системы типов ISO\-C\+\+.  Реализованные изменения подробно описаны в следующих подразделах.  
  
## Содержание  
 [Объявление управляемых типов классов](../dotnet/declaration-of-a-managed-class-type.md)  
 Рассматриваются способы объявления управляемых типов `class`, `struct` и `interface`.  
  
 [Объявление объекта ссылочного класса в среде CLR](../dotnet/declaration-of-a-clr-reference-class-object.md)  
 Рассматриваются способы объявления объекта ссылочного типа класса с помощью дескриптора отслеживания.  
  
 [Объявление массива CLR](../dotnet/declaration-of-a-clr-array.md)  
 Объясняются способы объявления и инициализации массива.  
  
 [Изменения в последовательности инициализации конструктора](../Topic/Changes%20in%20Constructor%20Initialization%20Order.md)  
 Рассматриваются основные изменения в порядке инициализации классов в конструкторе.  
  
 [Изменения в семантике деструктора](../dotnet/changes-in-destructor-semantics.md)  
 Рассматривается неопределенное завершение \(`Finalize` или `Dispose`\), влияние на объекты ссылочного типа, а также использование явного метода `Finalize`.  
  
 **Примечание.** Делегаты рассматриваются в подразделе [Делегаты и события](../dotnet/delegates-and-events.md) вместе с членами события внутри класса \(общий раздел [Объявления членов в пределах класса или интерфейса \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)\).  
  
## См. также  
 [Основы миграции C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md)   
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Массивы](../windows/arrays-cpp-component-extensions.md)