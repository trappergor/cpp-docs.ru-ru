---
title: "Способы создания панели инструментов | Microsoft Docs"
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
  - "CToolBar - класс, создание панелей инструментов"
  - "CToolBarCtrl - класс, и класс CToolBar"
  - "CToolBarCtrl - класс, создание панелей инструментов"
  - "Панели инструментов MFC"
  - "элементы управления панели инструментов [MFC]"
  - "элементы управления панели инструментов [MFC], создание"
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Способы создания панели инструментов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC предоставляет 2 класса для создания панелей инструментов: [CToolBar](../mfc/reference/ctoolbar-class.md) и [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) \(API, создания общего элемента управления Windows\).  `CToolBar` предоставляет всю функциональность общего элемента управления панели инструментов, а также обрабатывает большую часть необходимых параметров и структур общего элемента управления автоматически; однако, если полученный исполняемый файл обычно будет больше, чем у созданного с помощью `CToolBarCtrl`.  
  
 `CToolBarCtrl` обычно приводит к уменьшению исполняемый файл, который может быть использован `CToolBarCtrl`, если не планируется инструмент архитектуры интеграции в MFC.  Если планируется использовать `CToolBarCtrl` и интегрировать инструмент архитектуры в MFC, необходимо соблюдать осторожность дополнительный для связи манипуляции элемента управления панели инструментов в MFC.  Это сообщение не сложно; однако дополнительную работу, не нужен при использовании `CToolBar`.  
  
 Visual C\+\+ 2 C предоставляет два способа использования общего элемента управления панели инструментов.  
  
-   Создайте панель инструментов с помощью `CToolBar`, а затем вызвать [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md), чтобы получить доступ к функциям элемента `CToolBarCtrl`.  
  
-   Создайте панель инструментов с помощью конструктора [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md).  
  
 Любой метод выдаст доступ к функциям элемента элемента управления панели инструментов.  При вызове `CToolBar::GetToolBarCtrl`, оно возвращает ссылку на объект `CToolBarCtrl` таким образом можно использовать любой набор функции\-члены.  В разделе [CToolBar](../mfc/reference/ctoolbar-class.md) сведения о построении и создать панель инструментов с помощью `CToolBar`.  
  
## См. также  
 [Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)