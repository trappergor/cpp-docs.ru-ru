---
title: Поддержка IDispEventImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d7bfd2690cf8f1ed692e6e21bf05b56e2280ce0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055667"
---
# <a name="supporting-idispeventimpl"></a>Поддержка IDispEventImpl

Класс шаблона [IDispEventImpl](../atl/reference/idispeventimpl-class.md) может использоваться для обеспечения поддержки для приемников точек подключения в вашем классе ATL. Приемник точки подключения позволяет классу обрабатывать события, инициируемые из внешнего COM-объектов. Эти приемники точки подключения, сопоставляются с картой приемника событий, предоставляемые вашим классом.

Для правильной реализации приемника точки подключения для класса, необходимо выполнить следующие действия:

- Импорт библиотеки типов для каждого внешнего объекта

- Объявите `IDispEventImpl` интерфейсы

- Объявите картой приемника событий

- Уведомлений и негативной рекомендации точек подключения

Действия, связанные в реализация приемника точки подключения выполняются путем изменения только файле заголовка (.h) вашего класса.

## <a name="importing-the-type-libraries"></a>Импорт библиотек типов

Для каждого внешнего объекта, события которого вы хотите обрабатывать необходимо импортировать библиотеку типов. Этот шаг определяет события, которые могут быть обработаны и предоставляет сведения, используемые при объявлении карты приемника событий. [#Import](../preprocessor/hash-import-directive-cpp.md) директива может использоваться для выполнения этой задачи. Для добавления необходимой `#import` строки директив для каждого интерфейса диспетчеризации, которые будут поддерживаться в файл заголовка (.h) вашего класса.

Следующий пример импортирует библиотеку типов внешнего сервера COM (`MSCAL.Calendar.7`):

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
>  Необходимо создать отдельный `#import` инструкции для каждого внешних библиотек типов, которые будут поддерживаться.

## <a name="declaring-the-idispeventimpl-interfaces"></a>Объявление интерфейсов IDispEventImpl

Теперь, после импорта библиотек типов каждого интерфейса диспетчеризации, необходимо объявить отдельные `IDispEventImpl` интерфейсы для каждого интерфейса внешних диспетчеризации. Измените объявление класса, добавив `IDispEventImpl` объявление для каждого объекта внешнего интерфейса. Дополнительные сведения о параметрах см. в разделе [IDispEventImpl](../atl/reference/idispeventimpl-class.md).

В следующем коде объявляется два приемников точек подключения для `DCalendarEvents` интерфейса для COM-объект, реализованный классом `CMyCompositCtrl2`:

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>Объявление картой приемника событий

В порядке для уведомлений о событиях будут обрабатываться для правильной работы ваш класс должен направлять каждое событие в его правильный обработчик. Это достигается путем объявления картой приемника событий.

Библиотека ATL предоставляет несколько макросов [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map), [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map), и [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex), который упростить это сопоставление. Стандартный формат выглядит следующим образом:

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

В следующем примере объявляется картой приемника событий с двумя обработчиками событий:

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

Реализация почти завершена. Последний шаг касается расхваливают и unadvising внешних интерфейсов.

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>О том и Unadvising интерфейсы IDispEventImpl

Последним шагом является реализация метода, который будет соединения (или разъединения) все точки подключения в соответствующие моменты времени. Этот о том, необходимо выполнить до связи между внешним клиентам и объекта могут иметь место. Прежде чем объект становится видимым, каждого диспетчеризации внешний интерфейс, поддерживаемый объект запрашивается для исходящих интерфейсов. Подключения и ссылку на исходящий интерфейс используется для обработки событий из объекта. Эта процедура называется «спроса».

После завершения объекта с помощью внешних интерфейсов исходящих интерфейсов должны уведомляться что они больше не используется вашим классом. Этот процесс называется «unadvising».

Особенности COM-объектов эта процедура отличается по сведений и выполнение, между реализациями. Эти сведения выходят за рамки этой статьи и не описываются.

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)

