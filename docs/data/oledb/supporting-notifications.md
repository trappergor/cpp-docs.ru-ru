---
title: Поддержка уведомлений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f750346b0fdd8821800b012b3cdff7acc12f7897
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="supporting-notifications"></a>Поддержка уведомлений
## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>Реализация точки подключения интерфейсов для поставщика и потребителя  
 Для реализации уведомлений, должны наследовать класс поставщика [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) и [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md).  
  
 `IRowsetNotifyCP` реализует сайт поставщика для интерфейса точки подключения [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx). `IRowsetNotifyCP` реализует широковещательных функции для в точке подключения **IID_IRowsetNotify** изменений содержимого набора строк.  
  
 Обратите внимание, что необходимо также реализовать и зарегистрировать `IRowsetNotify` на объекте-получателе (приемник) с помощью [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) потребитель может обрабатывать уведомления. Сведения о реализации точки подключения интерфейса на объекте-получателе см. в разделе [получение уведомления](../../data/oledb/receiving-notifications.md).  
  
 Кроме того класс также должен содержать сопоставление, определяющее точку ввода соединения следующим образом:  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>Добавление IRowsetNotify  
 Чтобы добавить `IRowsetNotify`, необходимо добавить `IConnectionPointContainerImpl<rowset-name>` и `IRowsetNotifyCP<rowset-name>` в цепочку наследования.  
  
 Например, вот цепочку наследования для `RUpdateRowset` в [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  Образец кода может отличаться от приведенного в примере; в образце кода следует рассматривать в качестве более позднюю версию.  
  
```cpp
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan>>, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll >>,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### <a name="setting-com-map-entries"></a>Настройка сопоставления COM  
 Необходимо также добавьте следующее сопоставление COM в наборе строк:  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 Эти макросы разрешить всем вызов `QueryInterface` для точки подключения контейнера (основы `IRowsetNotify`) для поиска на запрошенный интерфейс для поставщика. Пример демонстрирует использование точки подключения см. в образце ATL POLYGON и учебник.  
  
### <a name="setting-connection-point-map-entries"></a>Настройка компонентов сопоставления точек подключения  
 Необходимо также добавить сопоставление точки подключения. Он должен выглядеть примерно так:  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 Сопоставление точки подключения позволяет компоненту, поиск `IRowsetNotify` интерфейс, чтобы найти его в поставщике.  
  
### <a name="setting-properties"></a>Настройка свойств  
 Также необходимо добавить следующие свойства для используемого поставщика. Необходимо добавить свойства, основанных на интерфейсах, которые вы поддерживаете.  
  
|Свойство.|Добавить в случае поддержки|  
|--------------|------------------------|  
|**DBPROP_IConnectionPointContainer**|Всегда|  
|**DBPROP_NOTIFICATIONGRANULARITY**|Всегда|  
|**DBPROP_NOTIFICATIONPHASES**|Всегда|  
|**DBPROP_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE**|Всегда|  
|**DBPROP_NOTIFYROWFIRSTCHANGE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWSETRELEASE**|Всегда|  
|**DBPROP_NOTIFYROWUNDOCHANGE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 Большая часть реализации уведомлений уже внедрена в шаблоны поставщика OLE DB. Если не добавить `IRowsetNotifyCP` в цепочке наследования, компилятор удаляет весь код из потока компиляции, таким образом, делая его меньшего размера.  
  
## <a name="see-also"></a>См. также  
 [Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)