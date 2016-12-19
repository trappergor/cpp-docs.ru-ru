---
title: "Доступ к библиотеке типов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "библиотеки типов, доступ"
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Доступ к библиотеке типов
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Библиотеки типов элемента управления предоставляют интерфейсы OLE в другой OLE\- зависимым приложениям.  Каждый элемент управления OLE должен иметь библиотеку типов, если один или несколько интерфейсов предоставлять.  
  
 Следующие макросы позволяют элемента управления OLE для предоставления доступа к отдельной библиотеке типов:  
  
### Доступ библиотеки типов  
  
|||  
|-|-|  
|[DECLARE\_OLETYPELIB](../Topic/DECLARE_OLETYPELIB.md)|Объявляет функции\-члена `GetTypeLib` элемента управления OLE \(не используется в объявлении класса\).|  
|[IMPLEMENT\_OLETYPELIB](../Topic/IMPLEMENT_OLETYPELIB.md)|Реализует функции\-члена `GetTypeLib` элемента управления OLE \(не используется в реализации класса\).|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)