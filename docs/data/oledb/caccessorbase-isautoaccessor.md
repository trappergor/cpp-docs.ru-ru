---
title: "CAccessorBase::IsAutoAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IsAutoAccessor"
  - "CAccessorBase.IsAutoAccessor"
  - "CAccessorBase::IsAutoAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsAutoAccessor - метод"
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessorBase::IsAutoAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает значение true, если данные автоматически получены для доступа во время операции перемещения.  
  
## Синтаксис  
  
```  
  
      bool IsAutoAccessor(  
   ULONG nAccessor   
) const;  
```  
  
#### Параметры  
 `nAccessor`  
 \[in\] число нулевым смещения для доступа.  
  
## Возвращаемое значение  
 Возвращает значение **true**, если объект доступа автоматическим.  В противном случае возвращается значение **false**.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CAccessorBase](../../data/oledb/caccessorbase-class.md)