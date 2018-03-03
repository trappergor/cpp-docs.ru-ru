---
title: "Обработка и сопоставление сообщений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6c13ed0bb19ef1ed2864378e151c6be8d98887
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="message-handling-and-mapping"></a>Обработка и сопоставление сообщений
Этого семейства статья описывает способ обработки сообщения и команды платформой MFC и способ их подключения к их функциями обработчиков.  
  
 В традиционных программ для Windows в больших switch в процедуру окна обрабатываются сообщения Windows. Вместо этого используется библиотекой MFC [схемы сообщений](../mfc/message-categories.md) соотнести прямой сообщения для различных классов функций-членов. Схемы сообщений, более эффективны, чем виртуальные функции для этой цели и разрешают сообщения должны обрабатываться самый подходящий объект C++ — приложения, документа, представления и т. д. Можно сопоставить одно сообщение или диапазон сообщений, идентификаторы команд или идентификаторы элемента управления.  
  
 **WM_COMMAND** сообщения — как правило, создаются с меню, кнопки панели инструментов и сочетания клавиш — использовать механизм сопоставления сообщений. MFC определяет стандарт [маршрутизации](../mfc/command-routing.md) команда сообщений между приложения, фрейма окна, представления и активные документы в программе. Можно переопределить для данного маршрута.  
  
 Схемы сообщений также указать способ обновления объектов пользовательского интерфейса (например, меню и кнопки панели инструментов), включая или отключая их в соответствии с текущем контексте.  
  
 Общие сведения о сообщения и очереди сообщений в Windows см. в разделе [сообщения и очереди сообщений](http://msdn.microsoft.com/library/windows/desktop/ms632590) в Windows SDK.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [Как платформа вызывает обработчик сообщений](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [Выполнение платформой поиска по схемам сообщений](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)  
  
-   [Сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)  
  
-   [Отображение сведений о команде в строке состояния](../mfc/how-to-display-command-information-in-the-status-bar.md)  
  
-   [Динамическое обновление объектов пользовательского интерфейса](../mfc/how-to-update-user-interface-objects.md)  
  
-   [Практическое руководство. Создание схемы сообщений для класса шаблона](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)   
 [CWnd-класс](../mfc/reference/cwnd-class.md)   
 [Класс CCmdTarget](../mfc/reference/ccmdtarget-class.md)
