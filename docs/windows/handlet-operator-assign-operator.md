---
title: "Оператор HandleT::operator= | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= - оператор"
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор HandleT::operator=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Перемещает значение указанного объекта HandleT в текущий объект HandleT.  
  
## Синтаксис  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### Параметры  
 `h`  
 Ссылка rvalue на дескриптор.  
  
## Возвращаемое значение  
 Ссылка на текущий объект HandleT.  
  
## Примечания  
 Эта операция делает недействительным объект HandleT, указанный параметром `h`.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HandleT](../Topic/HandleT%20Class.md)