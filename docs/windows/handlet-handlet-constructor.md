---
title: "Конструктор HandleT::HandleT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleT, конструктор"
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Конструктор HandleT::HandleT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует новый экземпляр класса HandleT.  
  
## Синтаксис  
  
```  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
#### Параметры  
 `h`  
 Дескриптор.  
  
## Примечания  
 Первый конструктор инициализирует объект HandleT, который не является допустимым дескриптором объекта.  Второй конструктор создает новый объект HandleT из параметра `h`.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HandleT](../Topic/HandleT%20Class.md)