---
title: Обработка уведомления TTN_NEEDTEXT для всплывающих подсказок | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TTN_NEEDTEXT
dev_langs:
- C++
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65278571fabf24011960ad577461347f1dfebf73
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200522"
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>Обработка уведомления TTN_NEEDTEXT для всплывающих подсказок
Как часть [Включение всплывающих подсказок](../mfc/enabling-tool-tips.md), вы обрабатываете **TTN_NEEDTEXT** сообщения, добавив следующую запись в схеме сообщений для окна-владельца:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
 `memberFxn`  
 Функция-член вызывается в том случае, когда требуется текст для данной кнопки.  
  
 Обратите внимание, что идентификатор подсказки всегда равно 0.  
  
 Объявите обработчик функции в определении класса следующим образом:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 выделенный курсивом используются следующие параметры:  
  
 `id`  
 Идентификатор элемента управления, которому было отправлено уведомление. Не используется. Идентификатор элемента управления берется из **NMHDR** структуры.  
  
 `pNMHDR`  
 Указатель на [NMTTDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagnmttdispinfoa) структуры. Эта структура также рассматривается далее в [структура TOOLTIPTEXT](../mfc/tooltiptext-structure.md).  
  
 `pResult`  
 Указатель на код результата можно задать перед возвратом. **TTN_NEEDTEXT** обработчики можно игнорировать *pResult* параметра.  
  
 Пример обработчика уведомлений представление формы:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 Вызовите `EnableToolTips` (этот фрагмент взят из `OnInitDialog`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Подсказки в Windows, не являющиеся производными от CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

