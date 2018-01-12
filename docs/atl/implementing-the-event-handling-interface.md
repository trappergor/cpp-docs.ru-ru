---
title: "Реализация интерфейса обработки события | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9226cf2630ad18651f9bda2f154f49b5b739a433
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-the-event-handling-interface"></a>Реализация интерфейса обработки событий
ATL можно выполнить с помощью всех трех элементов, необходимых для обработки событий: реализация событий интерфейса, предупреждающее о том, источник события и unadvising источника события. Конкретные шаги, необходимые для использования зависят от типа интерфейса событий, а также требования к производительности приложения.  
  
 Ниже перечислены наиболее распространенные способы реализации интерфейса с использованием ATL  
  
-   Наследование непосредственно из пользовательского интерфейса.  
  
-   Наследование от [IDispatchImpl](../atl/reference/idispatchimpl-class.md) сдвоенных интерфейсов, описанный в библиотеке типов.  
  
-   Наследование от [IDispEventImpl](../atl/reference/idispeventimpl-class.md) для диспетчерских, описанный в библиотеке типов.  
  
-   Наследование от [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) для диспетчера интерфейсов, которые не описаны в библиотеке типов, или если вы хотите повысить эффективность, не удалось загрузить сведения о типе во время выполнения.  
  

 При реализации пользовательских или двойного интерфейса следует сообщить источнику события путем вызова [AtlAdvise](reference/connection-point-global-functions.md#atladvise) или [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise). Необходимо для отслеживания файлов cookie, возвращенного вызовом. Вызовите [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) Чтобы разорвать связь.  

  
 Если вы реализуете disp-интерфейса с помощью `IDispEventImpl` или `IDispEventSimpleImpl`, следует рекомендовать источник события путем вызова [IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise). Вызовите [IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) Чтобы разорвать связь.  
  
 Если вы используете `IDispEventImpl` как базовый класс составного элемента управления, перечисленный в карте приемник источников событий будет желательно и unadvised автоматически с помощью [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).  
  
 `IDispEventImpl` И `IDispEventSimpleImpl` классы управления куки-файл для вас.  
  
## <a name="see-also"></a>См. также  
 [Обработка событий](../atl/event-handling-and-atl.md)

