---
title: "Жизненный цикл диалогового окна | Microsoft Docs"
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
  - "диалоговые окна, жизненный цикл"
  - "жизненный цикл диалоговых окон"
  - "диалоговые окна MFC, жизненный цикл"
  - "модальные диалоговые окна, жизненный цикл"
  - "безрежимные диалоговые окна, жизненный цикл"
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Жизненный цикл диалогового окна
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Во время жизненного цикла диалогового окна, пользователь вызывает диалоговое окно, обычно внутри обработчика команды, который создает и инициализирует объект диалогового окна, пользователь взаимодействует с диалоговым окном, и закрывает диалоговое окно.  
  
 Для модальных окон обработчик собирает все данные, введенные пользователем, как только диалоговое окно закрывает.  Поскольку объект диалогового окна существует после его закрывает окно диалогового окна, можно просто использовать переменные\-члены класса диалогового окна извлекают данные.  
  
 Для немодальных диалоговых окон часто можно извлечь данные из объекта диалогового окна, пока диалоговое окно по\-прежнему является видимым.  В некоторый момент, объект уничтожается диалогового окна. если это происходит зависит от коде.  
  
## Дополнительные сведения  
  
-   [Создание и отображение диалоговые окна](../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [Создание модальные диалоговые окна](../mfc/creating-modal-dialog-boxes.md)  
  
-   [Создание немодальные диалоговые окна](../mfc/creating-modeless-dialog-boxes.md)  
  
-   [С помощью шаблона диалоговых окон в памяти](../mfc/using-a-dialog-template-in-memory.md)  
  
-   [Устанавливать цвет фона диалогового окна](../mfc/setting-the-dialog-box’s-background-color.md)  
  
-   [Для инициализации диалогового окна](../mfc/initializing-the-dialog-box.md)  
  
-   [Обработка сообщений Windows в диалоговом окне](../mfc/handling-windows-messages-in-your-dialog-box.md)  
  
-   [Извлечь данные из объекта диалогового окна](../Topic/Retrieving%20Data%20from%20the%20Dialog%20Object.md)  
  
-   [Закрыть диалоговое окно](../mfc/closing-the-dialog-box.md)  
  
-   [Удалить диалоговое окно](../Topic/Destroying%20the%20Dialog%20Box.md)  
  
-   [Данные диалогового окна \(DDX\) и проверка \(DDV\)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Диалоговые окна " страницы свойств "](../mfc/property-sheets-and-property-pages-mfc.md)  
  
## См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)