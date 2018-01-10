---
title: "Класс IRowsetNotifyCP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IRowsetNotifyCP
dev_langs: C++
helpviewer_keywords: IRowsetNotifyCP class
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bae872c90a6df76e3efc1fce1aab6e77bc8fd313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetnotifycp-class"></a>Класс IRowsetNotifyCP
Реализует сайт поставщика для интерфейса точки подключения [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRowsetNotifyCP`.  
  
 `ReentrantEventSync`  
 Класс mutex, поддерживающего повторный вход (значение по умолчанию — **CComSharedMutex**). Мьютекс — объект синхронизации, позволяющий один поток взаимно исключают друг друга доступ к ресурсу.  
  
 `piid`  
 Указателя на идентификатор интерфейса (**IID\***) для **IRowsetNotify** интерфейса точки подключения. Значение по умолчанию — **& __uuidof(IRowsetNotify)**.  
  
 `DynamicUnkArray`  
 Массив объектов типа [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), которая представляет динамически выделяемый массив **IUnknown** указатели клиенту приемника интерфейсы.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Fire_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|Уведомляет объект-получатель изменение значения столбца.|  
|[Fire_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|Уведомляет объект-получатель из изменений, влияющих на строки.|  
|[Fire_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|Уведомляет объект-получатель из изменений, влияющих на весь набор строк.|  
  
## <a name="remarks"></a>Примечания  
 `IRowsetNotifyCP`реализует широковещательных функции для в точке подключения **IID_IRowsetNotify** изменений содержимого набора строк.  
  
 Обратите внимание, что необходимо также реализовать и зарегистрировать `IRowsetNotify` на объекте-получателе (также называется «приемник») с помощью [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) потребитель может обрабатывать уведомления. В разделе [получение уведомлений](../../data/oledb/receiving-notifications.md) о реализации точки подключения интерфейса на объекте-получателе.  
  
 Подробные сведения о реализации уведомлений. в разделе «Поддержка уведомления» в [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Уведомления (COM)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)   
 [END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)   
 [CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)   
 [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)