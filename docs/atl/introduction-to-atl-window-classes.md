---
title: "Introduction to ATL Window Classes | Microsoft Docs"
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
  - "window classes"
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Introduction to ATL Window Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие классы библиотеки ATL предназначены для реализации и управлять окна:  
  
-   [CWindow](../atl/reference/cwindow-class.md) можно вложить дескриптор окна для объекта `CWindow`.  После этого вызовите методы `CWindow` управлять окно.  
  
-   [CWindowImpl](../Topic/CWindowImpl%20Class.md) позволяет реализовать новое окно и процесс сообщения с сопоставлением сообщения.  Можно создать поле, основанную на классе суперклассе существующий класс или подклассе нового окна существующее окно.  
  
-   [CDialogImpl](../Topic/CDialogImpl%20Class.md) позволяет реализовать сообщения режимного или немодального диалогового окна и процесса с сопоставлением сообщения.  
  
-   [CContainedWindowT](../Topic/CContainedWindowT%20Class.md) класс, реализующий prebuilt окно которого сопоставление сообщения содержится в другом классе.  Использование `CContainedWindowT` позволяют централизовать обработка сообщений в одном классе.  
  
-   [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md) позволяет реализовать \(или модальное диалоговое окно modeless\), управления ActiveX узлов.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) позволяет реализовать модального диалогового окна с базовой функциональностью.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) позволяет реализовать окно, размещение элемент управления ActiveX.  
  
-   [CAxWindow2T](../Topic/CAxWindow2T%20Class.md) позволяет реализовать окно, размещение лицензированное элемент управления ActiveX.  
  
 В дополнение к конкретным классам окна библиотеки ATL предоставляет несколько классов, предназначенных для выполнения реализацию объекта окна библиотеки ATL.  К ним относится следующее.  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) управляет сведения класса нового окна.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) и [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) обеспечивают простой метод стандартизации признаки объекта окна библиотеки ATL.  
  
## См. также  
 [Классы окон](../Topic/ATL%20Window%20Classes.md)