---
title: "Which ATL Classes Facilitate ActiveX Control Containment? | Microsoft Docs"
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
  - "контейнер для элементов ActiveX [C++], ATL control hosting"
  - "hosting controls using ATL"
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Which ATL Classes Facilitate ActiveX Control Containment?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Код элемента управления\- размещения библиотеки ATL не требует использовании все классы библиотеки ATL. можно просто создать поле **"AtlAxWin80"** и использовать API размещения если требуемый элемент управления\- \(дополнительные сведения см. в разделе [API Размещения, что Элемент управления\- библиотеки ATL?](../atl/what-is-the-atl-control-hosting-api-q.md)\).  Однако следующие классы реализуют включения функции проще использовать.  
  
|Класс|Описание|  
|-----------|--------------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|Создает программу\-оболочку окно **"AtlAxWin80"**, предоставляя методы для создания окна создание элемента управления и\/или вложить элемент управления в окно и получить указатели интерфейса объекта основного приложения.|  
|[CAxWindow2T](../Topic/CAxWindow2T%20Class.md)|Создает программу\-оболочку окно **"AtlAxWinLic80"**, предоставляя методы для создания окна создание элемента управления и\/или вложить лицензированный элемент управления в окно и получить указатели интерфейса объекта основного приложения.|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Действует как базовый класс для классов элементов управления ActiveX, основанных на ресурс диалогового окна.  Такие элементы управления могут содержать другие элементы управления ActiveX.|  
|[CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md)|Действует как базовый класс для классов диалоговых окон, основанных на ресурс диалогового окна.  Эти диалоговые окна могут содержать управления ActiveX.|  
|[CWindow](../atl/reference/cwindow-class.md)|Предоставляет метод, [GetDlgControl](../Topic/CWindow::GetDlgControl.md), которое возвращает указатель интерфейса на элементе управления, заданным идентификатором его окна основного приложения.  Кроме того, программы\-оболочки API Windows, предоставляемые `CWindow` обычно выполняют управление окнами.|  
  
## См. также  
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)