---
title: Макрос ON_UPDATE_COMMAND_UI
ms.date: 11/04/2016
f1_keywords:
- ON_UPDATE_COMMAND_UI
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
ms.openlocfilehash: 986bc4f12223048a20f88da5d164b24dc1c08ace
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261184"
---
# <a name="onupdatecommandui-macro"></a>Макрос ON_UPDATE_COMMAND_UI

Используйте **свойства** окно для подключения объект пользовательского интерфейса с обработчиком команд обновления на целевой объект команды. Он автоматически подключиться к макрос ON_UPDATE_COMMAND_UI идентификатор объекта пользовательского интерфейса и создайте обработчик в объекте, который будет обрабатывать обновления. См. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md) Дополнительные сведения.

Например, чтобы обновить очистить все команды в меню "Правка" программы, используйте **свойства** окно, чтобы добавить запись схемы сообщений в выбранный класс, в объявлении функции обработчика команд обновления `OnUpdateEditClearAll` в классе объявление и шаблон пустой функции в файле реализации класса. Прототип функции выглядит следующим образом:

[!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]

Все обработчики, показано в функции, такие как **afx_msg** ключевое слово. Как и все обработчики обновлений, он принимает один аргумент указатель на `CCmdUI` объект.

## <a name="see-also"></a>См. также

[Практическое руководство. Обновление объектов пользовательского интерфейса](../mfc/how-to-update-user-interface-objects.md)
