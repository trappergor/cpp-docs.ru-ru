---
title: "Структура MixIn | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::MixIn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MixIn - структура"
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Структура MixIn
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Гарантирует, что класс среды выполнения является производным от интерфейсов [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], если таковые имеются, и интерфейсов классической модели COM.  
  
## Синтаксис  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### Параметры  
 `Derived`  
 Тип, производный от структуры [Реализации](../Topic/Implements%20Structure.md).  
  
 `MixInType`  
 Базовый тип.  
  
 `hasImplements`  
 `true`, если `MixInType` создан от текущей реализации базового типа; в противном случае — `false`.  
  
## Примечания  
 Если класс является производным как от [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], так и от интерфейсов модели COM класса, список объявления класса сначала должен перечислить все интерфейсы [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], а затем все интерфейсы классической модели COM.  MixIn обеспечивает, что интерфейсы определяются в правильном порядке.  
  
## Иерархия наследования  
 `MixIn`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)