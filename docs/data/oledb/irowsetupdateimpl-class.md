---
title: Класс IRowsetUpdateImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
- SetData
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
- ATL.IRowsetUpdateImpl.GetOriginalData
- IRowsetUpdateImpl.GetOriginalData
- GetOriginalData
- ATL::IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetPendingRows
- GetPendingRows
- IRowsetUpdateImpl.GetPendingRows
- ATL::IRowsetUpdateImpl::GetPendingRows
- ATL.IRowsetUpdateImpl.GetPendingRows
- ATL.IRowsetUpdateImpl.GetRowStatus
- IRowsetUpdateImpl::GetRowStatus
- IRowsetUpdateImpl.GetRowStatus
- ATL::IRowsetUpdateImpl::GetRowStatus
- GetRowStatus
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
- SetData method
- GetOriginalData method
- GetPendingRows method
- GetRowStatus method
- Undo method
- Update method
- IsUpdateAllowed method
- m_mapCachedData
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: afbf8b42b4d518412c1004d78c5c718e54078c1c
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340785"
---
# <a name="irowsetupdateimpl-class"></a>Класс IRowsetUpdateImpl
Реализация шаблонов OLE DB [IRowsetUpdate](https://msdn.microsoft.com/library/ms714401.aspx) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  

class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass>  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Класс, производный от `IRowsetUpdateImpl`.  
  
 *Хранилища*  
 Записи пользователя.  
  
 *UpdateArray*  
 Массив, содержащий кэшированные данные для обновления набора строк.  
  
 *RowClass*  
 Единица хранения для `HROW`.  
  
 *MapClass*  
 Единица хранения для всех дескрипторов строк, удерживаемые поставщика.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используется с IRowsetChange)  
  
