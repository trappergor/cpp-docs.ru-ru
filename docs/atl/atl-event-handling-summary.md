---
title: Обработка Сводка событий ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a938bd072ea8df30e64cce28fbf0709f08547d28
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atl-event-handling-summary"></a>Сводка обработки событий ATL
Как правило обработка событий COM — это относительно простой процесс. Существует три основных этапа:  
  
-   Реализует интерфейс событий объекта.  
  
-   Рекомендуется использовать источник события объекта хочет получать события.  
  
-   Разъединения источника события, если объект больше не нужна для получения событий.  
  
## <a name="implementing-the-interface"></a>Реализация интерфейса  
 Существует четыре основных способа реализации интерфейса с использованием библиотеки ATL.  
  
|Производные от|Подходит для типа интерфейса|Необходимо реализовать все методы *|Требуется библиотеку типов во время выполнения|  
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|  
|Интерфейс|Таблицы vtable|Да|Нет|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Два двухъядерных|Да|Да|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Disp-интерфейс|Нет|Да|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Disp-интерфейс|Нет|Нет|  
  
 \* При использовании классов поддержки ATL, никогда не требуется реализовывать **IUnknown** или `IDispatch` методы вручную.  
  
## <a name="advising-and-unadvising-the-event-source"></a>О том и Unadvising источник события  
 Существует три основных способа о том, и unadvising источник событий, с использованием библиотеки ATL.  
  
|Уведомить функции|Функция разъединения|Наиболее подходящий для использования с|Требуется для отслеживания куки-файл|Комментарии|  
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|  

|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)| Vtable или сдвоенные интерфейсы | Да | `AtlAdvise` глобальная функция ATL. `CComPtrBase::Advise` используется [CComPtr](../atl/reference/ccomptr-class.md) и [CComQIPtr](../atl/reference/ccomqiptr-class.md). |  

|[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) или [ IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)| Не | Меньшее число параметров, чем `AtlAdvise` , так как большую часть работы выполняет базовый класс. |  
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)| Элементы управления ActiveX в составных элементах управления | Не | `CComCompositeControl::AdviseSinkMap` будет указано, все операции приемника событий карты. Функция с тем же unadvises записи. Этот метод автоматически вызывается `CComCompositeControl` класс. |  
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)| Элементы управления ActiveX в диалоговое окно | Не | `CAxDialogImpl::AdviseSinkMap` будет указано и unadvises все элементы управления ActiveX в диалоговом окне ресурса. Это выполняется автоматически для вас. |  
  
## <a name="see-also"></a>См. также  
 [Обработка событий](../atl/event-handling-and-atl.md)   
 [Поддержка IDispEventImpl](../atl/supporting-idispeventimpl.md)

