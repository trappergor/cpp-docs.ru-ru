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
ms.openlocfilehash: 67510ada7af557877f427d757200a48c0df95fe9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054120"
---
# <a name="irowsetupdateimpl-class"></a>Класс IRowsetUpdateImpl

Реализация шаблонов OLE DB [IRowsetUpdate](/previous-versions/windows/desktop/ms714401\(v=vs.85\)) интерфейс.  
  
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

*T*<br/>
Класс, производный от `IRowsetUpdateImpl`.  
  
*Хранилища*<br/>
Записи пользователя.  
  
*UpdateArray*<br/>
Массив, содержащий кэшированные данные для обновления набора строк.  
  
*RowClass*<br/>
Единица хранения для `HROW`.  
  
*MapClass*<br/>
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

Вам необходимо сначала прочесть и понять в документации по [IRowsetChange](/previous-versions/windows/desktop/ms715790\(v=vs.85\)), так как все там описано также применяется здесь. Также следует ознакомиться с главе 6 *Справочник программиста OLE DB по* о настройке данных.  
  
`IRowsetUpdateImpl` реализует OLE DB `IRowsetUpdate` интерфейс, который позволяет потребителям приостановить передачу изменений, внесенных с `IRowsetChange` для источника данных и отменить изменения перед передачей.  
  
> [!IMPORTANT]
>  Настоятельно рекомендуется ознакомиться со следующей документацией, прежде ЧЕМ пытаться реализации поставщика:  
  
- [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)  
  
- Глава 6 *справочнике программиста OLE DB*  
  
- Также см. в разделе как `RUpdateRowset` класс используется в [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) образца  

## <a name="setdata"></a> IRowsetUpdateImpl::SetData

Задает значения данных в один или несколько столбцов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>Параметры  

См. в разделе [IRowsetChange::SetData](/previous-versions/windows/desktop/ms721232\(v=vs.85\)) в *справочнике программиста OLE DB*.  
  
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

См. в разделе [IRowsetUpdate::GetOriginalData](/previous-versions/windows/desktop/ms709947\(v=vs.85\)) в *справочнике программиста OLE DB*.   

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

*hReserved*<br/>
[in] Соответствует *hChapter* параметр в [IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626\(v=vs.85\)).  
  
Другие параметры, см. в разделе [IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626\(v=vs.85\)) в *Справочник программиста OLE DB по*.  
  
### <a name="remarks"></a>Примечания  

Дополнительные сведения см. в разделе [IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626\(v=vs.85\)) в *Справочник программиста OLE DB по*.  

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

*hReserved*<br/>
[in] Соответствует *hChapter* параметр в [IRowsetUpdate::GetRowStatus](/previous-versions/windows/desktop/ms724377\(v=vs.85\)).  
  
Другие параметры, см. в разделе [IRowsetUpdate::GetRowStatus](/previous-versions/windows/desktop/ms724377\(v=vs.85\)) в *Справочник программиста OLE DB по*.  

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

*hReserved*<br/>
[in] Соответствует *hChapter* параметр в [IRowsetUpdate::Undo](/previous-versions/windows/desktop/ms719655\(v=vs.85\)).  
  
*pcRowsUndone*<br/>
[out] Соответствует *pcRows* параметр в [IRowsetUpdate::Undo](/previous-versions/windows/desktop/ms719655\(v=vs.85\)).  
  
*prgRowsUndone*<br/>
[in] Соответствует *prgRows* параметр в [IRowsetUpdate::Undo](/previous-versions/windows/desktop/ms719655\(v=vs.85\)).  
  
Другие параметры, см. в разделе [IRowsetUpdate::Undo](/previous-versions/windows/desktop/ms719655\(v=vs.85\)) в *Справочник программиста OLE DB по*. 

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

*hReserved*<br/>
[in] Соответствует *hChapter* параметр в [IRowsetUpdate::Update](/previous-versions/windows/desktop/ms719709\(v=vs.85\)).  
  
Другие параметры, см. в разделе [IRowsetUpdate::Update](/previous-versions/windows/desktop/ms719709\(v=vs.85\)) в *Справочник программиста OLE DB по*.  
  
### <a name="remarks"></a>Примечания  

Изменения передаются путем вызова [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md). Потребитель должен вызвать метод [CRowset::Update](../../data/oledb/crowset-update.md) изменения вступили в силу. Задайте *prgRowstatus* соответствующее значение, описанных в [состояния строк](/previous-versions/windows/desktop/ms722752\(v=vs.85\)) в *Справочник программиста OLE DB по*. 
  
## <a name="isupdateallowed"></a> IRowsetUpdateImpl::IsUpdateAllowed

Переопределите этот метод для проверки безопасности, целостность и так далее до обновления.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,  
   HROW /* [in] */ /* hRowUpdate */,  
   DBROWSTATUS* /* [out] */ /* pRowStatus */);  
```  
  
#### <a name="parameters"></a>Параметры  

*status*<br/>
[in] Состояние отложенных операций по строкам.  
  
*hRowUpdate*<br/>
[in] Дескриптор строки, которые пользователю нужно обновить.  
  
*pRowStatus*<br/>
[out] Состояние, возвращаемое для пользователя.  
  
### <a name="remarks"></a>Примечания  

Если вы определили, что обновление должно быть разрешено, возвращает значение S_OK; в противном случае возвращает значение E_FAIL. Если разрешить обновления, необходимо также задать `DBROWSTATUS` в [IRowsetUpdateImpl::Update](../../data/oledb/irowsetupdateimpl-update.md) — соответствующую [состоянием строк](/previous-versions/windows/desktop/ms722752\(v=vs.85\)).  

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

*hRow*<br/>
Дескриптор строки данных.  
  
*pData*<br/>
Указатель данных должен быть помещен в кэш. Данные имеют тип *хранения* (класс записей пользователя). См. в разделе *хранения* аргумент шаблона в [класс IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md).  

## <a name="see-also"></a>См. также  

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)