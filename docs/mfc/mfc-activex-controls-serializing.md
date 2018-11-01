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
ms.openlocfilehash: fddd09ad7a3dc7d9211480bb21ac434419a48758
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522217"
---
# <a name="mfc-activex-controls-serializing"></a>Элементы управления ActiveX в MFC. Сериализация

В этой статье описывается сериализация элемента управления ActiveX. Сериализация — это процесс чтение или запись в среде постоянного хранения, например файл на диске. Библиотека Microsoft Foundation Class (MFC) предоставляет встроенную поддержку для сериализации в классе `CObject`. `COleControl` расширяет эту функцию на элементы управления ActiveX при помощи свойства механизм exchange.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, заменяющие ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

Сериализация для элементов управления ActiveX реализована путем переопределения [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Эта функция вызывается во время загрузки и сохранения объекта элемента управления, хранит все свойства, реализовано с помощью переменную-член или переменную-член с уведомления об изменениях.

В следующих разделах рассматриваются основные вопросы, относящиеся к сериализации элемента управления ActiveX:

- Реализация `DoPropExchange` функции для сериализации объекта элемента управления

- [Настройка процесса сериализации](#_core_customizing_the_default_behavior_of_dopropexchange)

- [Реализация поддержки версии](#_core_implementing_version_support)

##  <a name="_core_implementing_the_dopropexchange_function"></a> Реализация функции DoPropExchange

При использовании мастера элементов управления ActiveX, чтобы создать проект элемента управления, несколько функций обработчика по умолчанию автоматически добавляются в класс элемента управления, включая реализацию по умолчанию [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). В примере показан код, добавленный к классам, созданных с помощью мастера управления ActiveX:

[!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]

Если вы хотите сделать постоянные свойство, измените `DoPropExchange` путем добавления вызова функции exchange свойство. В следующем примере показано сериализации пользовательского свойства Boolean CircleShape, где CircleShape свойство имеет значение по умолчанию **TRUE**:

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]

В следующей таблице перечислены функции exchange возможные свойства, которые можно использовать для сериализации свойств элемента управления:

|Свойства функции обмена данными|Цель|
|---------------------------------|-------------|
|**PX_Blob)**|Сериализует тип данных свойства больших двоичных объектов (BLOB).|
|**PX_Bool)**|Сериализует тип логического свойства.|
|**PX_Color)**|Сериализует свойство цвета типа.|
|**PX_Currency)**|Сериализует тип **CY** свойство (валюта).|
|**PX_Double)**|Сериализует тип **двойные** свойство.|
|**PX_Font)**|Сериализует тип свойства шрифтов.|
|**PX_Float)**|Сериализует тип **float** свойство.|
|**PX_IUnknown)**|Сериализует свойство типа `LPUNKNOWN`.|
|**PX_Long)**|Сериализует тип **long** свойство.|
|**PX_Picture)**|Сериализует тип свойства изображения.|
|**PX_Short)**|Сериализует тип **короткие** свойство.|
|**(PXstring)**|Сериализует тип `CString` свойства.|
|**PX_ULong)**|Сериализует тип **ULONG** свойство.|
|**PX_UShort)**|Сериализует тип **USHORT** свойство.|

Дополнительные сведения об этих функциях свойства exchange см. в разделе [сохраняемости OLE элементов управления](../mfc/reference/persistence-of-ole-controls.md) в *Справочник по библиотеке MFC*.

##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> Настройка поведения по умолчанию DoPropExchange

Реализация по умолчанию `DoPropertyExchange` (как показано в предыдущем разделе) вызывает метод базового класса `COleControl`. Это сериализует набор свойств, поддерживаемых автоматически `COleControl`, которая использует больше места, чем сериализации только пользовательские свойства элемента управления. Удаление этого вызова позволяет объекта для сериализации только те свойства, которые вы считаете важными. Все состояния стандартное свойство элемента управления реализовала не будут сериализованы при сохранении или загрузке объект элемента управления, можно явно добавить **PX_** вызывает для них.

##  <a name="_core_implementing_version_support"></a> Реализация поддержки версии

Поддержка версий включает измененный элемент управления ActiveX для добавления новых свойств постоянных и по-прежнему иметь возможность обнаружить и загрузить постоянное состояние, созданные в более ранней версии элемента управления. Чтобы изменить версию элемента управления как часть постоянные данные, вызовите [COleControl::ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) в элементе управления `DoPropExchange` функции. Этот вызов вставляется автоматически в том случае, если элемент управления ActiveX был создан с помощью мастера элементов управления ActiveX. Если не требуется поддержка версий, он может быть удален. Тем не менее, затраты на размер элемента управления является очень мелкий (4 байта) Повышенная гибкость обеспечивается тем, предоставляющий поддерживаемые версии.

Если элемент управления не был создан с помощью мастера элементов управления ActiveX, добавьте вызов `COleControl::ExchangeVersion` путем вставки следующую строку в начале вашей `DoPropExchange` функция (перед вызовом `COleControl::DoPropExchange`):

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

Можно использовать любой **DWORD** как номер версии. Использовать проекты, созданные с помощью мастера управления ActiveX `_wVerMinor` и `_wVerMajor` по умолчанию. Это глобальные константы, определенные в файле реализации класса элемента управления ActiveX проекта. В оставшейся части вашего `DoPropExchange` функции, можно вызвать [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion) в любое время для получения версии сохранения или получения.

В следующем примере версия 1 Этот пример элемента управления содержит только свойство «ReleaseDate». Версия 2 добавляет свойство «OriginalDate». Если элемент управления настраивается для загрузки сохраняемого состояния из более старой версии, конструктор инициализирует переменную-член для нового свойства на значение по умолчанию.

[!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

По умолчанию элемент управления «преобразует» старые данные в формат последней версии. Например если версия 2 элемент управления загружает данные, которые были сохранены в версии 1, запишет формат версии 2 при его сохранении еще раз. Если требуется, чтобы элемент управления для сохранения данных в формате последней операции чтения, передайте **FALSE** качестве третьего параметра при вызове `ExchangeVersion`. Это третий параметр является необязательным и **TRUE** по умолчанию.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

