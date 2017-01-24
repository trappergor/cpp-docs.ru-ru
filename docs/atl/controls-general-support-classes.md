---
title: "Controls: General Support Classes | Microsoft Docs"
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
  - "vc.atl.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления [ATL]"
  - "general support classes"
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Controls: General Support Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие классы предоставляют общую поддержку для элементов управления библиотеки ATL:  
  
-   [CComControl](../atl/reference/ccomcontrol-class.md) состоит из функций и элементов данных к элементам управления, которые требуются вспомогательной библиотеки ATL.  
  
-   [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) предоставляет методы, необходимые для элементов управления.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) предоставляет основные методы, с помощью которых контейнер взаимодействует с элементом управления.  Управляет активация и деактивация элементов управления в\- размещения.  
  
-   Инициализация зернокомбайнов [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) в отдельный вызов, чтобы помочь контейнерам избежать задержки при управления загрузки.  
  
-   [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) предоставляет минимальные возможности мыши, в противном случае неактивного элемента управления.  
  
## Пример программы  
 [ATLFire](../top/visual-cpp-samples.md)  
  
## Связанные статьи  
 [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)  
  
## См. также  
 [Class Overview](../atl/atl-class-overview.md)