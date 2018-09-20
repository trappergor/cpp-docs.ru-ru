---
title: Обработка уведомлений элемента управления заголовка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd7c6fa8a85aee06aca3b1bf804a06df428e82cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387761"
---
# <a name="processing-header-control-notifications"></a>Обработка уведомлений элемента управления "Заголовок"

В классе представления или диалогового окна, используйте окно свойств для создания [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) функцию обработчика с оператором switch для любого заголовка элемента управления ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) для уведомляющих сообщений обрабатывать (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)). Уведомления отправляются в родительское окно, когда пользователь нажимает кнопку или дважды щелкает элемент заголовка, перетаскивания a разделитель между элементами и т. д.

Сообщения уведомлений, связанных с элементом управления заголовка перечислены в [ссылки на элемент управления заголовка](https://msdn.microsoft.com/library/windows/desktop/bb775239) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

