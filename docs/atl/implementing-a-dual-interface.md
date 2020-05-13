---
title: Реализация двойного интерфейса (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: a85597adad045bee3edb5cc3ed63c72a22fa08fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319469"
---
# <a name="implementing-a-dual-interface"></a>Реализация двойного интерфейса

Вы можете реализовать двойной интерфейс с помощью класса [IDispatchImpl,](../atl/reference/idispatchimpl-class.md) который обеспечивает реализацию `IDispatch` методов по умолчанию в двойном интерфейсе. Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

Для использования этого класса:

- Определите ваш двойной интерфейс в библиотеке типов.

- Извлеките свой класс `IDispatchImpl` из специализации (передайте информацию об интерфейсе и библиотеке ввода в качестве аргументов шаблона).

- Добавьте запись (или записи) на карту COM, `QueryInterface`чтобы разоблачить двойной интерфейс через .

- Реализуйте vtable часть интерфейса в классе.

- Убедитесь, что библиотека типов, содержащая определение интерфейса, доступна для объектов во время выполнения.

## <a name="atl-simple-object-wizard"></a>Мастер простых объектов ATL

Если вы хотите создать новый интерфейс и новый класс для его реализации, вы можете использовать [поле диалога ATL Add Class,](../ide/add-class-dialog-box.md)а затем [ATL Simple Object Wizard.](../atl/reference/atl-simple-object-wizard.md)

## <a name="implement-interface-wizard"></a>Мастер реализации интерфейсов

Если у вас есть существующий интерфейс, вы можете использовать [мастер интерфейса реализации,](../atl/reference/adding-a-new-interface-in-an-atl-project.md) чтобы добавить необходимый базовый класс, записи карты COM и реализации скелетного метода к существующему классу.

> [!NOTE]
> Возможно, потребуется настроить сгенерированный базовый класс таким образом, чтобы основные и `IDispatchImpl` незначительные номера версий библиотеки типов передавались в качестве аргументов шаблона в базовый класс. Мастер интерфейса реализации не проверяет номер библиотеки типа для вас.

## <a name="implementing-idispatch"></a>Внедрение IDispatch

Базовый `IDispatchImpl` класс можно использовать для обеспечения реализации дисинтерфейса, просто указав соответствующую запись на карте COM (с помощью [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) или [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) макроса), если у вас есть библиотека типов, описывающая соответствующий двойной интерфейс. Например, довольно часто `IDispatch` можно реализовать интерфейс таким образом. AtL Simple Object Wizard и Implement Interface Wizard `IDispatch` предполагают, что вы собираетесь реализовать таким образом, поэтому они добавят соответствующую запись на карту.

> [!NOTE]
> ATL предлагает классы [IDispEventImpl](../atl/reference/idispeventimpl-class.md) и [IDispEventSimpleImpl,](../atl/reference/idispeventsimpleimpl-class.md) чтобы помочь вам реализовать дисинтерфейсы, не требуя библиотеки типов, содержащей определение совместимого двойного интерфейса.

## <a name="see-also"></a>См. также раздел

[Двойные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)
