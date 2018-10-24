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
ms.openlocfilehash: 73bc32cd4a02affa98c53f892e5d34e1650d08f7
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990106"
---
# <a name="supporting-notifications"></a>Поддержка уведомлений

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>Реализация точки подключения интерфейсов для поставщика и потребителя  

Чтобы реализовать уведомлений, должен наследовать класс поставщика [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) и [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md).  
  
`IRowsetNotifyCP` реализует поставщик сайта для точки подключения интерфейса [IRowsetNotify](/previous-versions/windows/desktop/ms712959). `IRowsetNotifyCP` реализует широковещательных функции для в точке подключения `IID_IRowsetNotify` об изменениях содержимого набора строк.  
  
Обратите внимание, что необходимо также реализовать и зарегистрировать `IRowsetNotify` на объекте-получателе (приемник) с помощью [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) потребитель может обрабатывать уведомления. Сведения о реализации интерфейса точки подключения на потребителя, см. в разделе [получение уведомлений](../../data/oledb/receiving-notifications.md).  
  
Кроме того класс должен также содержать картой, которая определяет запись точки подключения, следующим образом:  
  
```cpp  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>Добавление IRowsetNotify  

Чтобы добавить `IRowsetNotify`, необходимо добавить `IConnectionPointContainerImpl<rowset-name>` и `IRowsetNotifyCP<rowset-name>` в цепочку наследования.  
  
Например, вот цепочку наследования для `RUpdateRowset` в [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV):  
  
> [!NOTE]
> Пример кода может отличаться от приведенного в примере; пример кода следует рассматривать в качестве более новой версии.  
  
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
  
```cpp  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
Эти макросы запретить всем пользователям вызывать `QueryInterface` для точки подключения контейнера (основы `IRowsetNotify`) найти запрошенный интерфейс для поставщика. Пример демонстрирует использование точки подключения, см. в образце ATL POLYGON и руководства.  
  
### <a name="setting-connection-point-map-entries"></a>Установка компонентов сопоставления точек подключения  

Необходимо также добавить сопоставление точки подключения. Он должен выглядеть примерно следующим образом:  
  
```cpp  
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