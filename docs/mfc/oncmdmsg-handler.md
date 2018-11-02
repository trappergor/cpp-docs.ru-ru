---
title: Обработчик OnCmdMsg
ms.date: 11/04/2016
f1_keywords:
- OnCmdMsg
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
ms.openlocfilehash: 37b3d5ffa3e6492c8c00b8b22eba58d09fad51f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643174"
---
# <a name="oncmdmsg-handler"></a>Обработчик OnCmdMsg

Чтобы выполнить маршрутизацию команд, вызывает каждый целевой объект команды `OnCmdMsg` функцию-член следующий целевой объект команды в последовательности. Команда предназначен для использования `OnCmdMsg` для определения ли они могут обрабатывать команды и направить ее в другой целевой объект команды, если они не может его обработать.

Каждый целевой объект команды класс может переопределить `OnCmdMsg` функция-член. Переопределения позвольте команд маршрута каждого класса Далее конкретной цели. Окно фрейма, к примеру, всегда направляет команды его текущее дочернее окно или представление, как показано в таблице [Стандартная Маршрутизация команды](../mfc/command-routing.md).

Значение по умолчанию `CCmdTarget` реализация `OnCmdMsg` использует схемы сообщений класса целевой объект команды для поиска функцию обработчика событий для каждого сообщения команды, он получает — так же, что стандартные сообщения производится поиск. Если совпадение найдено, он вызывает обработчик. Поиск схемы сообщений описан в [как Framework поиск схемы сообщений](../mfc/how-the-framework-searches-message-maps.md).

## <a name="see-also"></a>См. также

[Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

