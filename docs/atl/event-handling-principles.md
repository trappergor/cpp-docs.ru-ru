---
title: Событие обработки принципы (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: b882a1d356a431f75be1feb6e7bd997abed41c33
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301484"
---
# <a name="event-handling-principles"></a>Принципы обработки событий

Существует три действия, общие для всех событий обработки. Вам потребуется:

- Реализация событий интерфейса для объекта.

- Уведомить источник события, объект хочет получать события.

- Когда объект больше не нужно получать события негативной рекомендации источника события.

Так, что вы реализуете интерфейс событий зависит от его типа. Интерфейс событий может быть vtable, двойной или disp-интерфейсом. Он работает в конструктор источника событий для определения интерфейса; именно для реализации этого интерфейса.

> [!NOTE]
>  Хотя нет технических причин, которые интерфейс событий не может быть двух, существует ряд причин хороший проект отказаться от использования duals. Тем не менее, это решение, внесенные средством конструктора/реализации события *источника*. Так как вы работаете с точки зрения события `sink`, вам потребуется возможность того, что у вас нет любой выбор, но реализация интерфейса двух событий. Дополнительные сведения о сдвоенных интерфейсов, см. в разделе [сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md).

О том, источник события можно разделить на три этапа:

- Объект источника [IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer).

- Вызовите [IConnectionPointContainer::FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) передав идентификатор IID интерфейса событий, которая вас интересует. Если в случае успешного выполнения возвращается [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint) интерфейса на объект точки подключения.

- Вызовите [IConnectionPoint::Advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise) передачи `IUnknown` приемника событий. Если в случае успешного выполнения возвращается `DWORD` куки-файл, представляющий соединение.

После успешной регистрации ваш интерес к получение событий методы интерфейса событий объекта будет вызываться в соответствии с события, инициируемые исходного объекта. При вам больше не нужно получать события, можно передать файл cookie обратно в точку подключения с помощью [IConnectionPoint::Unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise). Это приведет к разрыву подключения между источником и приемником.

Будьте внимательны и избегайте ссылку циклами при обработке событий.

## <a name="see-also"></a>См. также

[Обработка событий](../atl/event-handling-and-atl.md)
