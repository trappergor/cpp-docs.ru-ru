---
title: Обработчики для команд и уведомлений элементов управления
ms.date: 11/04/2016
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
ms.openlocfilehash: 43b6a517b680a5f6ff092337fbf3d90dd0115dd7
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907974"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Обработчики для команд и уведомлений элементов управления

Нет обработчиков по умолчанию для команд или сообщений уведомления об управлении. Поэтому вы привязаны только по соглашению в именовании обработчиков для этих категорий сообщений. При сопоставлении команды или уведомления элемента управления с обработчиком, [мастер классов](reference/mfc-class-wizard.md) предлагает имя на основе идентификатора команды или кода уведомления элемента управления. Вы можете принять предложенное имя, изменить его или заменить.

Соглашение предполагает, что вы наименают обработчики в обеих категориях для объекта пользовательского интерфейса, который они представляют. Таким же обработчиком команды Cut в меню Правка может быть присвоено имя

[!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

Поскольку команда «вырезать» настолько часто реализуется в приложениях, платформа определяет идентификатор команды для команды Cut как **ID_EDIT_CUT**. Список всех предопределенных идентификаторов команд см. в файле AFXRES. Высоты. Дополнительные сведения см. в разделе [стандартные команды](../mfc/standard-commands.md).

Кроме того, соглашение предлагает обработчик для сообщения уведомления **BN_CLICKED** на кнопке, обозначенной как "Моя кнопка", может называться

[!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

Этой команде можно назначить идентификатор **IDC_MY_BUTTON** , так как она эквивалентна объекту пользовательского интерфейса, относящегося к приложению.

Обе категории сообщений не имеют аргументов и не возвращают значения.

## <a name="see-also"></a>См. также

[Объявление функций обработчиков сообщений](../mfc/declaring-message-handler-functions.md)
