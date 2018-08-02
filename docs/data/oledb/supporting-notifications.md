---
title: Поддержка уведомлений | Документация Майкрософт
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
ms.openlocfilehash: a9fea13ef4a89ee2a1105702db4fe692c12643d2
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337944"
---
# <a name="supporting-notifications"></a>Поддержка уведомлений

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>Реализация точки подключения интерфейсов для поставщика и потребителя  
 Чтобы реализовать уведомлений, должен наследовать класс поставщика [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) и [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md).  
  
 `IRowsetNotifyCP` реализует поставщик сайта для точки подключения интерфейса [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx). `IRowsetNotifyCP` реализует широковещательных функции для в точке подключения `IID_IRowsetNotify` об изменениях содержимого набора строк.  
  
 Обратите внимание, что необходимо также реализовать и зарегистрировать `IRowsetNotify` на объекте-получателе (приемник) с помощью [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) потребитель может обрабатывать уведомления. Сведения о реализации интерфейса точки подключения на потребителя, см. в разделе [получение уведомлений](../../data/oledb/receiving-notifications.md).  
  
 Кроме того класс должен также содержать картой, которая определяет запись точки подключения, следующим образом:  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>Добавление IRowsetNotify  
 Чтобы добавить `IRowsetNotify`, необходимо добавить `IConnectionPointContainerImpl<rowset-name>` и `IRowsetNotifyCP<rowset-name>` в цепочку наследования.  
  
 Например, вот цепочку наследования для `RUpdateRowset` в [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  Пример кода может отличаться от приведенного в примере; пример кода следует рассматривать в качестве более новой версии.  
  
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
 Также необходимо добавить следующее в сопоставление COM в наборе строк:  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 Эти макросы запретить всем пользователям вызывать `QueryInterface` для точки подключения контейнера (основы `IRowsetNotify`) найти запрошенный интерфейс для поставщика. Пример демонстрирует использование точки подключения, см. в образце ATL POLYGON и руководства.  
  
### <a name="setting-connection-point-map-entries"></a>Установка компонентов сопоставления точек подключения  
 Необходимо также добавить сопоставление точки подключения. Он должен выглядеть примерно следующим образом:  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 Сопоставление точки подключения позволяет компоненту, ищете `IRowsetNotify` интерфейс, чтобы найти его в поставщике.  
  
### <a name="setting-properties"></a>Настройка свойств  
 Также необходимо добавить следующие свойства для поставщика. Необходимо только добавить свойства, основанные на интерфейсах, которые вы поддерживаете.  
  
|Свойство.|Добавить в случае поддержки|  
|--------------|------------------------|  
|`DBPROP_IConnectionPointContainer`|Всегда|  
|`DBPROP_NOTIFICATIONGRANULARITY`|Всегда|  
|`DBPROP_NOTIFICATIONPHASES`|Всегда|  
|`DBPROP_NOTIFYCOLUMNSET`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWDELETE`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWINSERT`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE`|Всегда|  
|`DBPROP_NOTIFYROWFIRSTCHANGE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWSETRELEASE`|Всегда|  
|`DBPROP_NOTIFYROWUNDOCHANGE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUNDODELETE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUNDOINSERT`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUPDATE`|`IRowsetUpdate`|  
  
 Большую часть реализации для уведомлений, внедренных в шаблонах поставщика OLE DB. Если вы не добавите `IRowsetNotifyCP` в цепочку наследования, компилятор удаляет весь код из потока компиляции, таким образом уменьшая размер вашего кода.  
  
## <a name="see-also"></a>См. также  
 [Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)