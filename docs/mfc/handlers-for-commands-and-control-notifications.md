---
title: Обработчики для команд и уведомлений элементов управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bda42393cd55b60ab787665b51957bb2f94c5df3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430087"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Обработчики для команд и уведомлений элементов управления

Существуют обработчики не по умолчанию для команды или сообщения уведомление элемента управления. Таким образом вам доступен только по соглашению именования обработчики для этих двух категорий сообщений. При сопоставлении обработчика уведомление команды или элемента управления, свойства windows предлагает имя на основе кода команда идентификатор или уведомление элемента управления. Можно принять предложенное имя, изменить его или заменить его.

Соглашение о предлагает имени обработчики из обеих категорий для объекта пользовательского интерфейса, которые они представляют. Таким образом можно назвать обработчик для команды вырезания в меню "Правка"

[!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Так как команды вырезания так часто реализуется в приложениях, платформа предопределяет идентификатор команды для команды вырезания в виде **ID_EDIT_CUT**. Список всех предварительно определенная команда идентификаторы см. в файле AFXRES. З. Дополнительные сведения см. в разделе [стандартные команды](../mfc/standard-commands.md).

Кроме того, соглашение о предлагает обработчик для **BN_CLICKED** сообщение уведомления кнопкой с надписью «Кнопка» может называться

[!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

Эта команда может назначить Идентификатором **IDC_MY_BUTTON** так, как она эквивалентна объект пользовательского интерфейса приложения.

Обе категории сообщения не принимают аргументы и не возвращают значений.

## <a name="see-also"></a>См. также

[Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)
