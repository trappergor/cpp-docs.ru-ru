---
title: Класс IRowsetChangeImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 11435cd1372147efb14aed78448d889fd60dc5a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetchangeimpl-class"></a>Класс IRowsetChangeImpl
Реализация шаблонов OLE DB [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) интерфейса в спецификации OLE DB.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRowsetChangeImpl`.  
  
 `Storage`  
 Записи пользователя.  
  
 `BaseInterface`  
 Базовый класс для интерфейса, такие как `IRowsetChange`.  
  
 `RowClass`  
 Устройство хранения для дескриптора строки.  
  
 `MapClass`  
 Устройство хранения для все дескрипторы строк, удерживаемые поставщика.  
  
## <a name="members"></a>Члены  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Методы интерфейса (используется с IRowsetChange)  
  
|||  
|-|-|  
|[DeleteRows](../../data/oledb/irowsetchangeimpl-deleterows.md)|Удаляет строки из набора строк.|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|Вставляет строку в наборе строк.|  
|[SetData](../../data/oledb/irowsetchangeimpl-setdata.md)|Задает значения данных в одном или нескольких столбцах.|  
  
### <a name="implementation-method-callback"></a>Реализация метода (обратный вызов)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|Overidden поставщиком для фиксации данных к своему хранилищу.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс не отвечает за операции записи непосредственно в хранилище данных. «Immediate» означает, когда конечный пользователь (лицом, использующим потребитель) делает все изменения, эти изменения немедленно переносятся данные хранения (и не может быть отменено).  
  
 `IRowsetChangeImpl` реализует OLE DB `IRowsetChange` интерфейс, позволяющий обновления значений столбцов в существующих строках, удаление строк и вставки новых строк.  
  
 Реализация шаблонов OLE DB поддерживает все базовые методы (`SetData`, `InsertRow`, и `DeleteRows`).  
  
> [!IMPORTANT]
>  Настоятельно рекомендуется ознакомиться со следующей документацией, прежде ЧЕМ пытаться реализации поставщика:  
  
-   [Создание поставщика с возможностью записи](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Глава 6 *справочника программиста OLE DB*  
  
-   См. также как `RUpdateRowset` класс используется в разделе Создание  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)