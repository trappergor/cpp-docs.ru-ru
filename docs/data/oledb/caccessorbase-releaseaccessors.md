---
title: "CAccessorBase::ReleaseAccessors | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAccessorBase::ReleaseAccessors"
  - "CAccessorBase.ReleaseAccessors"
  - "ReleaseAccessors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAccessors - метод"
ms.assetid: f08bc88e-0552-4a9c-9c65-b4061094649a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessorBase::ReleaseAccessors
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выпуски доступ, созданные классом.  
  
## Синтаксис  
  
```  
  
      HRESULT ReleaseAccessors(  
   IUnknown* pUnk   
);  
```  
  
#### Параметры  
 *панк*  
 \[in\] указатель на интерфейс **IUnknown** для com\-объекта, для которого доступ были созданы.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Эта функция вызывается из [CAccessorRowset::Close](../Topic/CAccessorRowset::Close.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CAccessorBase](../../data/oledb/caccessorbase-class.md)