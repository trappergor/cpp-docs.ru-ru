---
title: Класс IDBSchemaRowsetImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBSchemaRowsetImpl class
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dc9da29bcd49b227596325913d521347b6b0ca0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl - класс
Предоставляет реализацию для наборов строк схемы.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### <a name="parameters"></a>Параметры  
 `SessionClass`  
 Класс, по которому наследуется `IDBSchemaRowsetImpl` . Как правило, этот класс будет классом сеанса пользователя.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|Проверяет допустимость ограничений относительно набора строк схемы.|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|Реализует функцию создателя COM-объекта для объекта, указанного параметром шаблона.|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|Указывает, какие ограничения поддерживаются в определенном наборе строк схемы.|  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|Возвращает набор строк схемы.|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|Возвращает список наборов строк схемы, доступных для [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).|  
  
## <a name="remarks"></a>Примечания  
 Этот класс реализует интерфейс [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) и шаблонизируемую функцию создателя [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB использует наборы строк схемы для возврата сведений о данных в поставщике. Такие данные часто называют метаданными. По умолчанию поставщик всегда должен поддерживать `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**и **DBSCHEMA_PROVIDER_TYPES**, как описано в разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *справочнике программиста OLE DB*. Наборы строк схемы назначаются в карте схемы. Сведения о карте записей схемы см. в разделе [SCHEMA_ENTRY](../../data/oledb/schema-entry.md).  
  
 Мастер поставщиков OLE DB в мастере объектов ATL автоматически создает код для наборов строк схемы в проекте. (По умолчанию мастер поддерживает упомянутые выше обязательные наборы строк схемы.) При создании потребителя мастер объектов ATL использует наборы строк схемы для привязки правильных данных к поставщику. Если наборы строк схемы не реализованы для представления правильных метаданных, мастер не выполнит привязку правильных данных.  
  
 Сведения о поддержке наборов строк схемы в поставщике см. в разделе [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md).  
  
 Дополнительные сведения о наборах строк схемы см. в разделе [Наборы строк схемы](https://msdn.microsoft.com/en-us/library/ms712921.aspx) в *справочнике программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IDBSchemaRowsetImpl члены](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Классы схемы Rowset и Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md)