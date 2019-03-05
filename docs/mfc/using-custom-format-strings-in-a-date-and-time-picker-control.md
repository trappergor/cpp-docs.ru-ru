---
title: Использование строк пользовательского формата в элементе выбора даты и времени
ms.date: 11/04/2016
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
ms.openlocfilehash: 8da5ecaf473d6d3c35ddc1b95ac856ce8c12f163
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57286890"
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>Использование строк пользовательского формата в элементе выбора даты и времени

По умолчанию элементов выбора даты и времени предоставляют три формате типов (каждый формат, соответствующий уникальный стиль) для отображения текущей даты или времени.

- **DTS_LONGDATEFORMAT** отображает дату в длинном формате, выдавать выходные данные, такие как «Среда, 2 января 2000».

- **DTS_SHORTDATEFORMAT** отображает дату в кратком формате, выдавать выходные данные, такие как «1/3/00».

- **DTS_TIMEFORMAT** отображает время в длинном формате, выдавать выходные данные, такие как «17:31:42: 00».

Тем не менее используя строку пользовательского формата можно настроить внешний вид даты или времени. Это Настраиваемая строка состоит из существующего формата символов, nonformat символов или их сочетание. После создания пользовательской строки сделать вызов к [CDateTimeCtrl::SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) передавая пользовательской строки. Элемент управления выбора даты и времени будут отображаться текущее значение с помощью строки настраиваемого формата.

В следующем примере кода (где *m_dtPicker* является `CDateTimeCtrl` объекта) показано одно из возможных решений:

[!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]

Помимо строк настраиваемого формата, элемент выбора даты и времени также управляет поддержкой [полей обратного вызова](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).

## <a name="see-also"></a>См. также

[Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
