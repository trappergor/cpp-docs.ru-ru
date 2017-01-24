---
title: "Инициализация диалогового окна | Microsoft Docs"
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
  - "инициализация диалоговых окон"
  - "диалоговые окна MFC, инициализация"
  - "модальные диалоговые окна, инициализация"
  - "безрежимные диалоговые окна, инициализация"
  - "OnInitDialog - метод"
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Инициализация диалогового окна
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

После создания диалогового окна и все его элементов управления, но непосредственно перед вызовом диалогового окна \(любого типа\) отображается на экране, функцию\-член [OnInitDialog](../Topic/CDialog::OnInitDialog.md) объекта вызывается диалогового окна.  Для модального диалогового окна это происходит во время вызова `DoModal`.  Для немодального диалогового окна `OnInitDialog` вызывается, когда вызывается метод **Создать**.  Как правило, переопределите `OnInitDialog` для инициализации управления диалогового окна, как устанавливать исходный текст поля ввода.  Следует вызвать функцию\-член `OnInitDialog` базового класса, `CDialog`, из переопределения `OnInitDialog`.  
  
 Если нужно изменить цвет фона диалогового окна \(и два других диалоговых окон в приложении\) см. в разделе [Устанавливать цвет фона диалогового окна](../mfc/setting-the-dialog-box’s-background-color.md).  
  
## См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)