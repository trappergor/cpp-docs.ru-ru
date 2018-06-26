---
title: Макрос ON_UPDATE_COMMAND_UI | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_UPDATE_COMMAND_UI
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43caffe53be180221b4145a03df7cfc41c31828e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928642"
---
# <a name="onupdatecommandui-macro"></a>Макрос ON_UPDATE_COMMAND_UI
Используйте **свойства** окно для подключения объект пользовательского интерфейса с обработчиком команды update в целевой объект команды. Он автоматически соединиться макрос ON_UPDATE_COMMAND_UI идентификатор объекта пользовательского интерфейса и создайте обработчик в объект, который будет обрабатывать обновления. В разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md) для получения дополнительной информации.  
  
 Например, чтобы обновить очистить все команды в меню "Правка" программы, используйте **свойства** окно для добавления записи в схеме сообщений в выбранный класс, в объявлении функции обработчика команд обновления `OnUpdateEditClearAll` в классе объявление и пустой функции шаблона в файле реализации класса. Прототип функции выглядит следующим образом:  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]  
  
 Как и все обработчики, показано в функции **afx_msg** ключевое слово. Как и все обработчики обновлений, принимает один аргумент, указатель на `CCmdUI` объект.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)

