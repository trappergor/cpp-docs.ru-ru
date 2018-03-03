---
title: "Обработчик OnCmdMsg | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 173741ef73cd4bf6426787ef56e8334f504d7c0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="oncmdmsg-handler"></a>Обработчик OnCmdMsg
Для выполнения маршрутизации команд, вызывает каждый целевой объект команды `OnCmdMsg` функцию-член следующий целевой объект команды в последовательности. Команда предназначен для использования `OnCmdMsg` для определения, является ли они могут обрабатывать команды и направить ее другой целевой объект команды, если они не может обрабатывать.  
  
 Каждый целевой объект команды класс может переопределить `OnCmdMsg` функции-члена. Переопределения позволяют каждый класс маршрутизации команд для определенного целевого Далее. Окно фрейма, например, всегда направляет команды его текущее дочернее окно или представления, как показано в таблице [Стандартная Маршрутизация команды](../mfc/command-routing.md).  
  
 Значение по умолчанию `CCmdTarget` реализация `OnCmdMsg` использует для поиска функцию обработчика событий для каждого сообщения команды, он получает схему сообщений класса цель команды — таким же образом, поиск будет производиться стандартные сообщения. Если совпадение найдено, он вызывает обработчик. Поиск в схеме сообщений описан в [как Framework поиск схемы сообщений](../mfc/how-the-framework-searches-message-maps.md).  
  
## <a name="see-also"></a>См. также  
 [Вызовы обработчика со стороны платформы](../mfc/how-the-framework-calls-a-handler.md)

