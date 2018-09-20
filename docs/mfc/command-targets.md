---
title: Команда целевых объектов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 408f63b80ff30a7ebdc51e5becb1dd97bb062852
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404232"
---
# <a name="command-targets"></a>Цели команды

Рис [команды платформы](../mfc/user-interface-objects-and-command-ids.md) представлена связь между объект пользовательского интерфейса, например пункта меню и функции обработчика, который вызывается платформой для выполнения команды, полученный при щелчке объекта.

Windows отправляет сообщения, которые не являются командных сообщений непосредственно на окно, затем вызывается обработчик которого для сообщения. Тем не менее, платформа перенаправляет команды, в число кандидатов объектов — называется «целевые объекты команд» — одна из которых обычно вызывает обработчик для команды. Функции обработчика работают одинаково для команд и стандартные сообщения Windows, но механизмы, по которым они вызываются отличаются, как описано в [как платформа вызывает обработчик](../mfc/how-the-framework-calls-a-handler.md).

## <a name="see-also"></a>См. также

[Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

