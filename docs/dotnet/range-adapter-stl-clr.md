---
title: "range_adapter (STL/CLR) | Microsoft Docs"
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
  - "cliext::range_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "range_adapter - класс [STL/CLR]"
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# range_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона, который создается пара итераторов, используемые для реализации несколько интерфейсов \(BCL\) библиотеки базового класса.  Используется range\_adapter для управления диапазон STL\/CLR, как коллекции BCL.  
  
## Синтаксис  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### Параметры  
 Iter  
 Тип, связанный с создаватьыми программу\-оболочку итераторами.  
  
## Члены  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[range\_adapter::range\_adapter](../dotnet/range-adapter-range-adapter-stl-clr.md)|Создает объект адаптера.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[range\_adapter::operator\=](../dotnet/range-adapter-operator-assign-stl-clr.md)|Заменяет сохраненного пары итератора.|  
  
## Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|--------------|  
|<xref:System.Collections.IEnumerable>|Выполняет перебор элементов коллекции.|  
|<xref:System.Collections.ICollection>|Поддерживает группу в составе элементы.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Типизированные выполняет перебор элементов коллекции.|  
|<xref:System.Collections.Generic.ICollection%601>|Поддерживает группу в составе типизированных элементов.|  
  
## Заметки  
 Range\_adapter сохраняет пару итераторов, которые, в свою очередь, разделяющие последовательность элементов.  Объект реализует 4 интерфейса BCL, позволяющие перебирать элементы в порядке.  Используется этот класс шаблона для управления диапазоны STL\/CLR подобно контейнеры BCL.  
  
## Требования  
 **Заголовок:**\<cliext\/adapter\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md)   
 [make\_collection](../dotnet/make-collection-stl-clr.md)