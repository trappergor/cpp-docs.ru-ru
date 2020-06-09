---
title: создание объекта CToolBarCtrl
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
ms.openlocfilehash: 2627f9aaceeab7760e15b23435233e124c5ea6f0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619005"
---
# <a name="creating-a-ctoolbarctrl-object"></a>создание объекта CToolBarCtrl

Объекты [CToolBarCtrl](reference/ctoolbarctrl-class.md) содержат несколько внутренних структур данных — список растровых изображений для кнопок, список строк меток кнопок и список `TBBUTTON` структур, которые связывают изображение и (или) строку с положением, стилем, СОСТОЯНИЕм и идентификатором команды кнопки. На каждый элемент этих структур данных ссылается индекс, начинающийся с нуля. Прежде чем можно будет использовать `CToolBarCtrl` объект, необходимо настроить эти структуры данных. Список структур данных см. в разделе [элементы управления ToolBar](controls-mfc.md) в Windows SDK. Список строк можно использовать только для меток кнопок; нельзя получить строки с панели инструментов.

Для использования `CToolBarCtrl` объекта, как правило, выполняются следующие действия.

### <a name="to-use-a-ctoolbarctrl-object"></a>Использование объекта CToolBarCtrl

1. Создайте объект [CToolBarCtrl](reference/ctoolbarctrl-class.md) .

1. Вызовите [CREATE](reference/ctoolbarctrl-class.md#create) , чтобы создать общий элемент управления панели инструментов Windows и присоединить его к `CToolBarCtrl` объекту. Если необходимо, чтобы растровые изображения для кнопок, добавьте на панель инструментов точечные рисунки, вызвав [аддбитмап](reference/ctoolbarctrl-class.md#addbitmap). Если требуется использовать строковые метки для кнопок, добавьте строки на панель инструментов, вызвав [AddString](reference/ctoolbarctrl-class.md#addstring) и/или [аддстрингс](reference/ctoolbarctrl-class.md#addstrings). После вызова метода `AddString` и/или необходимо `AddStrings` вызвать функцию [AutoSize](reference/ctoolbarctrl-class.md#autosize) , чтобы получить строку или строки для отображения.

1. Добавьте структуры кнопок на панель инструментов, вызвав [аддбуттонс](reference/ctoolbarctrl-class.md#addbuttons).

1. Если вы хотите использовать подсказки, обработайте сообщения **TTN_NEEDTEXT** в окне владельца панели инструментов, как описано в разделе [Обработка всплывающих уведомлений](handling-tool-tip-notifications.md).

1. Если вы хотите, чтобы пользователь мог настраивать панель инструментов, обрабатывайте сообщения уведомления о настройке в окне "владелец", как описано в разделе [обработка уведомлений о настройке](handling-customization-notifications.md).

## <a name="see-also"></a>См. также раздел

[Использование CToolBarCtrl](using-ctoolbarctrl.md)<br/>
[Элементы управления](controls-mfc.md)
