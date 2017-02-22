---
title: "Конструктор RoInitializeWrapper::RoInitializeWrapper | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# Конструктор RoInitializeWrapper::RoInitializeWrapper
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует новый экземпляр класса RoInitializeWrapper.  
  
## Синтаксис  
  
```cpp  
RoInitializeWrapper(  
   RO_INIT_TYPE flags)  
  
```  
  
#### Параметры  
 `flags`  
 Одно из перечислений RO\_INIT\_TYPE, определяющее поддержку, обеспеченную [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Примечания  
 Класс RoInitializeWrapper вызывает Windows::Foundation::Initialize\(*flags*\).  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HandleT](../Topic/HandleT%20Class.md)