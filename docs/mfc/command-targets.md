---
title: Цели команды
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: ed3d6a68967dc7f4244f887ae34760fdb99fa7f5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274462"
---
# <a name="command-targets"></a>Цели команды

Рис [команды платформы](../mfc/user-interface-objects-and-command-ids.md) представлена связь между объект пользовательского интерфейса, например пункта меню и функции обработчика, который вызывается платформой для выполнения команды, полученный при щелчке объекта.

Windows отправляет сообщения, которые не являются командных сообщений непосредственно на окно, затем вызывается обработчик которого для сообщения. Тем не менее, платформа перенаправляет команды, в число кандидатов объектов — называется «целевые объекты команд» — одна из которых обычно вызывает обработчик для команды. Функции обработчика работают одинаково для команд и стандартные сообщения Windows, но механизмы, по которым они вызываются отличаются, как описано в [как платформа вызывает обработчик](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>См. также

[Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)
