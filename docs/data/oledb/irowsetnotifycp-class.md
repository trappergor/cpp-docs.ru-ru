---
title: Класс IRowsetNotifyCP | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetNotifyCP
- Fire_OnFieldChange
- ATL::IRowsetNotifyCP::Fire_OnFieldChange
- ATL.IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP::Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
- Fire_OnRowsetChange
- IRowsetNotifyCP::Fire_OnRowsetChange
- IRowsetNotifyCP.Fire_OnRowsetChange
- ATL::IRowsetNotifyCP::Fire_OnRowsetChange
- ATL.IRowsetNotifyCP.Fire_OnRowsetChange
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyCP class
- Fire_OnFieldChange method
- Fire_OnRowChange method
- Fire_OnRowsetChange method
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 207128da3e46da492ebc812b68d9ef09847045e5
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322128"
---
# <a name="irowsetnotifycp-class"></a>Класс IRowsetNotifyCP
Реализует поставщик сайта для точки подключения интерфейса [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx).  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class ReentrantEventSync = CComSharedMutex>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray>,  
   public ReentrantEventSync  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Класс, производный от `IRowsetNotifyCP`.  
  
 *ReentrantEventSync*  
 Класс mutex, поддерживающий повторного входа (по умолчанию используется `CComSharedMutex`). Мьютекс — объект синхронизации, позволяющий один поток взаимно исключают друг друга доступ к ресурсу.  
  
 *piid*  
 Указатель на интерфейс идентификатор (`IID*`) для `IRowsetNotify` интерфейса точки подключения. Значение по умолчанию — `&__uuidof(IRowsetNotify)`.  
  
 *DynamicUnkArray*  
 Массив объектов типа [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), которая представляет динамический массив `IUnknown` указатели на клиенте приемник интерфейсов. 

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h   
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Fire_OnFieldChange](#onfieldchange)|Уведомляет объект-получатель изменения значения столбца.|  
|[Fire_OnRowChange](#onrowchange)|Уведомляет объект-получатель изменений, влияющих на строки.|  
|[Fire_OnRowsetChange](#onrowsetchange)|Уведомляет объект-получатель изменений, влияющих на весь набор строк.|  
  
## <a name="remarks"></a>Примечания  
 `IRowsetNotifyCP` реализует широковещательных функции для в точке подключения `IID_IRowsetNotify` об изменениях содержимого набора строк.  
  
 Обратите внимание, что необходимо также реализовать и зарегистрировать `IRowsetNotify` на объекте-получателе (также называется «приемник») с помощью [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) потребитель может обрабатывать уведомления. См. в разделе [получение уведомлений](../../data/oledb/receiving-notifications.md) о реализации интерфейса точки подключения на объекте-получателе.  
  
 Подробные сведения о реализации уведомлений см. в разделе «Поддержка уведомления» в [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md).  

## <a name="onfieldchange"></a> IRowsetNotifyCP::Fire_OnFieldChange
Осуществляет широковещательную передачу [OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) событие для уведомления пользователей об изменении значения столбца.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Fire_OnFieldChange(IRowset* pRowset,  
   HROW hRow,  
   DBORDINAL cColumns,  
   DBORDINAL* rgColumns,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) в *справочнике программиста OLE DB*. 

## <a name="onrowchange"></a> IRowsetNotifyCP::Fire_OnRowChange
Осуществляет широковещательную передачу [OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx) событий все прослушиватели в точке подключения `IID_IRowsetNotify` для уведомления потребителей изменений, влияющих на строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Fire_OnRowChange(IRowset* pRowset,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx) в *справочнике программиста OLE DB*.  

## <a name="onrowsetchange"></a> IRowsetNotifyCP::Fire_OnRowsetChange
Осуществляет широковещательную передачу [OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) событий все прослушиватели в точке подключения `IID_IRowsetNotify` для уведомления потребителей изменений, влияющих на весь набор строк.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) в *справочнике программиста OLE DB*.
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Уведомления (COM)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)   
 [END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)   
 [CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)   
 [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)
