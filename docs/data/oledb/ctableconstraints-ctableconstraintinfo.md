---
title: CTableConstraints, CTableConstraintInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szTableSchema
- CONSTRAINT_TYPE
- m_szCatalog
- CTableConstraints
- m_bInitiallyDeferred
- CONSTRAINT_NAME
- m_szTableCatalog
- m_szType
- m_szSchema
- INITIALLY_DEFERRED
- CTableConstraintInfo
- m_szTableName
- m_bIsDeferrable
- m_szName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
- IS_DEFERRABLE
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- CTableConstraints typedef class
- IS_DEFERRABLE
- m_szSchema
- m_bInitiallyDeferred
- CONSTRAINT_CATALOG
- m_szTableSchema
- TABLE_CATALOG
- m_szType
- m_szCatalog
- TABLE_NAME
- CONSTRAINT_NAME
- CONSTRAINT_TYPE
- CONSTRAINT_SCHEMA
- TABLE_SCHEMA
- m_szName
- m_szTableCatalog
- m_szDescription
- CTableConstraintInfo parameter class
- m_szTableName
- INITIALLY_DEFERRED
- m_bIsDeferrable
ms.assetid: aaa07ade-0bfa-41d0-94df-8342152a4ff0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f83f6d9b7f8c79be9ec02d19698f002e38534a6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ctableconstraints-ctableconstraintinfo"></a>CTableConstraints, CTableConstraintInfo
Вызовите typedef-класс **CTableConstraints** реализации класса своего параметра **CTableConstraintInfo**.  
  
## <a name="remarks"></a>Примечания  
 В разделе [классы набора строк схемы и классы Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) Дополнительные сведения об использовании классов typedef.  
  
 Этот класс определяет ограничения таблицы, определенные в каталоге, которые принадлежат данному пользователю.  
  
 В следующей таблице перечислены данные-члены класса и их соответствующие OLE DB столбцы. В разделе [строк TABLE_CONSTRAINTS](https://msdn.microsoft.com/en-us/library/ms715921.aspx) в *Справочник программиста OLE DB* Дополнительные сведения о схеме и столбцы.  
  
|Члены данных|Столбцы OLE DB|  
|------------------|--------------------|  
|m_szCatalog|CONSTRAINT_CATALOG|  
|m_szSchema|CONSTRAINT_SCHEMA|  
|m_szName|CONSTRAINT_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szType|CONSTRAINT_TYPE|  
|m_bIsDeferrable|IS_DEFERRABLE|  
|m_bInitiallyDeferred|INITIALLY_DEFERRED|  
|m_szDescription|DESCRIPTION|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRestrictions](../../data/oledb/crestrictions-class.md)