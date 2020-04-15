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
ms.openlocfilehash: 2e810853e7c81f279039e0b3dfda5199d38deee2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319569"
---
# <a name="event-handling-principles"></a>Принципы обработки событий

Для всех обработки событий есть три шага. Вам нужно будет:

- Реализация интерфейса события на объекте.

- Сообщите источнику событий, что ваш объект хочет получать события.

- Не сообщить источник событий, когда объекту больше не нужно получать события.

Способ реализации интерфейса события будет зависеть от его типа. Интерфейс события может быть vtable, двойной или dispinterface. Определить интерфейс должен разработчик источника событий; это до вас, чтобы реализовать этот интерфейс.

> [!NOTE]
> Хотя нет никаких технических причин, по которым интерфейс события не может быть двойным, существует ряд веских причин, чтобы избежать использования дуаулов. Тем не менее, это решение, принятое дизайнером / исполнителем *источника*событий. Так как вы работаете с `sink`точки зрения события, необходимо предусмотреть возможность того, что у вас может не быть другого выбора, кроме как реализовать интерфейс двойного события. Для получения дополнительной информации о двойных интерфейсах, [см.](../atl/dual-interfaces-and-atl.md)

Консультирование источника событий может быть разбито на три этапа:

- Запрос исходного объекта для [IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer).

- Позвоните [iConnectionPointContainer::FindConnectionPoint,](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) передающее IID интересующего вас интерфейса события. В случае успеха это вернет интерфейс [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) на объект точки соединения.

- Позвоните [iConnectionPoint:: Консультирование](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) прохождения раковины `IUnknown` события. В случае успеха это `DWORD` возвращает файлы cookie, представляющие соединение.

После того как вы успешно зарегистрировали свой интерес к получению событий, методы интерфейса события объекта будут вызываться в соответствии с событиями, выпущенными исходным объектом. Если вам больше не нужно получать события, вы можете передать файл cookie обратно в точку соединения через [IConnectionPoint::Unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise). Это нарушит связь между источником и раковиной.

Будьте осторожны, чтобы избежать циклов отсылки при обработке событий.

## <a name="see-also"></a>См. также раздел

[Обработка событий](../atl/event-handling-and-atl.md)
