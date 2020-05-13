---
title: Обработчики для диапазонов схем сообщений
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- handlers [MFC], message-map ranges
- message maps [MFC], message handler functions
- message maps [MFC], ranges
- control-notification messages [MFC]
- command IDs [MFC], message mapping
- message-map ranges [MFC]
- handlers [MFC]
- message handling [MFC], message handler functions
- mappings [MFC], message ranges
- command handling [MFC], command update handlers
- controls [MFC], notifications
- handler functions [MFC], message-map ranges
- handler functions [MFC]
- command update handlers [MFC]
- command routing [MFC], command update handlers
- message ranges [MFC]
- handler functions [MFC], declaring
- message ranges [MFC], mapping
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
ms.openlocfilehash: fc33df6957beab6e4e8de3093dfc00cf2651780e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370511"
---
# <a name="handlers-for-message-map-ranges"></a>Обработчики для диапазонов схем сообщений

В этой статье объясняется, как сопоставить диапазон сообщений с одной функцией обработчика сообщений (вместо отображения одного сообщения только для одной функции).

Есть моменты, когда вам нужно обработать более одного сообщения или управления уведомления точно таким же образом. В такие моменты может потребоваться сопоставить все сообщения с одной функцией обработчика. Диапазоны сообщений-карты позволяют делать это для смежного диапазона сообщений:

- Вы можете сопоставить диапазоны идонов команд:

  - Функция обработчика команд.

  - Функция обработчика обработчика команд.

- Можно сопоставить сообщения диспетчерских уведомлений для различных иик-идомимов управления с функцией обработчика сообщений.

Темы, затронутые в этой статье, включают:

- [Запись на карту сообщений](#_core_writing_the_message.2d.map_entry)

- [Объявление функции обработчика](#_core_declaring_the_handler_function)

- [Пример для ряда командных идонов](#_core_example_for_a_range_of_command_ids)

- [Пример для ряда идотов управления](#_core_example_for_a_range_of_control_ids)

## <a name="writing-the-message-map-entry"></a><a name="_core_writing_the_message.2d.map_entry"></a>Написание ввода сообщения-Карты

В. Файл CPP, добавьте запись на карту сообщений, как показано в следующем примере:

[!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]

Запись на карту сообщений состоит из следующих элементов:

- Макрос диапазона «сообщение-карта»:

  - [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)

  - [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)

  - [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)

- Параметры макроса:

  Первые два макроса принимают три параметра:

  - Идентификатор команды, запускающий диапазон

  - Идентификатор команды, который завершает диапазон

  - Имя функции обработчика сообщений

  Диапазон идотов командования должен быть смежным.

  Третий макрос, `ON_CONTROL_RANGE`, принимает дополнительный первый параметр: сообщение о контроле-уведомлении, например, **EN_CHANGE.**

## <a name="declaring-the-handler-function"></a><a name="_core_declaring_the_handler_function"></a>Объявление функции обработчика

Добавьте декларацию функции обработчика в . H файл. Следующий код показывает, как это может выглядеть, как показано ниже:

[!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]

Функции обработчика для отдельных команд обычно не принимают никаких параметров. За исключением функций обработчика обновлений, функции обработчика для диапазонов сообщений-карты требуют дополнительного параметра, *nID*типа **UINT.** Этот параметр является первым параметром. Дополнительный параметр вмещает дополнительный идентификатор команды, необходимый для определения того, какую команду пользователь на самом деле выбрал.

Для получения дополнительной информации о требованиях к параметрам для обновления функций обработчика [см.](#_core_example_for_a_range_of_command_ids)

## <a name="example-for-a-range-of-command-ids"></a><a name="_core_example_for_a_range_of_command_ids"></a>Пример для идотов командования

Когда вы можете использовать диапазоны Один пример в обработке команд, как команда Увеличить в образце MFC [HIERSVR.](../overview/visual-cpp-samples.md) Эта команда масштабирует представление, масштабируя его между 25% и 300% от его нормального размера. Класс представления HIERSVR использует диапазон для обработки команд «Увеличить» с записью на карту сообщений, напоминающей это:

[!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]

Когда вы пишете запись на карту сообщений, вы указываете:

- Два идентисредина команды, начиная и заканчивая смежным диапазоном.

   Вот они **ID_VIEW_ZOOM25** и **ID_VIEW_ZOOM300**.

- Название функции обработчика для команд.

   Вот это `OnZoom`.

Декларация функций будет напоминать:

[!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]

Аналогичная функция обработчика обновлений, вероятно, будет более полезной. Довольно часто можно писать `ON_UPDATE_COMMAND_UI` обработчики для нескольких команд и находить себе написание или копирование одного и того же кода снова и снова. Решение заключается в том, чтобы сопоставить диапазон идонов команд с одной функцией обработчика обновлений с помощью макроса. `ON_UPDATE_COMMAND_UI_RANGE` Иди команды должен формировать смежный диапазон. Например, просмотрите `OnUpdateZoom` обработчик и его `ON_UPDATE_COMMAND_UI_RANGE` запись на карте сообщений в классе представления образца HIERSVR.

Функции обработчика обновления для отдельных команд обычно принимают один `CCmdUI*`параметр, *pCmdUI,* типа. В отличие от функций обработчика, функции обработчика обновлений для диапазонов сообщений-карты не требуют дополнительного параметра, *nID*типа **UINT.** Идентификатор команды, который необходим для определения того, `CCmdUI` какую команду пользователь на самом деле выбрал, находится в объекте.

## <a name="example-for-a-range-of-control-ids"></a><a name="_core_example_for_a_range_of_control_ids"></a>Пример диапазона идов управления

Еще один интересный случай — отображение сообщений диспетчерских уведомлений для различных иен управления для одного обработчика. Предположим, что пользователь может нажать любую из 10 кнопок. Чтобы сопоставить все 10 кнопок с одним обработчиком, запись на карту сообщений будет выглядеть следующим образом:

[!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]

Когда вы `ON_CONTROL_RANGE` пишете макрос на карте сообщений, вы указываете:

- Конкретное сообщение о контроле-уведомлении.

   Вот это **BN_CLICKED**.

- Значения идентификатора управления, связанные с смежным диапазоном элементов управления.

   Вот это **IDC_BUTTON1** и **IDC_BUTTON10.**

- Имя функции обработчика сообщений.

   Вот это `OnButtonClicked`.

При написании функции обработчика укажите дополнительный параметр **UINT,** как показано в следующем:

[!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]

Обработчик `OnButtonClicked` для одного **BN_CLICKED** сообщение не принимает никаких параметров. Тот же обработчик для ряда кнопок занимает один **UINT**. Дополнительный параметр позволяет определить конкретный элемент управления, ответственный за генерацию **BN_CLICKED** сообщения.

Код, показанный в примере, типичен: `int` преобразование значения, передаваемого в диапазон сообщения, и утверждение, что это так. После этого вы могли принять некоторые по-разному действия в зависимости от которой кнопка была щелкана.

## <a name="see-also"></a>См. также раздел

[Объявление функций обработчика сообщений](../mfc/declaring-message-handler-functions.md)
