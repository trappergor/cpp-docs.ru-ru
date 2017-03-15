---
title: "Типы сообщений, связанных с объектами пользовательского интерфейса | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.uiobject.msgs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "типы сообщений и объекты пользовательского интерфейса"
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Типы сообщений, связанных с объектами пользовательского интерфейса
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В следующей таблице приведены типы объектов, которые могут использоваться в работе, и связанные с ними типы сообщений.  
  
### Объекты пользовательского интерфейса и связанные с ними сообщения  
  
|Идентификатор объекта|Сообщения|  
|---------------------------|---------------|  
|Имя класса, представляющее содержащее окно|Сообщения Windows, допустимые для класса, производного от [CWnd](../Topic/CWnd%20Class.md): диалоговое окно, окно, дочернее окно, дочернее окно MDI или рамочное окно, лежащее поверх других окон.|  
|Идентификатор сочетания клавиш или меню|-   Сообщение **COMMAND** \(выполнение функции программы\).<br />-   Сообщение **UPDATE\_COMMAND\_UI** \(динамическое обновление элемента меню\).|  
|Идентификатор элемента управления|Уведомляющие сообщения элементов управления для выбранного типа элементов управления.|  
  
## См. также  
 [Сопоставление сообщений с функциями](../Topic/Mapping%20Messages%20to%20Functions.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Добавление функции\-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной\-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)