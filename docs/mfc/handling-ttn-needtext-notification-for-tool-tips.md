---
title: Обработка уведомления TTN_NEEDTEXT для всплывающих подсказок | Документы Microsoft
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
ms.openlocfilehash: ce7a4d6dc6edf122b5d9b5301768dea8389e771e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345921"
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>Обработка уведомления TTN_NEEDTEXT для всплывающих подсказок
В рамках [Включение всплывающих подсказок](../mfc/enabling-tool-tips.md), обработки **TTN_NEEDTEXT** сообщений, добавив следующую запись в схеме сообщений для окна-владельца:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
 `memberFxn`  
 Функция-член вызывается, когда требуется текст для этой кнопки.  
  
 Обратите внимание, что всегда имеет идентификатор в подсказке 0.  
  
 Объявите функции обработчика в определении класса следующим образом:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 выделены курсивом используются следующие параметры:  
  
 `id`  
 Идентификатор элемента управления, которому было отправлено уведомление. Не используется. Идентификатор элемента управления берется из **NMHDR** структуры.  
  
 `pNMHDR`  
 Указатель на [NMTTDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760258) структуры. Эта структура также рассматривается далее в [структура TOOLTIPTEXT](../mfc/tooltiptext-structure.md).  
  
 `pResult`  
 Указатель на код результата можно установить до возврата. **TTN_NEEDTEXT** обработчики можно игнорировать `pResult` параметра.  
  
 В качестве примера обработчика уведомлений представление формы:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 Вызовите `EnableToolTips` (этот фрагмент, взяты из `OnInitDialog`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Подсказки в Windows, не являющиеся производными от CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

