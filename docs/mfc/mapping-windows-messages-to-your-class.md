---
title: "Сопоставление сообщений Windows с классом | Microsoft Docs"
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
  - "сопоставления, сообщения в класс диалоговых окон"
  - "схемы сообщений [C++], в класс диалоговых окон"
  - "схемы сообщений [C++], сопоставление сообщений Windows классам"
  - "сообщения в класс диалоговых окон"
  - "сообщения в класс диалоговых окон, сопоставление"
  - "диалоговые окна MFC, сообщения Windows"
  - "сообщения Windows [C++], сопоставление в классах диалоговых окон"
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Сопоставление сообщений Windows с классом
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если требуется диалоговом окне обработки сообщений Windows, переопределите соответствующие функции обработчика.  Для этого используется окно свойств в [сопоставление сообщения](../Topic/Mapping%20Messages%20to%20Functions.md) в класс диалогового окна.  Это вносит запись сопоставления сообщений для всех сообщений и добавляет функции\-члены обработчика сообщений в класс.  Используйте редактор исходного кода Visual C\+\+ для написания кода в обработчиках сообщений.  
  
 Можно также переопределить функции\-члены [CDialog](../mfc/reference/cdialog-class.md) и его базовых классов, в особенности [CWnd](../Topic/CWnd%20Class.md).  
  
## Дополнительные сведения  
  
-   [Обработка сообщений и сопоставление](../mfc/message-handling-and-mapping.md)  
  
-   [Часто переопределенная функции\-члена](../mfc/commonly-overridden-member-functions.md)  
  
-   [Часто добавлены функции\-члены](../Topic/Commonly%20Added%20Member%20Functions.md)  
  
## См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)