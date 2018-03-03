---
title: "Обработка принципы (ATL) событий | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6ec61751e16bd67686a983b43c79fea138b3fa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="event-handling-principles"></a>Принципы обработки событий
Существует три действия, общие для всех обработки событий. Требуется:  
  
-   Реализует интерфейс событий объекта.  
  
-   Рекомендуется использовать источник события объекта хочет получать события.  
  
-   Разъединения источника события, если объект больше не нужна для получения событий.  
  
 Способ, что будет реализован интерфейс события будет зависеть от его типа. Интерфейс событий может быть vtable, двойная или диспетчерский интерфейс. Он работает в конструктор источника событий для определения интерфейса; именно для реализации этого интерфейса.  
  
> [!NOTE]
>  Несмотря на технические причины, по которым интерфейс событий не может быть двух, существует ряд причин для правильной разработки избегать использования duals. Тем не менее, это решение, внесенных в конструкторе или исполнитель события *источника*. Так как вы работаете с точки зрения события `sink`, требуется возможность того, что у вас нет любой выбор, но реализует интерфейс два события. Дополнительные сведения о сдвоенных интерфейсов см. в разделе [сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md).  
  
 О том, источник события можно разделить на три этапа:  
  
-   Исходный объект для запроса [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857).  
  
-   Вызовите [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) передав идентификатор IID интерфейса событий, которые нужно просмотреть. При успешном выполнении возвращается [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) интерфейс для объекта точки подключения.  
  
-   Вызовите [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) передачи **IUnknown** приемника событий. При успешном выполнении возвращается `DWORD` куки-файл, представляющий соединение.  
  
 После успешной регистрации ваш интерес при получении события методы интерфейса событий объекта будет вызываться в соответствии с событий, произошедших в исходный объект. Если больше нет необходимости для получения событий, можно передать куки-файл обратно в точку подключения через [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608). Это приведет к разрыву соединения между источником и приемником.  
  
 Будьте внимательны и не ссылка циклами при обработке событий.  
  
## <a name="see-also"></a>См. также  
 [Обработка событий](../atl/event-handling-and-atl.md)

