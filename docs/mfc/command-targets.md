---
title: Целевые объекты команды | Документы Microsoft
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
ms.openlocfilehash: 1cbcfa1042a8430c704bad93e4bc0ce5655b5921
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341301"
---
# <a name="command-targets"></a>Цели команды
Рисунок [команды в Framework](../mfc/user-interface-objects-and-command-ids.md) показано соединение между объект пользовательского интерфейса, например меню и функции обработчика, который вызывается платформой для выполнения команды, полученный при щелчке объекта.  
  
 Windows отправляет сообщения, которые не являются сообщения команд непосредственно в окно, затем вызывается которого обработчик для сообщения. Тем не менее, платформа перенаправляет команды для нескольких объектов кандидата — называется «целевым объектам команды» — один из которых обычно вызывает обработчик для команды. Функции обработчика работают одинаково для команд и стандартные сообщения Windows, но механизмы, с помощью которых они вызываются отличаются, как описано в статье [как платформа вызывает обработчик](../mfc/how-the-framework-calls-a-handler.md).  
  
## <a name="see-also"></a>См. также  
 [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

