---
title: "nonextensible Attribute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "nonextensible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "сдвоенные интерфейсы, nonextensible attribute"
  - "nonextensible attribute"
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# nonextensible Attribute
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если сдвоенный интерфейс не будет расширен во время выполнения \(то есть не обеспечите методы или свойства в **IDispatch::Invoke**, которые не доступны через vtable\), необходимо применить атрибут **nonextensible** в определение интерфейса.  Этот атрибут предоставляет информацию языки клиента \(Visual Basic\), которые можно использовать для включения полную проверку кода во время компиляции.  Если этот атрибут не задан, то ошибки не будут иметь возможность оставаться скрытыми в коде клиента до времени выполнения.  
  
 Дополнительные сведения об атрибуте **nonextensible** и примере см. в разделе [nonextensible](../Topic/nonextensible.md).  
  
## См. также  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)