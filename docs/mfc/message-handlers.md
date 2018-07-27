---
title: Обработчики сообщений | Документы Microsoft
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
ms.openlocfilehash: be4ccf9ec33e5ddf497193c1942e9f300f8cae57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347634"
---
# <a name="message-handlers"></a>Обработчики сообщений
В MFC, выделенную *обработчик* функция обрабатывает каждого отдельного сообщения. Функции обработчика сообщений — функции-члены класса. В этой документации используются термины *обработчик сообщений функции-члена*, *функцию обработки сообщений*, *обработчик сообщений*, и *обработчик*попеременно. Некоторые виды обработчиков сообщений, также называются «обработчики команд».  
  
 Запись сообщения счета обработчики для большую часть работы в написании платформы приложения. Семейство этой статье описано, как работает механизм обработки сообщений.  
  
 Что делает обработчик для сообщения, делать это любые необходимые выполняются в ответ на это сообщение. Можно создавать обработчики событий можно с помощью окна свойств класса и затем добавьте код обработчика, с помощью редактора исходного кода.  
  
 Все средства Microsoft Visual C++ и MFC можно использовать для написания обработчиков. Список всех классов см. в разделе [Общие сведения о библиотеке классов](../mfc/class-library-overview.md) в *Справочник по библиотеке MFC*.  
  
## <a name="see-also"></a>См. также  
 [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

