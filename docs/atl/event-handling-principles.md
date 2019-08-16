---
title: Принципы обработки событий (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: 066c8db60afed31ceba1c9ef6f4a10d5f842e608
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492147"
---
# <a name="event-handling-principles"></a>Принципы обработки событий

Существует три основных этапа обработки всех событий. Вам потребуется:

- Реализуйте интерфейс событий для объекта.

- Посоветуйте источнику событий, что объект хочет получать события.

- Если объекту больше не требуется получение событий, следует снять с него порекомендовать источник события.

Способ реализации интерфейса событий будет зависеть от его типа. Интерфейсом событий может быть vtable, Dual или DISP. Для определения интерфейса требуется конструктор источника событий. Вам нужно реализовать этот интерфейс.

> [!NOTE]
>  Хотя не существует технических причин того, что интерфейс событий не может быть сдвоенным, существует ряд хороших причин, по которым не следует использовать двойные конструкции. Однако это решение, принятое разработчиком или разработчиком *источника*события. Так как вы работаете с точки зрения события `sink`, необходимо разрешить возможность отсутствия какого-либо выбора, но реализовать сдвоенный интерфейс событий. Дополнительные сведения о сдвоенных интерфейсах см. в разделе [сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md).

Рекомендуется разделить источник событий на три этапа:

- Запросите исходный объект для [IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer).

- Вызовите [IConnectionPointContainer:: финдконнектионпоинт](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) , передав идентификатор IID интересующего вас интерфейса событий. В случае успешного выполнения будет возвращен интерфейс [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) для объекта точки подключения.

- Вызов [IConnectionPoint:: Advise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) `IUnknown` для передачи приемника событий. В случае успеха будет возвращен `DWORD` файл cookie, представляющий соединение.

После успешной регистрации интереса при получении событий методы в интерфейсе событий объекта будут вызываться в соответствии с событиями, инициированными исходным объектом. Если больше не требуется получение событий, можно передать файл cookie обратно в точку подключения через [IConnectionPoint:: unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise). Это приведет к разрыву соединения между источником и приемником.

Будьте внимательны, чтобы избежать циклических ссылок при обработке событий.

## <a name="see-also"></a>См. также

[Обработка событий](../atl/event-handling-and-atl.md)
