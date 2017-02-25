---
title: "CDefaultCharTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDefaultCharTraits"
  - "ATL::CDefaultCharTraits<T>"
  - "ATL.CDefaultCharTraits"
  - "ATL.CDefaultCharTraits<T>"
  - "ATL::CDefaultCharTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultCharTraits class"
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDefaultCharTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет 2 статических функций преобразования знаков между прописными буквами и нижним регистром.  
  
## Синтаксис  
  
```  
  
      template <  
   typename T  
>  
class CDefaultCharTraits  
```  
  
#### Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDefaultCharTraits::CharToLower](../Topic/CDefaultCharTraits::CharToLower.md)|\(Статический\) Эта функция вызывается для преобразования символов в прописными буквами.|  
|[CDefaultCharTraits::CharToUpper](../Topic/CDefaultCharTraits::CharToUpper.md)|\(Статический\) Эта функция вызывается для преобразования символов в нижний регистр.|  
  
## Заметки  
 Этот класс предоставляет функции, которые используются классом [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)