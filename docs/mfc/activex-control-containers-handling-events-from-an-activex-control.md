---
title: Контейнеры элементов управления ActiveX. Обработка событий из элемента управления ActiveX
ms.date: 09/12/2018
helpviewer_keywords:
- event handlers [MFC], ActiveX controls
- ActiveX control containers [MFC], event sinks
- event handling [MFC], ActiveX controls
- ON_EVENT macro [MFC]
- ActiveX controls [MFC], events [MFC]
- END_EVENTSINK_MAP macro, using
- events [MFC], ActiveX controls
- BEGIN_EVENTSINK_MAP macro
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
ms.openlocfilehash: ae623ee0973e78db3b542646dd6bdec58cc2dfc8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367955"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>Контейнеры элементов управления ActiveX. Обработка событий из элемента управления ActiveX

В этой статье обсуждается использование окна **Свойств** (в **классе View)** для установки обработчиков событий для элементов управления ActiveX в контейнере управления ActiveX. Обработчики событий используются для получения уведомлений (из-под контроля) определенных событий и выполнения некоторых действий в ответ. Это уведомление называется "запуск" события.

>[!IMPORTANT]
> ActiveX является устаревшей технологией, которая не должна использоваться для новых разработок. Для получения дополнительной информации о современных технологиях, которые заменяли ActiveX, [см.](activex-controls.md)

> [!NOTE]
> В этой статье в качестве примеров в процедурах и коде используется проект контейнера для управления ActiveX на основе диалога ActiveX под названием Container и встроенный элемент управления с именем Circ.

Using the Events button in the **Properties** window (in **Class View**), you can create a map of events that can occur in your ActiveX control container application. Эта карта, называемая «картой раковины событий», создается и поддерживается Visual C, когда вы добавляете обработчики событий в класс контейнеров управления. Каждый обработчик событий, реализованный с входом на карту событий, отображает определенное событие с функцией обработчика событий контейнера. Функция обработчика событий вызывается при увольнении указанного события объектом управления ActiveX.

Для получения дополнительной информации о картах *Class Library Reference*раковины событий, [см.](../mfc/reference/event-sink-maps.md)

## <a name="event-handler-modifications-to-the-project"></a><a name="_core_event_handler_modifications_to_the_project"></a>Модификации обработчика событий в проекте

При использовании окна **Свойств** для добавления обработчиков событий в проекте объявляется и определяется карта погружения событий. Следующие операторы добавляются в элемент управления. Файл CPP при первом добавлении обработчика событий. Этот код объявляет карту раковины события для класса диалогового окна (в данном случае, `CContainerDlg`):

[!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

При использовании окна **Свойств** для добавления`ON_EVENT`событий в карту событий () добавляется в карту раковины событий и добавляется функция обработчика событий в реализацию контейнера (. CPP) файл.

Следующий пример объявляет обработчик `OnClickInCircCtrl`события, называемый для `ClickIn` события управления Circ:

[!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

Кроме того, в реализацию класса `CContainerDlg` добавляется следующий шаблон (. CPP) файл для функции обработчика событий:

[!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

Для получения дополнительной информации о макросах *Class Library Reference*раковины событий [см.](../mfc/reference/event-sink-maps.md)

#### <a name="to-create-an-event-handler-function"></a>Создание функции обработчика событий

1. Из класса View выберите класс диалогов, содержащий элемент управления ActiveX. Для этого примера используйте `CContainerDlg`.

1. В окне **Свойства** нажмите кнопку **События** .

1. В окне **Свойств** выберите идентификатор управления встроенным элементом управления ActiveX. Для этого примера используйте `IDC_CIRCCTRL1`.

   Окно **Свойства** отображает список событий, которые могут быть уволены встроенным управлением ActiveX. Любая функция члена, показанная жирным шрифтом, уже имеет функции обработчика, назначенные ей.

1. Выберите событие, которое требуется для диалога. Для этого примера выберите **Нажмите кнопку**.

1. Из выпадающих вниз поле списка справа, ** \<выберите Добавить> ClickCircctrl1**.

1. Дважды щелкните новую функцию обработчика из класса View, чтобы перейти к коду обработчика событий в реализации (. CPP) файл `CContainerDlg`.

## <a name="see-also"></a>См. также раздел

[Контейнеры управления ActiveX](../mfc/activex-control-containers.md)
