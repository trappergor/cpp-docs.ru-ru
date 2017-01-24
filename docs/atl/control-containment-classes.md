---
title: "Control Containment Classes | Microsoft Docs"
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
  - "vc.atl.controls.containment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "control containment classes"
ms.assetid: e0812aee-c078-4ced-b967-247976552b9a
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Control Containment Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие классы предоставляют поддержку включения для размещения элементов управления:  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) предоставляет методы для работы с окно, размещение элемент управления ActiveX.  
  
-   [CAxWindow2T](../Topic/CAxWindow2T%20Class.md) предоставляет методы для работы с окно, размещение элемент управления ActiveX, а также поддерживает для размещения лицензированные элементы управления ActiveX.  
  
-   Вызов [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) методов этого интерфейса для задания свойств внешнего доступа к размещенному отслеживается.  
  
-   Вызов [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) методы в этом интерфейсе, чтобы создать или вложить элемент управления к объекту основного приложения или получить интерфейс из размещенного элемента управления.  
  
## Связанные статьи  
 [Вопросы и ответы вложения элементов управления библиотеки ATL](../atl/atl-control-containment-faq.md)  
  
## См. также  
 [Class Overview](../atl/atl-class-overview.md)