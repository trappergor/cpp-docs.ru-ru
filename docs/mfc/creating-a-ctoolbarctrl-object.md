---
title: создание объекта CToolBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
ms.openlocfilehash: cf1d2eeb9efd2f8a1e7b433c0e18dd868a8b9aca
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445892"
---
# <a name="creating-a-ctoolbarctrl-object"></a>создание объекта CToolBarCtrl

Объекты [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) содержат несколько внутренних структур данных — список растровых изображений для кнопок, список строк меток для кнопок и список структур `TBBUTTON`, которые связывают изображение и (или) строку с положением, стилем, состоянием и идентификатором команды кнопки. На каждый элемент этих структур данных ссылается индекс, начинающийся с нуля. Прежде чем можно будет использовать объект `CToolBarCtrl`, необходимо настроить эти структуры данных. Список структур данных см. в разделе [элементы управления ToolBar](controls-mfc.md) в Windows SDK. Список строк можно использовать только для меток кнопок; нельзя получить строки с панели инструментов.

Чтобы использовать объект `CToolBarCtrl`, обычно выполняются следующие действия.

### <a name="to-use-a-ctoolbarctrl-object"></a>Использование объекта CToolBarCtrl

1. Создайте объект [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) .

1. Вызовите [CREATE](../mfc/reference/ctoolbarctrl-class.md#create) , чтобы создать общий элемент управления панели инструментов Windows и присоединить его к объекту `CToolBarCtrl`. Если необходимо, чтобы растровые изображения для кнопок, добавьте на панель инструментов точечные рисунки, вызвав [аддбитмап](../mfc/reference/ctoolbarctrl-class.md#addbitmap). Если требуется использовать строковые метки для кнопок, добавьте строки на панель инструментов, вызвав [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) и/или [аддстрингс](../mfc/reference/ctoolbarctrl-class.md#addstrings). После вызова `AddString` и (или) `AddStrings`следует вызвать функцию [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) , чтобы получить строку или строки для отображения.

1. Добавьте структуры кнопок на панель инструментов, вызвав [аддбуттонс](../mfc/reference/ctoolbarctrl-class.md#addbuttons).

1. Если вы хотите использовать подсказки, обработайте сообщения **TTN_NEEDTEXT** в окне владельца панели инструментов, как описано в разделе [Обработка всплывающих уведомлений](../mfc/handling-tool-tip-notifications.md).

1. Если вы хотите, чтобы пользователь мог настраивать панель инструментов, обрабатывайте сообщения уведомления о настройке в окне "владелец", как описано в разделе [обработка уведомлений о настройке](../mfc/handling-customization-notifications.md).

## <a name="see-also"></a>См. также раздел

[Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
