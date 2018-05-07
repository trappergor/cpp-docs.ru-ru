---
title: BEGIN_SCHEMA_MAP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_SCHEMA_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_SCHEMA_MAP macro
ms.assetid: 4e751023-35bc-4efd-9018-5448dd1ad751
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 36839996a95257d39ded740c431f9db6ed2b372d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="beginschemamap"></a>BEGIN_SCHEMA_MAP
Обозначает начало карте схемы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      BEGIN_SCHEMA_MAP(SchemaClass);  
```  
  
#### <a name="parameters"></a>Параметры  
 *SchemaClass*  
 Класс, который содержит СХЕМУ. Как правило, это будет классом сеанса.  
  
## <a name="remarks"></a>Примечания  
 В разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в Windows SDK, Дополнительные сведения о наборах строк схемы.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)   
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)