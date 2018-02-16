---
title: "SCHEMA_ENTRY | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4b1ddabb976cdf4897dbd414433f013a84825d01
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
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