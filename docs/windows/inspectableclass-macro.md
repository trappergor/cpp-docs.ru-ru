---
title: "Макрос InspectableClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::InspectableClass"
dev_langs: 
  - "C++"
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Макрос InspectableClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает имя и уровень доверия класса времени выполнения.  
  
## Синтаксис  
  
```cpp  
  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
  
```  
  
#### Параметры  
 `runtimeClassName`  
 Полное текстовое имя класса среды выполнения.  
  
 `trustLevel`  
 Одно из значений перечисления [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx).  
  
## Заметки  
 Макрос `InspectableClass` может использоваться только с типами [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)