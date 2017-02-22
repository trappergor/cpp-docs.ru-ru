---
title: "Поддержка IDispatch и IErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorInfo"
  - "IDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispatch - поддержка класса в ATL"
  - "IDispatchImpl - класс"
  - "IErrorInfo - поддержка класса в ATL"
  - "ISupportErrorInfoImpl - метод"
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Поддержка IDispatch и IErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно использовать класс [IDispatchImpl](../atl/reference/idispatchimpl-class.md) шаблона для предоставления реализации по умолчанию части `IDispatch Interface` всех сдвоенных интерфейсов в объекте.  
  
 Если объект использует интерфейс `IErrorInfo` для оповещения ошибок обратно клиенту, то объект должен поддерживать интерфейс `ISupportErrorInfo Interface`.  Класс [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) шаблона обеспечивает простой способ реализации это если существует только один интерфейс, создающий ошибки в объекте.  
  
## См. также  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)