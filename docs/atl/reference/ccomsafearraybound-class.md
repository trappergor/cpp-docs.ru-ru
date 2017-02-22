---
title: "CComSafeArrayBound Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComSafeArrayBound"
  - "ATL::CComSafeArrayBound"
  - "CComSafeArrayBound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeArrayBound class"
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComSafeArrayBound Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс программа\-оболочка для структуры [SAFEARRAYBOUND](http://msdn.microsoft.com/ru-ru/303a9bdb-71d6-4f14-8747-84cf84936c6d).  
  
## Синтаксис  
  
```  
  
class CComSafeArrayBound : public SAFEARRAYBOUND  
  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CComSafeArrayBound](../Topic/CComSafeArrayBound::CComSafeArrayBound.md)|Конструктор.|  
|[GetCount](../Topic/CComSafeArrayBound::GetCount.md)|Вызывайте этот метод для возврата числа элементов.|  
|[GetLowerBound](../Topic/CComSafeArrayBound::GetLowerBound.md)|Вызовите этот метод, чтобы вернуть нижнюю границу.|  
|[GetUpperBound](../Topic/CComSafeArrayBound::GetUpperBound.md)|Вызывайте этот метод для возврата верхней границы.|  
|[SetCount](../Topic/CComSafeArrayBound::SetCount.md)|Вызовите этот метод, чтобы задать число элементов.|  
|[SetLowerBound](../Topic/CComSafeArrayBound::SetLowerBound.md)|Вызовите этот метод, чтобы задать нижнюю границу.|  
  
### Операторы  
  
|||  
|-|-|  
|[оператор \=](../Topic/CComSafeArrayBound::operator%20=.md)|Задает `CComSafeArrayBound` новое значение.|  
  
## Заметки  
 Этот класс программа\-оболочка для структуры **SAFEARRAYBOUND**, используемой [CComSafeArray](../Topic/CComSafeArray%20Class.md).  Он предоставляет методы для выполнения запросов и установка из строчных и меньшие границы одного измерения `CComSafeArray` объект и количество элементов.  Многомерный объект `CComSafeArray` использует массив объектов `CComSafeArrayBound`, по одному для каждого измерения.  Поэтому при использовании таких методов, как [GetCount](../Topic/CComSafeArrayBound::GetCount.md), учтите, что этот метод не возвращает общее число элементов в многомерной таблице.  
  
 **Header:** atlsafe.h  
  
## Требования  
 **Header:** atlsafe.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)