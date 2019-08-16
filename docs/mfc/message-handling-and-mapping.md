---
title: Обработка и сопоставление сообщений
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
ms.openlocfilehash: 0321d98d8b92af0b80259bc49e84e69b987577a4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508246"
---
# <a name="message-handling-and-mapping"></a>Обработка и сопоставление сообщений

В этом семействе статей описывается обработка сообщений и команд платформой MFC и их подключение к функциям обработчика.

В традиционных программах для Windows сообщения Windows обрабатываются в виде большого оператора switch в оконной процедуре. Вместо этого MFC использует [схемы сообщений](../mfc/message-categories.md) для сопоставления прямых сообщений с разными функциями членов класса. Схемы сообщений более эффективны, чем виртуальные функции для этой цели, и позволяют обрабатывать сообщения наиболее подходящим C++ объектом — приложением, документом, представлением и т. д. Можно сопоставлять одно сообщение или диапазон сообщений, идентификаторы команд или идентификаторы элементов управления.

Сообщения WM_COMMAND, обычно создаваемые меню, кнопками панели инструментов или ускорителями, также используют механизм карт сообщений. MFC определяет стандартную [маршрутизацию](../mfc/command-routing.md) командных сообщений между приложением, окном фрейма, представлением и активными документами в программе. При необходимости эту маршрутизацию можно переопределить.

Схемы сообщений также предоставляют способ обновления объектов пользовательского интерфейса (например, меню и кнопок на панели инструментов), включая или отключая их в соответствии с текущим контекстом.

Общие сведения о сообщениях и очередях сообщений в Windows см. в разделе [сообщения и очереди сообщений](/windows/win32/winmsg/messages-and-message-queues) в Windows SDK.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

- [Вызов обработчика сообщений платформой](../mfc/how-the-framework-calls-a-handler.md)

- [Выполнение платформой поиска по схемам сообщений](../mfc/how-the-framework-searches-message-maps.md)

- [Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)

- [Сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)

- [Отображение сведений о командах в строке состояния](../mfc/how-to-display-command-information-in-the-status-bar.md)

- [Динамическое обновление объектов пользовательского интерфейса](../mfc/how-to-update-user-interface-objects.md)

- [Практическое руководство. Создание схемы сообщений для класса шаблона](../mfc/how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие разделы по MFC](../mfc/general-mfc-topics.md)<br/>
[Класс CWnd](../mfc/reference/cwnd-class.md)<br/>
[Класс CCmdTarget](../mfc/reference/ccmdtarget-class.md)
