---
title: "Получение уведомлений | Microsoft Docs"
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
  - "события [C++], напоминания в OLE DB"
  - "уведомления [C++], события"
  - "уведомления [C++], потребители OLE DB"
  - "потребители OLE DB, уведомления"
  - "поставщики OLE DB, уведомления"
  - "получение напоминаний в OLE DB"
  - "наборы строк, уведомления о событиях"
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Получение уведомлений
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В OLE DB предусматриваются интерфейсы для получения уведомлений в случае возникновения событий.  Дополнительные сведения см. в разделе [Уведомления объектов OLE DB](https://msdn.microsoft.com/en-us/library/ms725406.aspx) в *справочнике программиста OLE DB*.  При настройке этих событий используется стандартный механизм точки подключения COM.  Например, для получения событий в объекте ATL посредством интерфейса `IRowsetNotify` следует реализовать интерфейс `IRowsetNotify`. Для этого добавьте интерфейс `IRowsetNotify` в список производных объектов класса и предоставьте его с помощью макроса **COM\_INTERFACE\_ENTRY**.  
  
 В интерфейсе `IRowsetNotify` предусматривается три метода, которые вызываются в различных ситуациях.  Чтобы реагировать только на один из этих методов, используйте класс [IRowsetNotifyImpl](../Topic/IRowsetNotifyImpl%20Class.md), который возвращает значение **E\_NOTIMPL** для нужного метода.  
  
 При создании набора строк необходимо указать поставщику, что возвращаемый объект набора строк должен поддерживать интерфейс **IConnectionPointContainer**, который используется для настройки уведомлений.  
  
 В следующем примере описывается порядок открытия набора строк из объекта ATL, а также настройка приемника уведомлений с помощью функции `AtlAdvise`.  Функция `AtlAdvise` возвращает файл cookie, который используется при вызове функции `AtlUnadvise`.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  
product.Open(session, _T("Products"), &propset);  
  
AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)