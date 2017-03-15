---
title: "Поддержка уведомлений | Microsoft Docs"
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
  - "уведомления [C++], потребители OLE DB"
  - "потребители OLE DB, уведомления"
  - "шаблоны поставщика OLE DB, уведомления"
  - "поставщики OLE DB, уведомления"
  - "наборы строк, уведомления о событиях"
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Поддержка уведомлений
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Реализация точки подключения интерфейсов для поставщика и объекта\-получателя  
 Для реализации уведомлений класс поставщика должен наследоваться от [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) и [IConnectionPointContainer](../Topic/IConnectionPointContainerImpl%20Class.md).  
  
 `IRowsetNotifyCP` реализует сайт поставщика для интерфейса точки подключения [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  `IRowsetNotifyCP` реализует широковещательные функции для уведомления пользователей в точке подключения **IID\_IRowsetNotify** об изменениях содержимого набора строк.  
  
 Чтобы объект\-получатель смог обрабатывать уведомления, на объекте\-получателе \(также называемом приемник\) должна производится реализация и регистрация `IRowsetNotify` с помощью [IRowsetNotifyImpl](../Topic/IRowsetNotifyImpl%20Class.md).  Дополнительные сведения по реализации точки подключения интерфейса на объекте\-получателе см. в разделе [Получение уведомлений](../../data/oledb/receiving-notifications.md).  
  
 Кроме того, класс должен содержать сопоставление, определяющее точку ввода соединения, подобную указанной ниже.  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## Добавление IRowsetNotify  
 Чтобы добавить `IRowsetNotify`, необходимо добавить `IConnectionPointContainerImpl<rowset-name>` и `IRowsetNotifyCP<rowset-name>` к цепочке наследования.  
  
 Рассмотрим, например, цепочку наследования для `RUpdateRowset` в [UpdatePV](http://msdn.microsoft.com/ru-ru/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  Образец кода может отличаться от приведенного в примере; рассматривать образец кода следует как более современную версию.  
  
```  
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan> >, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll > >,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### Настройка компонентов сопоставления COM  
 К сопоставлению COM в наборе строк должны добавляться следующие элементы.  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 Использование этого макроса позволяет всем пользователям, сделавшим вызов `QueryInterface` для точки подключения контейнера \(основа `IRowsetNotify`\) находить нужный интерфейс у поставщика.  Примеры использования точек подключения см. в примере ATL POLYGON и в руководстве.  
  
### Настройка компонентов сопоставления точек подключения  
 Необходимо добавить сопоставление точки подключения.  Этот процесс выглядит приблизительно следующими образом.  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 Сопоставление точки подключения позволяет компоненту, осуществляющему поиск интерфейса `IRowsetNotify`, находить его у поставщика.  
  
### Задание свойств  
 К поставщику должны добавляться следующие свойства.  Добавлять свойства необходимо только исходя из поддерживаемого интерфейса.  
  
|Свойство|Добавить в случае поддержки|  
|--------------|---------------------------------|  
|**DBPROP\_IConnectionPointContainer**|Всегда|  
|**DBPROP\_NOTIFICATIONGRANULARITY**|Всегда|  
|**DBPROP\_NOTIFICATIONPHASES**|Всегда|  
|**DBPROP\_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWSETFETCHPOSITIONCHANGE**|Всегда|  
|**DBPROP\_NOTIFYROWFIRSTCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWSETRELEASE**|Всегда|  
|**DBPROP\_NOTIFYROWUNDOCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 Большая часть реализации уведомлений уже внедрена в шаблоны поставщика OLE DB.  Из\-за функции компилятора в Visual C\+\+ .NET, если `IRowsetNotifyCP` не добавлен к цепочке наследования, компилятор удаляет весь код из потока компиляции, таким образом, делая его меньше.  
  
## См. также  
 [Дополнительные способы использования поставщика](../Topic/Advanced%20Provider%20Techniques.md)