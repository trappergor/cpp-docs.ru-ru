---
title: "ATL Event Handling Summary | Microsoft Docs"
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
  - "обработка событий, реализация"
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Event Handling Summary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В общем случае обработка событий модели COM относительно простой процесс.  3 Основных этапов:  
  
-   Реализуйте интерфейс события в объекте.  
  
-   Источник события посоветуйте, что объект хочет получать события.  
  
-   Unadvise источник события, когда конкретному объекту больше не нужно получать события.  
  
## Реализация интерфейса  
 4 Основных способа реализации интерфейса с использованием библиотеки ATL.  
  
|Является производным от|Пригодный для типа интерфейса|Необходимо реализовать все methods\*|Требует наличия библиотеки типов во время выполнения|  
|-----------------------------|-----------------------------------|------------------------------------------|----------------------------------------------------------|  
|Интерфейс|Vtable|Да|Нет|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Сдвоенный|Да|Да|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Диспетчерский интерфейс|Нет|Да|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Диспетчерский интерфейс|Нет|Нет|  
  
 \* При использовании классов поддержки библиотеки ATL, никогда не требуется реализовать методы **IUnknown** или `IDispatch` вручную.  
  
## Advise и Unadvising источник события  
 3 Основных способа advise и unadvising источник событий с использованием библиотеки ATL.  
  
|Посоветуйте функции|Функция Unadvise|Наиболее подходящий для использования с|Необходимо хранить отслеживание cookie?|Комментарии|  
|-------------------------|----------------------|---------------------------------------------|---------------------------------------------|-----------------|  
|[AtlAdvise](../Topic/AtlAdvise.md), [CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|[AtlUnadvise](../Topic/AtlUnadvise.md)|Vtable или двойные интерфейсы|Да|`AtlAdvise` глобальной функции библиотеки ATL.  `CComPtrBase::Advise` используется [CComPtr](../atl/reference/ccomptr-class.md) и [CComQIPtr](../atl/reference/ccomqiptr-class.md).|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) или [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Нет|Чем меньше параметров `AtlAdvise` поскольку базовый класс выполняет дополнительную работу.|  
|[CComCompositeControl::AdviseSinkMap \(TRUE\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|[CComCompositeControl::AdviseSinkMap \(FALSE\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|Элементы управления ActiveX в нескольких элементах управления|Нет|`CComCompositeControl::AdviseSinkMap` советует всему сопоставлению приемников записей в случае.  Эти же unadvises функции записи.  Этот метод вызывается классом `CComCompositeControl` автоматически.|  
|[CAxDialogImpl::AdviseSinkMap \(TRUE\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|[CAxDialogImpl::AdviseSinkMap \(FALSE\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|Элементы управления ActiveX в диалоговом окне|Нет|`CAxDialogImpl::AdviseSinkMap` советует и unadvises все элементы управления ActiveX в ресурс диалогового окна.  Это выполняется автоматически.|  
  
## См. также  
 [Обработка событий](../Topic/Event%20Handling%20and%20ATL.md)   
 [Supporting IDispEventImpl](../atl/supporting-idispeventimpl.md)