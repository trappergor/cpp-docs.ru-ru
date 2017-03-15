---
title: "Event Handling Principles | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "сдвоенные интерфейсы, event interfaces"
  - "обработка событий, advising event sources"
  - "обработка событий, dual event interfaces"
  - "обработка событий, реализация"
  - "интерфейсы, event and event sink"
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Event Handling Principles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

3 Общего шага на весь обработки событий.  Необходимо:  
  
-   Реализуйте интерфейс события в объекте.  
  
-   Источник события посоветуйте, что объект хочет получать события.  
  
-   Unadvise источник события, когда конкретному объекту больше не нужно получать события.  
  
 Способ, с помощью которого необходимо будет реализовать интерфейс события будет зависеть от его типа.  Интерфейс событий может быть виртуальной таблицы, двойной или диспетчерский интерфейс.  Он до конструктора источника события, чтобы определить интерфейс; это значение необходимо для реализации этого интерфейса.  
  
> [!NOTE]
>  Хотя никаких технических причине, интерфейс события не может быть двойной хороших причинам некоторые конструкции избегайте использования удваивают.  Однако это решение сделанное конструктором или разработчик *источника* события.  Поскольку вы работаете с точки зрения события `sink`, допускать возможность, что не могут иметь любой вариант, но реализация сдвоенный интерфейс события.  Дополнительные сведения о сдвоенных интерфейсах см. в разделе [Сдвоенные интерфейсы и библиотеки ATL](../atl/dual-interfaces-and-atl.md).  
  
 Advise источнику события можно разбить на шаге 3.  
  
-   Запросите исходный объект для [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857).  
  
-   Вызов [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) указав идентификатор IID интерфейса события, интересует вас.  Если успешно, оно возвратит интерфейс [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) для объекта точки подключения.  
  
-   Вызов [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) указав **IUnknown** приемника событий.  Если успешно, оно возвратит файл cookie `DWORD`, представляющий соединение.  
  
 Как только вы успешно зарегистрирован у процент при получении события, методы интерфейса события конкретного объекта будут Вызываются события инициированный в соответствии с исходным объектом.  Если которые больше не нужно получать события можно передать файл cookie обратно в точке подключения через [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608).  Это нарушит связь между источником и утонет.  
  
 Следите за тем, чтобы избежать базисные циклы обработка событий.  
  
## См. также  
 [Обработка событий](../Topic/Event%20Handling%20and%20ATL.md)