---
title: "Creating an Aggregated Object | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], создание"
  - "aggregation [C++], creating aggregated objects"
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Creating an Aggregated Object
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Агрегат вызовы делегатов **IUnknown** реализация указатель **IUnknown** внешнего объекта к внутреннему объекту.  
  
### Создание объединенный объект  
  
1.  Добавить указатель **IUnknown** к конкретному объекту класса и инициализируйте его в **NULL** в конструкторе.  
  
2.  Переопределение [FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md) чтобы создать статистическое выражение.  
  
3.  Используйте указатель **IUnknown**, указанный на шаге 1, в качестве второго параметра для макросов [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md).  
  
4.  Переопределение [FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md) для освобождения указатель **IUnknown**.  
  
> [!NOTE]
>  При использовании и освобождаете интерфейс из статистически вычислениеого объекта во время `FinalConstruct`, необходимо добавить макрос [DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md) к определению объекта класса.  
  
## См. также  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)