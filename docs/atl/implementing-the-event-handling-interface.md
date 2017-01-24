---
title: "Implementing the Event Handling Interface | Microsoft Docs"
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
  - "ATL - библиотека, обработка событий"
  - "обработка событий, ATL - библиотека"
  - "интерфейсы, event and event sink"
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing the Event Handling Interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотеки ATL помогает со всеми 3 элементов, необходимые для обработки событий: реализация интерфейса события, советующ источнику события и unadvising источник события.  Точные шаги необходимо предпринимать зависит от типа интерфейса события и требования по производительности приложения.  
  
 Наиболее распространенные способы реализации интерфейса с использованием библиотеки ATL:  
  
-   Наследование от пользовательского интерфейса напрямую.  
  
-   Создание класса, производного от [IDispatchImpl](../atl/reference/idispatchimpl-class.md) сдвоенных интерфейсов, описанных в библиотеке типов.  
  
-   Создание класса, производного от [IDispEventImpl](../atl/reference/idispeventimpl-class.md) для диспетчерских интерфейсов, описанных в библиотеке типов.  
  
-   Создание класса, производного от [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) для диспетчерских интерфейсов не описанных в библиотеке типов или нужно повысить эффективность не загружая данные о типе во время выполнения.  
  
 При реализации пользовательского или сдвоенный интерфейс, необходимо advise источнику события путем вызова [AtlAdvise](../Topic/AtlAdvise.md) или [CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md).  Вам самостоятельно будет отслеживать cookie, возвращенного вызовом.  Вызов [AtlUnadvise](../Topic/AtlUnadvise.md) для прерывания соединение.  
  
 Если реализуется с помощью `IDispEventImpl` или диспетчерский интерфейс `IDispEventSimpleImpl`, необходимо advise источнику события путем вызова [IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md).  Вызов [IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) для прерывания соединение.  
  
 При использовании `IDispEventImpl` в качестве базового класса составного элемента управления источников событий, перечисленные в сопоставлении приемников будут advise и unadvised автоматически с помощью [CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md).  
  
 Классы `IDispEventImpl` и `IDispEventSimpleImpl` управляют файл cookie.  
  
## См. также  
 [Обработка событий](../Topic/Event%20Handling%20and%20ATL.md)