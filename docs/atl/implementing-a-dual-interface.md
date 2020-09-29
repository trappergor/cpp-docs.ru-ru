---
title: Реализация сдвоенного интерфейса (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: 97d8cd912c85a74f3550a9ca6c7b87a9717d4075
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499557"
---
# <a name="implementing-a-dual-interface"></a>Реализация сдвоенного интерфейса

Вы можете реализовать сдвоенный интерфейс с помощью класса [IDispatchImpl](../atl/reference/idispatchimpl-class.md) , который предоставляет реализацию методов по умолчанию `IDispatch` в сдвоенном интерфейсе. Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

Чтобы использовать этот класс, сделайте следующее:

- Определите сдвоенный интерфейс в библиотеке типов.

- Создайте класс, производный от специализации `IDispatchImpl` (передайте сведения об интерфейсе и библиотеке типов в качестве аргументов шаблона).

- Добавьте запись (или записи) в карту COM, чтобы предоставить сдвоенный интерфейс через `QueryInterface` .

- Реализуйте часть интерфейса vtable в своем классе.

- Убедитесь, что библиотека типов, содержащая определение интерфейса, доступна для объектов во время выполнения.

## <a name="atl-simple-object-wizard"></a>Мастер простых объектов ATL

Если вы хотите создать новый интерфейс и новый класс для его реализации, можно использовать [диалоговое окно Добавление класса ATL](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box), а затем [мастер простых объектов ATL](../atl/reference/atl-simple-object-wizard.md).

## <a name="implement-interface-wizard"></a>Мастер реализации интерфейсов

При наличии существующего интерфейса можно использовать [Мастер реализации интерфейса](../atl/reference/adding-a-new-interface-in-an-atl-project.md) , чтобы добавить необходимый базовый класс, записи карты com и скелет реализации методов в существующий класс.

> [!NOTE]
> Может потребоваться изменить созданный базовый класс таким образом, чтобы основной и дополнительный номера версий библиотеки типов передавались как аргументы шаблона в `IDispatchImpl` базовый класс. Мастер реализации интерфейса не проверяет номер версии библиотеки типов.

## <a name="implementing-idispatch"></a>Реализация IDispatch

Базовый класс можно использовать `IDispatchImpl` для предоставления реализации disp-интерфейса только путем указания соответствующей записи в сопоставлении com (с помощью [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) или [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) макроса) при условии, что имеется библиотека типов, описывающая соответствующий сдвоенный интерфейс. Такой способ реализуется довольно часто `IDispatch` , например. Мастер создания простых объектов ATL и мастер реализации интерфейса предполагают, что вы планируете реализовать `IDispatch` таким образом, чтобы они добавили соответствующую запись в карту.

> [!NOTE]
> ATL предлагает классы [IDispEventImpl](../atl/reference/idispeventimpl-class.md) и [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) , помогающие реализовать DISP-интерфейсы без использования библиотеки типов, содержащей определение совместимого сдвоенного интерфейса.

## <a name="see-also"></a>См. также раздел

[Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)
