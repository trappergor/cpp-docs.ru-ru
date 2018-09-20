---
title: Обработка и сопоставление сообщений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8c0fc3b9eec88fc9db9bb4eaff93381d1368368
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444324"
---
# <a name="message-handling-and-mapping"></a>Обработка и сопоставление сообщений

Этого семейства статье описывается, как сообщения и команды обрабатываются платформой MFC и способа их подключения к соответствующим функциям-обработчикам.

В традиционных программ для Windows в больших switch в процедуре окна обрабатываются сообщения Windows. Вместо этого использует MFC [сопоставлений сообщений](../mfc/message-categories.md) соотнести прямой сообщения для функций-членов различных классов. Схемы сообщений более эффективны, чем виртуальные функции для этой цели, и они дают сообщения будут обрабатываться наиболее соответствующий объект в C++ — приложения, документа, представления и т. д. Можно сопоставить одно сообщение или диапазон сообщений, идентификаторы команд или идентификаторов элементов управления.

WM_COMMAND-сообщения, как правило, создаются с меню, кнопки панели инструментов или ускорители — также использовать механизм схемы сообщений. MFC определяет стандарт [маршрутизации](../mfc/command-routing.md) команда сообщений между приложения, кадра окна, представления и активные документы в программе. Можно переопределить эту маршрутизацию, если вам нужно.

Схемы сообщений также указать способ обновления объектов пользовательского интерфейса (например, меню и кнопки панели инструментов), включая или отключая их в соответствии с текущем контексте.

Общие сведения о сообщения и очереди сообщений в Windows, см. в разделе [сообщения и очереди сообщений](https://msdn.microsoft.com/library/windows/desktop/ms632590) в пакете Windows SDK.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Сообщения и команды платформы](../mfc/messages-and-commands-in-the-framework.md)

- [Как платформа вызывает обработчик сообщений](../mfc/how-the-framework-calls-a-handler.md)

- [Выполнение платформой поиска по схемам сообщений](../mfc/how-the-framework-searches-message-maps.md)

- [Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)

- [Сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)

- [Отображение сведений о команде в строке состояния](../mfc/how-to-display-command-information-in-the-status-bar.md)

- [Динамическое обновление объектов пользовательского интерфейса](../mfc/how-to-update-user-interface-objects.md)

- [Практическое руководство. Создание схемы сообщений для класса шаблона](../mfc/how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)<br/>
[Общие разделы по MFC](../mfc/general-mfc-topics.md)<br/>
[Класс CWnd](../mfc/reference/cwnd-class.md)<br/>
[Класс CCmdTarget](../mfc/reference/ccmdtarget-class.md)
