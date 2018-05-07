---
title: SCHEMA_ENTRY | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 665b337861959b28670a0b2e57649814853a7384
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="schemaentry"></a>SCHEMA_ENTRY
Связывает GUID с классом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      SCHEMA_ENTRY(guid,  
   rowsetClass);   
```  
  
#### <a name="parameters"></a>Параметры  
 `guid`  
 GUID набора строк схемы. В разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *Справочник программиста OLE DB* список наборов строк схемы и их идентификаторы GUID.  
  
 *rowsetClass*  
 Класс, который будет создан для представления набора строк схемы.  
  
## <a name="remarks"></a>Примечания  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) можно затем запрос карты список идентификаторов GUID, или его можно создать набор строк, если ему присваивается идентификатор GUID. Набор строк схемы `IDBSchemaRowsetImpl` создает аналогична стандартной `CRowsetImpl`-производного класса, за исключением того, он должен предоставлять **Execute** метод, который имеет следующую сигнатуру:  
  
```  
HRESULT Execute (LONG* pcRowsAffected,  
    ULONG cRestrictions,  
    const VARIANT* rgRestrictions);  
```  
  
 Это **Execute** функция заполняет данными набора строк. Создает мастер проектов ATL, как описано в [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *Справочник программиста OLE DB*, три начальный наборов строк схемы в проекте для каждого из трех обязательной схемы OLE DB:  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA_COLUMNS**  
  
-   **DBSCHEMA_PROVIDER_TYPES**  
  
 Мастер также добавляет три соответствующие записи в карте схемы. В разделе [Создание поставщика OLE DB шаблона](../../data/oledb/creating-an-ole-db-provider.md) Дополнительные сведения об использовании мастера для создания поставщика.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)