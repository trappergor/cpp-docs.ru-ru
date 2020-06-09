---
title: Цели команды
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: 59ba197174e95e42cd237c875f39f07801cb3dbe
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619312"
---
# <a name="command-targets"></a>Цели команды

Команды на рисунке [в платформе](user-interface-objects-and-command-ids.md) показывают соединение между объектом пользовательского интерфейса, например пунктом меню, и функцией обработчика, которая вызывается платформой для выполнения результирующей команды при щелчке объекта.

Windows отправляет сообщения, которые не являются командными сообщениями непосредственно в окно, обработчик которого для сообщения вызывается. Однако платформа направляет команды на ряд объектов-кандидатов, именуемых "целевыми объектами команды", одна из которых обычно вызывает обработчик для команды. Функции обработчика работают одинаково для обеих команд и стандартных сообщений Windows, но механизмы, с помощью которых они вызываются, отличаются, как описано в [описании того, как платформа вызывает обработчик](how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>См. также раздел

[Сообщения и команды в платформе](messages-and-commands-in-the-framework.md)