|||  
|-|-|  
|[SetData](#setdata)|Задает значения данных в один или несколько столбцов.|  
  
### <a name="interface-methods-used-with-irowsetupdate"></a>Методы интерфейса (используется с IRowsetUpdate)  
  
|||  
|-|-|  
|[GetOriginalData](#getoriginaldata)|Возвращает данные, наиболее недавно передаваемые или полученные из источника данных, игнорируя ожидающие изменения.|  
|[GetPendingRows](#getpendingrows)|Возвращает список строк с предполагаемыми изменениями.|  
|[GetRowStatus](#getrowstatus)|Возвращает состояние указанной строки.|  
|[Отменить](#undo)|Отменяет все изменения в строку с момента последнего получения или обновления.|  
|[Обновление](#update)|Передает любые изменения, внесенные в строку с момента последнего получения или обновления.|  
  
### <a name="implementation-methods-callback"></a>Методы реализации (обратный вызов)  
  
|||  
|-|-|  
|[IsUpdateAllowed](#isupdateallowed)|Используются для проверки безопасности, целостности, и т. д перед предоставлением обновлений.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_mapCachedData](#mapcacheddata)|Содержит исходные данные для отложенной операции.|  
  
## <a name="remarks"></a>Примечания  
 Вам необходимо сначала прочесть и понять в документации по [IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx), так как все там описано также применяется здесь. Также следует ознакомиться с главе 6 *Справочник программиста OLE DB по* о настройке данных.  
  
 `IRowsetUpdateImpl` реализует OLE DB `IRowsetUpdate` интерфейс, который позволяет потребителям приостановить передачу изменений, внесенных с `IRowsetChange` для источника данных и отменить изменения перед передачей.  
  
> [!IMPORTANT]
>  Настоятельно рекомендуется ознакомиться со следующей документацией, прежде ЧЕМ пытаться реализации поставщика:  
  
-   [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Глава 6 *справочнике программиста OLE DB*  
  
-   Также см. в разделе как `RUpdateRowset` класс используется в разделе Создание  

## <a name="setdata"></a> IRowsetUpdateImpl::SetData
Задает значения данных в один или несколько столбцов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowsetChange::SetData](https://msdn.microsoft.com/library/ms721232.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="remarks"></a>Примечания  
 Этот метод переопределяет [IRowsetChangeImpl::SetData](../../data/oledb/irowsetchangeimpl-setdata.md) метод но включает кэширование исходных данных, чтобы разрешить немедленно обновляемых подписок или отложенной обработки операции.

## <a name="getoriginaldata"></a> IRowsetUpdateImpl::GetOriginalData
Возвращает данные, наиболее недавно передаваемые или полученные из источника данных, игнорируя ожидающие изменения.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (GetOriginalData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pData);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/library/ms709947.aspx) в *справочнике программиста OLE DB*.   

## <a name="getpendingrows"></a> IRowsetUpdateImpl::GetPendingRows
Возвращает список строк с предполагаемыми изменениями.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (GetPendingRows )(HCHAPTER /* hReserved */,  
   DBPENDINGSTATUS dwRowStatus,  
   DBCOUNTITEM* pcPendingRows,  
   HROW** prgPendingRows,  
   DBPENDINGSTATUS** prgPendingStatus);  
```  
  
#### <a name="parameters"></a>Параметры  
 *hReserved*  
 [in] Соответствует *hChapter* параметр в [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx).  
  
 Другие параметры, см. в разделе [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx) в *Справочник программиста OLE DB по*.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx) в *Справочник программиста OLE DB по*.  

## <a name="getrowstatus"></a> IRowsetUpdateImpl::GetRowStatus
Возвращает состояние указанной строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBPENDINGSTATUS rgPendingStatus[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 *hReserved*  
 [in] Соответствует *hChapter* параметр в [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/library/ms724377.aspx).  
  
 Другие параметры, см. в разделе [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/library/ms724377.aspx) в *Справочник программиста OLE DB по*.  

## <a name="undo"></a> IRowsetUpdateImpl::Undo
Отменяет все изменения в строку с момента последнего получения или обновления.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (Undo )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>Параметры  
 *hReserved*  
 [in] Соответствует *hChapter* параметр в [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx).  
  
 *pcRowsUndone*  
 [out] Соответствует *pcRows* параметр в [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx).  
  
 *prgRowsUndone*  
 [in] Соответствует *prgRows* параметр в [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx).  
  
 Другие параметры, см. в разделе [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx) в *Справочник программиста OLE DB по*. 

## <a name="update"></a> IRowsetUpdateImpl::Update
Передает любые изменения, внесенные в строку с момента последнего получения или обновления.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (Update )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>Параметры  
 *hReserved*  
 [in] Соответствует *hChapter* параметр в [IRowsetUpdate::Update](https://msdn.microsoft.com/library/ms719709.aspx).  
  
 Другие параметры, см. в разделе [IRowsetUpdate::Update](https://msdn.microsoft.com/library/ms719709.aspx) в *Справочник программиста OLE DB по*.  
  
### <a name="remarks"></a>Примечания  
 Изменения передаются путем вызова [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md). Потребитель должен вызвать метод [CRowset::Update](../../data/oledb/crowset-update.md) изменения вступили в силу. Задайте *prgRowstatus* соответствующее значение, описанных в [состояния строк](https://msdn.microsoft.com/library/ms722752.aspx) в *Справочник программиста OLE DB по*. 
  
## <a name="isupdateallowed"></a> IRowsetUpdateImpl::IsUpdateAllowed
Переопределите этот метод для проверки безопасности, целостность и так далее до обновления.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,  
   HROW /* [in] */ /* hRowUpdate */,  
   DBROWSTATUS* /* [out] */ /* pRowStatus */);  
```  
  
#### <a name="parameters"></a>Параметры  
 *status*  
 [in] Состояние отложенных операций по строкам.  
  
 *hRowUpdate*  
 [in] Дескриптор строки, которые пользователю нужно обновить.  
  
 *pRowStatus*  
 [out] Состояние, возвращаемое для пользователя.  
  
### <a name="remarks"></a>Примечания  
 Если вы определили, что обновление должно быть разрешено, возвращает значение S_OK; в противном случае возвращает значение E_FAIL. Если разрешить обновления, необходимо также задать `DBROWSTATUS` в [IRowsetUpdateImpl::Update](../../data/oledb/irowsetupdateimpl-update.md) — соответствующую [состоянием строк](https://msdn.microsoft.com/library/ms722752.aspx).  

## <a name="mapcacheddata"></a> IRowsetUpdateImpl::m_mapCachedData
Карта, содержащая исходные данные для отложенной операции.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CAtlMap<   
   HROW hRow,    
   Storage* pData   
>   
m_mapCachedData;  
```  
  
#### <a name="parameters"></a>Параметры  
 *hRow*  
 Дескриптор строки данных.  
  
 *pData*  
 Указатель данных должен быть помещен в кэш. Данные имеют тип *хранения* (класс записей пользователя). См. в разделе *хранения* аргумент шаблона в [класс IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md).  

## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)