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
ms.openlocfilehash: 5114fe53a5bac345eb6a55fb6c371f7bc1f698ef
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624031"
---
# <a name="oncmdmsg-handler"></a>Обработчик OnCmdMsg

Чтобы выполнить маршрутизацию команд, каждый целевой объект команды вызывает `OnCmdMsg` функцию члена следующей целевой цели команды в последовательности. Целевые объекты команды используют `OnCmdMsg` , чтобы определить, могут ли они выполнять команду и перенаправлять ее в другой целевой объект команды, если они не могут их обменяться.

Каждый целевой класс Command может переопределять `OnCmdMsg` функцию-член. Переопределения позволяют каждому классу маршрутизировать команды к конкретному следующему целевому объекту. Окно фрейма, например, всегда направляет команды в текущее дочернее окно или представление, как показано в таблице [стандартный маршрут команды](command-routing.md).

Реализация по умолчанию `CCmdTarget` `OnCmdMsg` использует схему сообщений класса Command-Target для поиска функции обработчика для каждого получаемого сообщения команды — так же, как и стандартные сообщения. При обнаружении совпадения вызывается обработчик. Поиск в схеме сообщений объясняется [тем, как платформа выполняет поиск в картах сообщений](how-the-framework-searches-message-maps.md).

## <a name="see-also"></a>См. также раздел

[Вызовы обработчика со стороны платформы](how-the-framework-calls-a-handler.md)
