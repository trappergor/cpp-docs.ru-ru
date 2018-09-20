---
title: Обработчиков сообщений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22dde243bb6d8e8a283e670804d4b8b6cad9082c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406754"
---
# <a name="message-handlers"></a>Обработчики сообщений

В MFC, выделенная *обработчик* функция обрабатывает каждого отдельного сообщения. Функции обработчика сообщений — функции-члены класса. В этой документации используются термины *функция-член обработчика сообщений*, *функция обработчика сообщений*, *обработчик сообщений*, и *обработчик*являются взаимозаменяемыми. Некоторые виды обработчиков сообщений, также называются «обработчики команд».

Запись учетных записей обработчики сообщений для большая часть работы в написании framework приложения. Семейство этой статье описывается, как работает механизм обработки сообщений.

Что делает обработчик для сообщения, сделать это все, что нужно сделать в ответ на это сообщение. Создания обработчиков с помощью окна свойств класса и внесите в код обработчика, с помощью редактора исходного кода.

Все средства Microsoft Visual C++ и MFC можно использовать для написания обработчиков. Список всех классов, см. в разделе [Обзор библиотеки классов](../mfc/class-library-overview.md) в *Справочник по библиотеке MFC*.

## <a name="see-also"></a>См. также

[Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

