---
title: "Операторы приведения | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "операторы приведения"
  - "операторы [C++], приведение"
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Операторы приведения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Некоторые операторы приведения типа используются только в языке C\+\+.  Эти операторы позволяют устранить неоднозначность и возможности допустить ошибку, которые характеры для приведения типов в стиле языка C.  Эти операторы перечислены ниже.  
  
-   [dynamic\_cast](../cpp/dynamic-cast-operator.md) Используется для преобразования полиморфных типов.  
  
-   [static\_cast](../cpp/static-cast-operator.md) Используется для преобразования неполиморфных типов.  
  
-   [const\_cast](../Topic/const_cast%20Operator.md) Используется для удаления атрибутов `const`, `volatile` и `__unaligned`.  
  
-   [reinterpret\_cast](../cpp/reinterpret-cast-operator.md) Используется для простой повторной интерпретации разрядов.  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) Используется для создания проверяемых MSIL.  
  
 В операторах `const_cast` и `reinterpret_cast` сохраняется опасность допустить ошибку \(как в операторах приведения типов в C\), поэтому их следует использовать только в тех случаях, когда обойтись без них не удается.  Однако они необходимы, чтобы полностью заменить приведения старого стиля.  
  
## См. также  
 [Приведение](../cpp/casting.md)