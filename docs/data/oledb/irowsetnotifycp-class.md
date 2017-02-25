---
title: "Класс IRowsetNotifyCP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetNotifyCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetNotifyCP - класс"
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс IRowsetNotifyCP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует сайт поставщика для интерфейса [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) точки подключения.  
  
## Синтаксис  
  
```  
template <  
   class T,   
   class ReentrantEventSync = CComSharedMutex   
>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray  
   >,  
   public ReentrantEventSync  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IRowsetNotifyCP`.  
  
 `ReentrantEventSync`  
 Класс мьютексов, поддерживающий reentrancy \(значение по умолчанию **CComSharedMutex**\).  Мьютекс объект синхронизации, позволяющий одним потоком — монопольный доступ к ресурсу.  
  
 `piid`  
 Указатель на идентификатор интерфейса \(**IID\***\) точки подключения для интерфейса **IRowsetNotify** .  Значение по умолчанию **&\_\_uuidof\(IRowsetNotify\)**.  
  
 `DynamicUnkArray`  
 Массив типа [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md), который динамически выбранный массив указателей **IUnknown** к интерфейсам приемника клиента.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[Fire\_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|Уведомляет объект\-получателя изменения значения столбца.|  
|[Fire\_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|Уведомляет объект\-получателя изменений, влияющих на строки.|  
|[Fire\_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|Уведомляет объект\-получателя изменений, влияющих на весь набор строк.|  
  
## Заметки  
 `IRowsetNotifyCP` реализует широковещательные функции для уведомления пользователей в точке подключения **IID\_IRowsetNotify** об изменениях содержимого набора строк.  
  
 Обратите внимание, что необходимо также реализовать и регистрация `IRowsetNotify` на также известном объекте\-получателе \(как «приемник»\) с помощью [IRowsetNotifyImpl](../Topic/IRowsetNotifyImpl%20Class.md), чтобы объект\-получатель смог обрабатывать уведомления.  В разделе [Получение уведомлений](../../data/oledb/receiving-notifications.md) о реализации интерфейса точки подключения на объекте\-получателе.  
  
 Дополнительные сведения о реализации уведомлений см. в разделе «поддержка уведомлений» раздела [Создание обновляемого поставщика](../../data/oledb/creating-an-updatable-provider.md).  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Notifications \(COM\)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [Overview of Notifications \(OLE DB\)](https://msdn.microsoft.com/en-us/library/ms725406.aspx)   
 [BEGIN\_CONNECTION\_POINT\_MAP](../Topic/BEGIN_CONNECTION_POINT_MAP.md)   
 [END\_CONNECTION\_POINT\_MAP](../Topic/END_CONNECTION_POINT_MAP.md)   
 [CONNECTION\_POINT\_ENTRY](../Topic/CONNECTION_POINT_ENTRY.md)   
 [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)