---
title: "Макрос ON_UPDATE_COMMAND_UI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ON_UPDATE_COMMAND_UI
dev_langs: C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3de873cf70bafa77d7c8f4b05c70ce211b2c2258
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="onupdatecommandui-macro"></a>Макрос ON_UPDATE_COMMAND_UI
Используйте **свойства** окно для подключения объект пользовательского интерфейса с обработчиком команды update в целевой объект команды. Идентификатор объекта пользовательского интерфейса автоматически подключится `ON_UPDATE_COMMAND_UI` макрос и создайте обработчик в объект, который будет обрабатывать обновления. В разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md) для получения дополнительной информации.  
  
 Например, чтобы обновить очистить все команды в меню "Правка" программы, используйте **свойства** окно для добавления записи в схеме сообщений в выбранный класс, в объявлении функции обработчика команд обновления `OnUpdateEditClearAll` в классе объявление и пустой функции шаблона в файле реализации класса. Прототип функции выглядит следующим образом:  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]  
  
 Как и все обработчики, показано в функции **afx_msg** ключевое слово. Как и все обработчики обновлений, принимает один аргумент, указатель на `CCmdUI` объект.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)

