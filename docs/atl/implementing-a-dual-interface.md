---
title: Реализация сдвоенный интерфейс (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34cc55e4466dba094bf70e734340b40237207f3c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="implementing-a-dual-interface"></a>Реализации сдвоенного интерфейса
Можно реализовать сдвоенный интерфейс, используя [IDispatchImpl](../atl/reference/idispatchimpl-class.md) класс, который предоставляет реализацию по умолчанию `IDispatch` методов сдвоенных интерфейсов. Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
 С помощью этого класса:  
  
-   Определите вашей сдвоенный интерфейс в библиотеке типов.  
  
-   Класс, производный от специализации `IDispatchImpl` (передать сведения о библиотеке интерфейсом и типом как аргументы шаблона).  
  
-   Добавить запись (или записи) в схему модели COM для предоставления сдвоенный интерфейс через `QueryInterface`.  
  
-   Реализация vtable частью интерфейса в классе.  
  
-   Убедитесь, что библиотека типов, содержащую определения интерфейса для объектов во время выполнения.  
  
## <a name="atl-simple-object-wizard"></a>Мастер простых объектов ATL  
 Если вы хотите создать новый интерфейс и новый класс для его реализации, можно использовать [диалоговое окно Добавление класса ATL](../ide/add-class-dialog-box.md), а затем [мастер простых объектов ATL](../atl/reference/atl-simple-object-wizard.md).  
  
## <a name="implement-interface-wizard"></a>Мастер реализации интерфейсов  
 При наличии существующего интерфейса, можно использовать [мастер реализации интерфейсов](../atl/reference/adding-a-new-interface-in-an-atl-project.md) для добавления необходимых базового класса, записях сопоставления COM. и реализации каркас метода в существующий класс.  
  
> [!NOTE]
>  Может потребоваться изменить базовый класс, созданный таким образом, чтобы номера основной и дополнительный номер версии библиотеки типов, передаются как аргументы шаблонов для вашей `IDispatchImpl` базового класса. Мастер реализации интерфейсов не проверяет номера версии библиотеки типов.  
  
## <a name="implementing-idispatch"></a>Реализация интерфейса IDispatch  
 Можно использовать `IDispatchImpl` базовый класс для реализации disp-интерфейс, просто задав соответствующую запись в схеме COM (с помощью [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) или [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) макрос), пока у вас есть библиотеку типов, описывающие соответствующего сдвоенный интерфейс. Довольно часто для реализации `IDispatch` интерфейса таким образом, например. Мастер простых объектов ATL и оба Предположим, вы планируете реализовать мастера реализации интерфейса `IDispatch` таким образом, поэтому они будет добавить соответствующую запись в схему.  
  
> [!NOTE]
>  Предлагает ATL [IDispEventImpl](../atl/reference/idispeventimpl-class.md) и [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) классы для реализации диспетчерских без необходимости библиотеку типов, содержащая определение совместимые сдвоенный интерфейс.  
  
## <a name="see-also"></a>См. также  
 [Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)

