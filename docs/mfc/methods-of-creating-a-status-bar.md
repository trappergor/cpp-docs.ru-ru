---
title: "Способы создания строки состояния | Microsoft Docs"
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
  - "CStatusBar - класс, или CStatusBarCtrl"
  - "CStatusBarCtrl - класс, создание"
  - "CStatusBarCtrl - класс, или CStatusBar"
  - "методы [MFC]"
  - "методы [MFC], создание строк состояния"
  - "строки состояния, создание"
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Способы создания строки состояния
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC предоставляет 2 класса для создания строки состояния. [CStatusBar](../mfc/reference/cstatusbar-class.md) и [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) \(API, создания общего элемента управления Windows\).  `CStatusBar` предоставляет всю функциональность общего элемента управления строки состояния, автоматически взаимодействует с меню и инструментами, и он обрабатывает большую часть необходимых параметров и структур общего элемента управления автоматически; однако, если полученный исполняемый файл обычно будет больше, чем у созданного с помощью `CStatusBarCtrl`.  
  
 `CStatusBarCtrl` обычно приводит к уменьшению исполняемый файл, который может быть использован `CStatusBarCtrl`, если не планируется интеграции строку состояния в архитектуру MFC.  Если планируется использовать `CStatusBarCtrl` и интегрировать строку состояния в архитектуру MFC, необходимо соблюдать осторожность дополнительный для связи для манипулирования элементами управления строки состояния в MFC.  Это сообщение не сложно; однако дополнительную работу, не нужен при использовании `CStatusBar`.  
  
 Visual C\+\+ 2 C предоставляет два способа использования общего элемента управления строки состояния.  
  
-   Создайте строку состояния с помощью `CStatusBar`, а затем вызвать [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md), чтобы получить доступ к функциям элемента `CStatusBarCtrl`.  
  
-   Создайте строку состояния с помощью конструктора [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md).  
  
 Любой метод выдаст доступ к функциям элемента элемента управления в строке состояния.  При вызове `CStatusBar::GetStatusBarCtrl`, оно возвращает ссылку на объект `CStatusBarCtrl` таким образом можно использовать любой набор функции\-члены.  В разделе [CStatusBar](../mfc/reference/cstatusbar-class.md) сведения о построении и создать строку состояния с помощью `CStatusBar`.  
  
## См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)