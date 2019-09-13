---
title: Создание элемента управления "Заголовок"
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
ms.openlocfilehash: 22739e5671fb0300011de84d976eff0ce26eaedb
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907587"
---
# <a name="creating-the-header-control"></a>Создание элемента управления "Заголовок"

Элемент управления "заголовок" не доступен непосредственно в редакторе диалоговых окон (хотя можно добавить элемент управления "список", включающий элемент управления "заголовок").

### <a name="to-put-a-header-control-in-a-dialog-box"></a>Размещение элемента управления "заголовок" в диалоговом окне

1. Вручную внедрите переменную-член типа [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) в класс диалогового окна.

1. В [онинитдиалог](../mfc/reference/cdialog-class.md#oninitdialog)создайте и задайте стили для `CHeaderCtrl`, разместите его и отобразите.

1. Добавление элементов в элемент управления "заголовок".

1. Используйте [мастер классов](reference/mfc-class-wizard.md) для сопоставления функций обработчика в классе диалогового окна с любыми сообщениями уведомления элемента управления заголовками, которые необходимо обменять (см. раздел [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>Размещение элемента управления "заголовок" в представлении (не в CListView)

1. Внедрите объект [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) в класс представления.

1. Стиль, расположение и отображение окна элемента управления "заголовок" в функции элемента [онинитиалупдате](../mfc/reference/cview-class.md#oninitialupdate) представления.

1. Добавление элементов в элемент управления "заголовок".

1. Используйте [мастер классов](reference/mfc-class-wizard.md) для сопоставления функций обработчика в классе представления с любыми сообщениями уведомления элемента управления заголовками, которые необходимо обменять (см. раздел [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).

В любом случае внедренный объект элемента управления создается при создании объекта представления или диалогового окна. Затем необходимо вызвать метод [CHeaderCtrl:: Create](../mfc/reference/cheaderctrl-class.md#create) , чтобы создать окно управления. Чтобы разместить элемент управления, вызовите [CHeaderCtrl:: Layout](../mfc/reference/cheaderctrl-class.md#layout) , чтобы определить начальный размер и положение элемента управления и [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) , чтобы задать нужное положение. Затем добавьте элементы, как описано в разделе [Добавление элементов в элемент управления "заголовок"](../mfc/adding-items-to-the-header-control.md).

Дополнительные сведения см. в разделе [Создание элемента управления "заголовок](/windows/win32/Controls/header-controls) " в Windows SDK.

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
