---
title: "ATL Connection Point Example | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "точки подключения [C++], примеры"
  - "examples [ATL]"
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ATL Connection Point Example
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом примере показан объект, поддержки [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) как исходящий интерфейс:  
  
 [!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/CPP/atl-connection-point-example_1.h)]  
  
 При указании `IPropertyNotifySink` как исходящий интерфейс, можно вместо этого использовать класс [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md)`IConnectionPointImpl`.  Примеры.  
  
 [!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/CPP/atl-connection-point-example_2.h)]  
  
## См. также  
 [Точка подключения](../atl/atl-connection-points.md)