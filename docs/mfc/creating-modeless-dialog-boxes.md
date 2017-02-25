---
title: "Создание немодальных диалоговых окон | Microsoft Docs"
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
  - "диалоговые окна MFC, создание"
  - "диалоговые окна MFC, безрежимные"
  - "безрежимные диалоговые окна, создание"
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Создание немодальных диалоговых окон
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для немодального диалогового окна необходимо предоставить собственный открытый конструктор в классе диалогового окна.  Для создания безрежимного диалогового окна вызовите свой открытый конструктор и затем вызывать функцию\-член [Создать](../Topic/CDialog::Create.md) объекта диалогового окна, чтобы загрузить ресурс диалогового окна.  Можно вызвать метод **Создать**, во время или после вызова конструктора.  Если ресурс диалогового окна есть свойство **WS\_VISIBLE**, то диалоговое окно отображается немедленно.  Если нет, необходимо вызвать функцию\-член [ShowWindow](../Topic/CWnd::ShowWindow.md).  
  
## См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)