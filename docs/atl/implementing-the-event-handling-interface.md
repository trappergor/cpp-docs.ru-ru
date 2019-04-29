---
title: Реализация интерфейса обработки событий
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
ms.openlocfilehash: d977b59907266a2e0141defa8c496b1e7bc66a6c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262077"
---
# <a name="implementing-the-event-handling-interface"></a>Реализация интерфейса обработки событий

ATL помогает выполнить все три элементы, необходимые для обработки событий: реализации интерфейса событий, о том, источник события и unadvising источника события. Точные шаги, которые необходимо будет уделить зависят от типа интерфейса событий, а также требования к производительности приложения.

Ниже приведены наиболее распространенных способов реализации интерфейса с помощью ATL.

- Наследование от пользовательского интерфейса напрямую.

- Наследование от [IDispatchImpl](../atl/reference/idispatchimpl-class.md) сдвоенных интерфейсов, описанных в библиотеку типов.

- Наследование от [IDispEventImpl](../atl/reference/idispeventimpl-class.md) для диспетчерских интерфейсов, описанных в библиотеку типов.

- Наследование от [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) для диспетчерских интерфейсов, которые не описаны в библиотеке типов, или если вы хотите повысить эффективность, не удалось загрузить сведения о типе времени выполнения.

При реализации пользовательских или два интерфейса, должен сообщить источника события путем вызова [AtlAdvise](reference/connection-point-global-functions.md#atladvise) или [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise). Вам потребуется для отслеживания файлов cookie, возвращенный вызовом метода самостоятельно. Вызовите [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) Чтобы разорвать подключение.

При реализации disp-интерфейса с помощью `IDispEventImpl` или `IDispEventSimpleImpl`, следует сообщить источника события путем вызова [IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise). Вызовите [IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) Чтобы разорвать подключение.

Если вы используете `IDispEventImpl` как базовый класс составного элемента управления, источники событий, в карте приемник будет еще и негативной рекомендации автоматически с помощью [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

`IDispEventImpl` И `IDispEventSimpleImpl` класса определяют куки-файл для вас.

## <a name="see-also"></a>См. также

[Обработка событий](../atl/event-handling-and-atl.md)
