---
title: Класс IRowsetChangeImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
- ATL.IRowsetChangeImpl.DeleteRows
- ATL::IRowsetChangeImpl::DeleteRows
- IRowsetChangeImpl.DeleteRows
- DeleteRows
- IRowsetChangeImpl::DeleteRows
- ATL.IRowsetChangeImpl.InsertRow
- InsertRow
- IRowsetChangeImpl.InsertRow
- ATL::IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::InsertRow
- SetData
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
- DeleteRows method
- InsertRow method
- SetData method
- FlushData method
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 70c9d1b5bc4952b0a56d8e136bc7b817a1e1b1c9
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269774"
---
# <a name="irowsetchangeimpl-class"></a>Класс IRowsetChangeImpl
Реализация шаблонов OLE DB [IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx) интерфейс в спецификации OLE DB.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Класс, производный от `IRowsetChangeImpl`.  
  
 *Хранилища*  
 Записи пользователя.  
  
 *BaseInterface*  
 Базовый класс для интерфейса, такие как `IRowsetChange`.  
  
 *RowClass*  
 Единица хранения для дескриптора строки.  
  
 *MapClass*  
 Единица хранения для всех дескрипторов строк, удерживаемые поставщика.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используется с IRowsetChange)  
  
|||  
|-|-|  
|[DeleteRows](#deleterows)|Удаляет строки из набора строк.|  
|[InsertRow](#insertrow)|Вставляет строку в наборе строк.|  
|[SetData](#setdata)|Задает значения данных в один или несколько столбцов.|  
  
### <a name="implementation-method-callback"></a>Реализация метода (обратный вызов)  
  
|||  
|-|-|  
|[FlushData](#flushdata)|Переопределенная поставщиком для фиксации данных в хранилище.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс отвечает за операции записи немедленно в хранилище данных. «Немедленно» означает, что когда конечный пользователь (пользователь, с помощью потребителя) делает все изменения, эти изменения немедленно переносятся данные хранения (и не может быть отменена).  
  
 `IRowsetChangeImpl` реализует OLE DB `IRowsetChange` интерфейс, позволяющий обновлять значения столбцов в существующих строках, удаление строк и вставки новых строк.  
  
 Реализация шаблонов OLE DB поддерживает все базовые методы (`SetData`, `InsertRow`, и `DeleteRows`).  
  
> [!IMPORTANT]
>  Настоятельно рекомендуется ознакомиться со следующей документацией, прежде ЧЕМ пытаться реализации поставщика:  
  
-   [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Глава 6 *справочнике программиста OLE DB*  
  
-   Также см. в разделе как `RUpdateRowset` класс используется в разделе Создание  
  
## <a name="deleterows"></a> IRowsetChangeImpl::DeleteRows
Удаляет строки из набора строк.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBROWSTATUS rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowsetChange::DeleteRows](https://msdn.microsoft.com/library/ms724362.aspx) в *справочнике программиста OLE DB*. 

## <a name="insertrow"></a> IRowsetChangeImpl::InsertRow
Создает и инициализирует новую строку в наборе строк.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,  
   HACCESSOR hAccessor,  
   void* pData,  
   HROW* phRow);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowsetChange::InsertRow](https://msdn.microsoft.com/library/ms716921.aspx) в *справочнике программиста OLE DB*. 

## <a name="setdata"></a> IRowsetChangeImpl::SetData
Задает значения данных в один или несколько столбцов.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowsetChange::SetData](https://msdn.microsoft.com/library/ms721232.aspx) в *справочнике программиста OLE DB*. 

## <a name="flushdata"></a> IRowsetChangeImpl::FlushData
Переопределенная поставщиком для фиксации данных в хранилище.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT FlushData(HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush);  
```  
  
#### <a name="parameters"></a>Параметры  
 *hRowToFlush*  
 [in] Дескриптор строки данных. Тип этой строки будет определяться *RowClass* аргумент шаблона `IRowsetImpl` класс (`CSimpleRow` по умолчанию).  
  
 *hAccessorToFlush*  
 [in] Дескриптор метода доступа, который содержит сведения о привязке и сведения о типе в его `PROVIDER_MAP` (см. в разделе [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
