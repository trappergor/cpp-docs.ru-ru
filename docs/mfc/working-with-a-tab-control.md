---
title: Работа с элементом управления Tab | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl class [MFC], using
- tab controls [MFC], working with
- tab controls [MFC], using
ms.assetid: 819488e3-4944-44b7-9483-195edb8e0aed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12de4065774c4813eeb10fab902551db14d10d3a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420846"
---
# <a name="working-with-a-tab-control"></a>Работа с элементом управления "Вкладка"

Самый простой способ использования вкладок ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) является, добавьте его в ресурс шаблона диалоговых окон с помощью редактора диалоговых окон. Также можно использовать набор вкладок в сам по себе. MFC вызывает `InitCommonControls` для вас. Ниже приведены основные задачи.

- [Создание элемента управления tab](../mfc/creating-the-tab-control.md)

- [Добавление вкладок в элемент управления вкладками](../mfc/adding-tabs-to-a-tab-control.md)

- [Обработка уведомляющих сообщений элемента управления tab](../mfc/processing-tab-control-notification-messages.md)

Если объект элемента управления tab внедрен в родительском классе представления или диалогового окна, элемент управления уничтожается при уничтожении родительского.

## <a name="see-also"></a>См. также

[Использование CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

