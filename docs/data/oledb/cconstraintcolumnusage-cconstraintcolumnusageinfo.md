---
title: "CConstraintColumnUsage, CConstraintColumnUsageInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_szTableSchema
- m_szConstraintCatalog
- CConstraintColumnUsage
- m_nColumnPropID
- COLUMN_GUID
- CONSTRAINT_NAME
- m_szColumnName
- m_szTableCatalog
- m_szConstraintSchema
- COLUMN_PROPID
- m_guidColumn
- CONSTRAINT_COLUMN_USAGE
- m_szTableName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
- CConstraintColumnUsageInfo
- m_szConstraintName
dev_langs: C++
helpviewer_keywords:
- COLUMN_PROPID
- m_szConstraintCatalog
- CONSTRAINT_COLUMN_USAGE
- CONSTRAINT_CATALOG
- CConstraintColumnUsageInfo parameter class
- m_szTableSchema
- TABLE_CATALOG
- TABLE_NAME
- CONSTRAINT_NAME
- CConstraintColumnUsage typedef class
- m_nColumnPropID
- CONSTRAINT_SCHEMA
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szTableCatalog
- m_szConstraintName
- m_szTableName
- m_szConstraintSchema
- COLUMN_GUID
- m_guidColumn
ms.assetid: 7d4d94e8-2025-4fcc-a176-c9b231eca77b
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d73239fbd3cab69d722f9d3c9546295685a6bd81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cconstraintcolumnusage-cconstraintcolumnusageinfo"></a>CConstraintColumnUsage, CConstraintColumnUsageInfo
Вызовите typedef-класс **CConstraintColumnUsage** реализации класса своего параметра **CConstraintColumnUsageInfo**.  
  
## <a name="remarks"></a>Примечания  
 В разделе [классы набора строк схемы и классы Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) Дополнительные сведения об использовании классов typedef.  
  
 Этот класс определяет столбцы, используемые ссылочные ограничения, ограничения unique, ограничения check и утверждения, определенные в каталоге и принадлежащие данному пользователю.  
  
 В следующей таблице перечислены данные-члены класса и их соответствующие OLE DB столбцы. В разделе [строк CONSTRAINT_COLUMN_USAGE](https://msdn.microsoft.com/en-us/library/ms724522.aspx) в *Справочник программиста OLE DB* Дополнительные сведения о схеме и столбцы.  
  
|Члены данных|Столбцы OLE DB|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
|m_szConstraintCatalog|CONSTRAINT_CATALOG|  
|m_szConstraintSchema|CONSTRAINT_SCHEMA|  
|m_szConstraintName|CONSTRAINT_NAME|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRestrictions](../../data/oledb/crestrictions-class.md)