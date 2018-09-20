---
title: Обработчик OnCmdMsg | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnCmdMsg
dev_langs:
- C++
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6691e4935d46b32bc8f433823888bb7f53a36890
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398837"
---
# <a name="oncmdmsg-handler"></a>Обработчик OnCmdMsg

Чтобы выполнить маршрутизацию команд, вызывает каждый целевой объект команды `OnCmdMsg` функцию-член следующий целевой объект команды в последовательности. Команда предназначен для использования `OnCmdMsg` для определения ли они могут обрабатывать команды и направить ее в другой целевой объект команды, если они не может его обработать.

Каждый целевой объект команды класс может переопределить `OnCmdMsg` функция-член. Переопределения позвольте команд маршрута каждого класса Далее конкретной цели. Окно фрейма, к примеру, всегда направляет команды его текущее дочернее окно или представление, как показано в таблице [Стандартная Маршрутизация команды](../mfc/command-routing.md).

Значение по умолчанию `CCmdTarget` реализация `OnCmdMsg` использует схемы сообщений класса целевой объект команды для поиска функцию обработчика событий для каждого сообщения команды, он получает — так же, что стандартные сообщения производится поиск. Если совпадение найдено, он вызывает обработчик. Поиск схемы сообщений описан в [как Framework поиск схемы сообщений](../mfc/how-the-framework-searches-message-maps.md).

## <a name="see-also"></a>См. также

[Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

