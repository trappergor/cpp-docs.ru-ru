---
title: "Windows Support Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.windows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, окна"
  - "windows [C++], ATL - библиотека"
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Windows Support Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие классы предоставляют поддержку для окон:  
  
-   [\_U\_MENUorID](../atl/reference/u-menuorid-class.md) Предоставляет программы\-оболочки для **CreateWindow** и **CreateWindowEx**.  
  
-   [CWindow](../atl/reference/cwindow-class.md) содержит методы для работы с окном.  `CWindow` является базовым классом для классов `CWindowImpl`, `CDialogImpl` и `CContainedWindow`.  
  
-   [CWindowImpl](../Topic/CWindowImpl%20Class.md) реализует окно, основанную на классе нового окна.  Позволяет также подклассу или суперклассу окно.  
  
-   [CDialogImpl](../Topic/CDialogImpl%20Class.md) реализующий диалоговое окно.  
  
-   [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md) реализует модальное диалоговое окно modeless \(или\), то управления ActiveX узлов.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) реализует модальное диалоговое окно modeless \(или\) с базовой функциональностью.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) управляет окно, размещение элемент управления ActiveX.  
  
-   [CAxWindow2T](../Topic/CAxWindow2T%20Class.md) предоставляет методы для работы с окно, размещение элемент управления ActiveX, а также поддерживает для размещения лицензированные элементы управления ActiveX.  
  
-   [CContainedWindowT](../Topic/CContainedWindowT%20Class.md) реализует окно, содержащихся в другой объект.  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) управляет сведения класса нового окна.  
  
-   Обозреватель [CDynamicChain](../atl/reference/cdynamicchain-class.md) цепочки динамического сопоставления сообщения.  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md) позволяет объекту предоставить его сопоставления сообщения с другими объектами.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) предоставляет простой метод стандартизации признаки объекта окна библиотеки ATL.  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) предоставляет значения по умолчанию для стилей окна и расширенных стилей, используемых для создания окна.  Эти значения добавлены, используя логически\- ИЛИ оператор, к значениям предоставленным во время создания окна.  
  
## Связанные статьи  
 [Классы окна библиотеки ATL](../Topic/ATL%20Window%20Classes.md)  
  
 [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)  
  
## См. также  
 [Class Overview](../atl/atl-class-overview.md)   
 [Message Map Macros](../atl/reference/message-map-macros-atl.md)   
 [Window Class Macros](../atl/reference/window-class-macros.md)