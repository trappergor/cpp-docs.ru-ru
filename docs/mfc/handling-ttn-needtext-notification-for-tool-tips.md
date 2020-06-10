---
title: Обработка уведомления TTN_NEEDTEXT для всплывающих подсказок
ms.date: 11/04/2016
f1_keywords:
- TTN_NEEDTEXT
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
ms.openlocfilehash: 75850dbf92587cf654d4f7a39ea54af1fd9dd5bd
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620085"
---
# <a name="handling-ttn_needtext-notification-for-tool-tips"></a>Обработка уведомления TTN_NEEDTEXT для всплывающих подсказок

В рамках [включения советов](enabling-tool-tips.md)вы обрабатываете **TTN_NEEDTEXT** сообщение, добавив следующую запись в схему сообщений окна владельца:

[!code-cpp[NVC_MFCControlLadenDialog#40](codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]

*мемберфксн*<br/>
Функция-член, вызываемая, когда для этой кнопки требуется текст.

Обратите внимание, что идентификатор подсказки всегда равен 0.

Объявите функцию обработчика в определении класса следующим образом:

[!code-cpp[NVC_MFCControlLadenDialog#53](codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]

Ниже перечислены параметры с курсивом.

*идентификатор*<br/>
Идентификатор элемента управления, отправившего уведомление. Не используется. Идентификатор элемента управления берется из структуры **NMHDR** .

*пнмхдр*<br/>
Указатель на структуру [нмттдиспинфо](/windows/win32/api/commctrl/ns-commctrl-nmttdispinfow) . Эта структура также обсуждается далее в [структуре ToolTipText](tooltiptext-structure.md).

*пресулт*<br/>
Указатель на код результата, который можно задать перед возвратом. Обработчики **TTN_NEEDTEXT** могут игнорировать параметр *пресулт* .

В качестве примера обработчика уведомлений представления формы:

[!code-cpp[NVC_MFCControlLadenDialog#54](codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]

Вызов `EnableToolTips` (этот фрагмент взят из `OnInitDialog` ):

[!code-cpp[NVC_MFCControlLadenDialog#55](codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]

## <a name="see-also"></a>См. также раздел

[Всплывающие подсказки в Windows, не являющиеся производными CFrameWnd](tool-tips-in-windows-not-derived-from-cframewnd.md)
