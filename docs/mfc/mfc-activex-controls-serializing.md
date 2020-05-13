---
title: Элементы управления ActiveX в MFC. Сериализация
ms.date: 09/12/2018
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
helpviewer_keywords:
- MFC ActiveX controls [MFC], version support
- wVerMinor global constant [MFC]
- GetVersion method [MFC]
- ExchangeVersion method [MFC]
- MFC ActiveX controls [MFC], serializing
- DoPropExchange method [MFC]
- versioning ActiveX controls
- wVerMajor global constant
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
ms.openlocfilehash: d804486b612906f537b6ed1665dfc0cec5149826
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364560"
---
# <a name="mfc-activex-controls-serializing"></a>Элементы управления ActiveX в MFC. Сериализация

В этой статье обсуждается, как сериализовать элемент управления ActiveX. Сериализация — это процесс чтения или записи в постоянном носителе, например дискового файла. Библиотека Microsoft Foundation Class (MFC) предоставляет встроенную `CObject`поддержку сериализации в классе. `COleControl`расширяет эту поддержку для контроля ActiveX с помощью механизма обмена имуществом.

>[!IMPORTANT]
> ActiveX является устаревшей технологией, которая не должна использоваться для новых разработок. Для получения дополнительной информации о современных технологиях, которые заменяли ActiveX, [см.](activex-controls.md)

Сериализация для элементов управления ActiveX осуществляется с помощью переопределения [COleControl: :DoPropExchange.](../mfc/reference/colecontrol-class.md#dopropexchange) Эта функция, вызванная во время загрузки и сохранения объекта управления, хранит все свойства, реализованные с переменной члена или переменной члена, с уведомлением об изменении.

Следующие темы охватывают основные вопросы, связанные с сериализом управления ActiveX:

- Реализация `DoPropExchange` функции для сериализации объекта управления

- [Настройка процесса сериализации](#_core_customizing_the_default_behavior_of_dopropexchange)

- [Поддержка версии](#_core_implementing_version_support)

## <a name="implementing-the-dopropexchange-function"></a><a name="_core_implementing_the_dopropexchange_function"></a>Реализация функции DoPropExchange

При использовании ActiveX Control Wizard для генерации проекта управления в класс управления автоматически добавляются несколько функций обработчика по умолчанию, включая реализацию [COleControl::DoPropExchange.](../mfc/reference/colecontrol-class.md#dopropexchange) Ниже приводится код, добавленный в классы, созданные с помощью Мастера управления ActiveX:

[!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]

Если вы хотите сделать свойство стойким, измените, `DoPropExchange` добавив вызов в функцию обмена свойствами. Следующий пример демонстрирует сериализацию пользовательского свойства Boolean CircleShape, где свойство CircleShape имеет значение по умолчанию **TRUE:**

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]

В следующей таблице перечислены возможные функции обмена свойствами, которые можно использовать для сериализации свойств элемента управления:

|Функции обмена недвижимостью|Цель|
|---------------------------------|-------------|
|**PX_Blob()**|Сериализирует свойство данных типа Binary Large Object (BLOB).|
|**PX_Bool()**|Сериализирует свойство типа Boolean.|
|**PX_Color()**|Сериализирует свойство цвета типа.|
|**PX_Currency()**|Сериализирует свойство типа **CY** (валюта).|
|**PX_Double()**|Сериализирует **двойное** свойство типа.|
|**PX_Font()**|Сериализирует свойство типа шрифта.|
|**PX_Float()**|Сериализирует свойство **поплавка** типа.|
|**PX_IUnknown()**|Сериализирует свойство `LPUNKNOWN`типа .|
|**PX_Long()**|Сериализирует свойство **длиной** типа.|
|**PX_Picture()**|Сериализирует свойство типа Picture.|
|**PX_Short()**|Сериализирует **краткое** свойство типа.|
|**PXstring ()**|Сериализирует свойство типа. `CString`|
|**PX_ULong()**|Сериализирует свойство **типа ULONG.**|
|**PX_UShort()**|Сериализирует свойство типа **USHORT.**|

Для получения дополнительной информации об этих функциях обмена *MFC Reference*имуществом, [см.](../mfc/reference/persistence-of-ole-controls.md)

## <a name="customizing-the-default-behavior-of-dopropexchange"></a><a name="_core_customizing_the_default_behavior_of_dopropexchange"></a>Настройка поведения DoPropExchange по умолчанию

Реализация по `DoPropertyExchange` умолчанию (как показано в предыдущей теме) делает вызов базового класса. `COleControl` Это сериализирует набор свойств, `COleControl`автоматически поддерживаемых , который использует больше места для хранения, чем сериализация только пользовательские свойства управления. Удаление этого вызова позволяет объекту сериализировать только те свойства, которые вы считаете важными. Любое свойство запасов, реализованное элементом управления, не будет сериализовано при сохранении или загрузке объекта управления, если вы явно не добавите **PX_** вызовов для них.

## <a name="implementing-version-support"></a><a name="_core_implementing_version_support"></a>Поддержка версии

Поддержка версии позволяет пересмотренному элементу управления ActiveX добавлять новые стойкие свойства и по-прежнему иметь возможность обнаруживать и загружать постоянное состояние, созданное более ранней версией управления. Чтобы сделать версию элемента управления доступной как часть его постоянных данных, `DoPropExchange` позвоните [COleControl::ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) в функции управления. Этот вызов автоматически вставляется, если элемент управления ActiveX был создан с помощью мастера управления ActiveX. Он может быть удален, если поддержка версии не требуется. Тем не менее, стоимость в размере управления очень мала (4 байт) для дополнительной гибкости, что поддержка версии обеспечивает.

Если элемент управления не был создан с помощью `COleControl::ExchangeVersion` Мастера управления ActiveX, добавьте `DoPropExchange` вызов, вставив следующую строку в начале функции (до вызова): `COleControl::DoPropExchange`

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

Вы можете использовать любой **DWORD** в качестве номера версии. Проекты, генерируемые `_wVerMinor` использованием `_wVerMajor` Мастера управления ActiveX и по умолчанию. Это глобальные константы, определяемые в файле реализации класса управления ActiveX проекта. В оставшейся `DoPropExchange` части функции, вы можете позвонить [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion) в любое время, чтобы получить версию вы сохранения или получения.

В следующем примере версия 1 этого элемента управления имеет только свойство "ReleaseDate". Версия 2 добавляет свойство "OriginalDate". Если элемент управления проинструктирован для загрузки постоянного состояния из старой версии, он инициализирует переменную элемента для нового свойства к значению по умолчанию.

[!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

По умолчанию элемент управления "преобразует" старые данные в последний формат. Например, если версия 2 элемента управления загружает данные, сохраненные в версии 1, она напишет формат версии 2 при повторном сохранении. Если вы хотите, чтобы элемент управления сохранял данные в формате последнего чтения, передайте **FALSE** в качестве третьего параметра при вызове. `ExchangeVersion` Этот третий параметр является необязательным и **является правдой** по умолчанию.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)
