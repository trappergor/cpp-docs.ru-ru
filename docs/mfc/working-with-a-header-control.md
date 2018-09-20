---
title: Работа с элементом управления заголовка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], working with
- header controls
ms.assetid: af3afb5c-bf97-451b-8fee-3adcb8257210
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6da3ffd669ebd3d9cc02fc56a13acfa1fe804e7b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381742"
---
# <a name="working-with-a-header-control"></a>Работа с элементом управления "Заголовок"

Простой способ использования элемента управления заголовка ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) работает в сочетании с элементом управления списка; см. в разделе [использование CListCtrl](../mfc/using-clistctrl.md) далее в этой статье семейство. Также можно использовать элемент управления заголовка сама по себе. MFC вызывает `InitCommonControls` для вас. Ниже приведены основные задачи.

- [Создание элемента управления заголовка](../mfc/creating-the-header-control.md)

- [Добавление элементов управления заголовка](../mfc/adding-items-to-the-header-control.md)

- [Сортировка элементов в элементе управления заголовка](../mfc/ordering-items-in-the-header-control.md)

- [Обработка уведомлений элемента управления заголовка](../mfc/processing-header-control-notifications.md)

Если объект элемента управления заголовка внедрен в родительском классе представления или диалогового окна, элемент управления уничтожается при уничтожении родительского.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

