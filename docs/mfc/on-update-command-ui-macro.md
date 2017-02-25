---
title: "Макрос ON_UPDATE_COMMAND_UI | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ON_UPDATE_COMMAND_UI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "макросы обработчика команд"
  - "ON_UPDATE_COMMAND_UI - макрос"
  - "обработчики обновлений"
  - "обновление объектов пользовательского интерфейса"
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Макрос ON_UPDATE_COMMAND_UI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используйте окно **Свойства** для подключения объекта пользовательского интерфейса в обработчик команда\- обновления в объекте команда\- целевого объекта.  Автоматически подключится идентификатор объекта пользовательского интерфейса макросу `ON_UPDATE_COMMAND_UI` и создает обработчик в объекте, который выполняет обновление.  Дополнительные сведения см. в разделе [Сообщения сопоставления в функции](../Topic/Mapping%20Messages%20to%20Functions.md).  
  
 Например, чтобы обновить очистить все команды в меню " Правка " программы, используется окно **Свойства** для добавления записи сопоставления сообщений в выбранном классе, объявление функции для него обработчика команда\- обновления `OnUpdateEditClearAll` в объявлении класса и пустой шаблон функции в файле реализации класса.  Прототип функции выглядит следующим образом:  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/CPP/on-update-command-ui-macro_1.h)]  
  
 Как и все обработчики, функция указывает ключевое слово **afx\_msg**.  Как и все обработчики обновления, и принимает один аргумент, указатель на объект `CCmdUI`.  
  
## См. также  
 [Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)