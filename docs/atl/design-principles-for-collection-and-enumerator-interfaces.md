---
title: "Design Principles for Collection and Enumerator Interfaces | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collection interfaces"
  - "enumerator interfaces"
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Design Principles for Collection and Enumerator Interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Различные основные принципы разработки за каждым типом интерфейса:  
  
-   Интерфейс коллекции предоставляет *прямой доступ* к *одному* элементу в коллекции с помощью метода **item**, он позволяет клиентам определить, сколько элементов в коллекции посредством свойства **Счетчик** и часто позволяет клиентам добавлять и удалять элементы.  
  
-   Интерфейс перечислителя предоставляет *серийный* доступ к *нескольким* элементам в коллекции, он не позволяет клиенту узнать число элементов в коллекции \(до тех пор, пока не будет остановлена возвращает перечислитель элементов\), и он не предоставляет никакой способ добавлять или удалять элементы.  
  
 Каждый тип интерфейса должен играть в другую роль безопасности доступа к элементам в коллекции.  
  
## См. также  
 [Коллекции и перечислители](../atl/atl-collections-and-enumerators.md)