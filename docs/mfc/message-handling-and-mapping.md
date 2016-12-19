---
title: "Обработка и сопоставление сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "обработка сообщений"
  - "схемы сообщений"
  - "MFC - библиотека, сообщения"
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработка и сопоставление сообщений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Это семейство статьи описание сообщения и команды отображаются платформой MFC и компьютеру в их в их функциями обработчика.  
  
 В традиционных программах для Windows, сообщения Windows, обрабатываются в общем оператор switch в процедуре окна.  Вместо этого MFC использует [схемы сообщений](../mfc/message-categories.md) для сопоставления сообщения непосредственно к определенным функциям членов класса.  Схемы сообщений является более эффективным, чем виртуальные функции для этой цели, и они позволяют сообщения, которое будет обрабатываться наиболее подходящий объект C\+\+, приложение, документ, представления и т д  Сопоставлением одно сообщение или набор сообщений, идентификаторы команд, или идентификатор элемента управления.  
  
 Сообщения **WM\_COMMAND** — как правило, создают меню, кнопки панели инструментов или сочетаниями клавиш — также используют механизм сопоставления сообщений.  MFC определяет стандартное [маршрутизация](../mfc/command-routing.md) сообщений команды для приложения, фреймового окна, представления и активных документов в программе.  Можно переопределить это маршрутизация при необходимости.  
  
 Схемы сообщений также предоставляют способ обновления объектов пользовательского интерфейса \(например, меню и кнопок панели инструментов\), включение или отключение их соответствии текущего контекста.  
  
 Общие сведения о сообщениях и очередях сообщений в Windows см. в разделе [Сообщения и очереди сообщений](http://msdn.microsoft.com/library/windows/desktop/ms632590) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Дополнительные сведения  
  
-   [Сообщения и команды в платформе .NET Framework](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [Как платформа вызывает обработчик сообщений](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [Как платформы .NET Framework найти сопоставления сообщений](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [Объявление функции обработчика сообщений](../mfc/declaring-message-handler-functions.md)  
  
-   [Сообщения сопоставления в функции](../Topic/Mapping%20Messages%20to%20Functions.md)  
  
-   [Отображает сведения о команде в строке состояния](../Topic/How%20to:%20Display%20Command%20Information%20in%20the%20Status%20Bar.md)  
  
-   [Динамическое обновление объектов пользовательского интерфейса](../mfc/how-to-update-user-interface-objects.md)  
  
-   [Практическое руководство. Создание виртуальной схемы сообщений для класса шаблона](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)