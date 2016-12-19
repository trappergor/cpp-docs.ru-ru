---
title: "Implementing a Dual Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "сдвоенные интерфейсы, реализация"
  - "IDispatchImpl - класс, implementing dual interfaces"
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing a Dual Interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно реализовать с помощью класса [IDispatchImpl](../atl/reference/idispatchimpl-class.md) сдвоенный интерфейс, который предоставляет реализацию по умолчанию `IDispatch` двойном методов в интерфейсе.  Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](http://msdn.microsoft.com/ru-ru/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
 Использовать этот класс.  
  
-   Укажите собственный сдвоенный интерфейс в библиотеке типов.  
  
-   Создайте производный класс от специализации `IDispatchImpl` \(передачи данных об интерфейсе и библиотеке типов как аргументы шаблонов\).  
  
-   Добавьте запись \(или записи\) к сопоставлению COM для предоставления сдвоенный интерфейс, через `QueryInterface`.  
  
-   Реализуйте vtable часть интерфейса в классе.  
  
-   Убедитесь, что библиотека типов, содержащие определения интерфейсов доступные объекты во время выполнения.  
  
## Мастер простых объектов ATL  
 Если нужно создать новый интерфейс и новый класс для реализации его можно использовать [Библиотеки ATL добавляет диалоговое окно класса](../ide/add-class-dialog-box.md), а затем [Мастер объекта простой библиотеки ATL](../atl/reference/atl-simple-object-wizard.md).  
  
## Мастер реализации интерфейсов  
 Если имеется существующий интерфейс можно использовать [Мастер реализации интерфейсов](../Topic/Adding%20a%20New%20Interface%20in%20an%20ATL%20Project.md) чтобы добавить необходимые записи базового класса, сопоставления и каркасные модели COM реализации метода к существующему классу.  
  
> [!NOTE]
>  Можно обработать созданный базовым классом, поэтому основной и дополнительный номера версии библиотеки типов, передаются как аргументы шаблонов к базовому классу `IDispatchImpl`.  Мастер реализации интерфейса не проверяет номер версии библиотеки типов.  
  
## Реализация интерфейса IDispatch  
 Можно использовать базовый класс, обеспечивающий реализацию `IDispatchImpl` только диспетчерский интерфейс, указав соответствующую запись в сопоставлении модели COM \(использование макроса [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) или [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md) \), пока будет библиотеку типов, описывающую соответствующий сдвоенный интерфейс.  Он скорее общий для реализации интерфейса `IDispatch` таким образом, например.  Мастер объекта библиотеки ATL простой и мастера обе реализации интерфейса предположим, что необходимо реализовать предназначен `IDispatch` таким образом, поэтому они добавляют соответствующую запись для сопоставления.  
  
> [!NOTE]
>  Библиотеки ATL предоставляет классы [IDispEventImpl](../atl/reference/idispeventimpl-class.md) и [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) чтобы помочь реализовать диспетчерских интерфейсов без использования библиотеки типов, содержащие определения, совместимой с двойного интерфейса.  
  
## См. также  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)