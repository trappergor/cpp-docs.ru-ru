---
title: CCheckConstraints, CCheckConstraintInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCheckConstraintInfo
- CHECK_CONSTRAINTS
- m_szCatalog
- CCheckConstraints
- CONSTRAINT_NAME
- m_szSchema
- CHECK_CLAUSE
- m_szCheckClause
- m_szName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- m_szSchema
- CONSTRAINT_CATALOG
- m_szCatalog
- CONSTRAINT_NAME
- CONSTRAINT_SCHEMA
- CCheckConstraints typedef class
- CHECK_CLAUSE
- m_szName
- m_szDescription
- CCheckConstraintInfo parameter class
- m_szCheckClause
- CHECK_CONSTRAINTS
ms.assetid: e53e79a5-01e5-42b7-aa8c-164aec94b011
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a2f167212458266b44f93315cd3185010461c78d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093874"
---
# <a name="ccheckconstraints-ccheckconstraintinfo"></a>CCheckConstraints, CCheckConstraintInfo
Вызовите typedef-класс **CCheckConstraints** реализации класса своего параметра **CCheckConstraintInfo**.  
  
## <a name="remarks"></a>Примечания  
 В разделе [классы набора строк схемы и классы Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) Дополнительные сведения об использовании классов typedef.  
  
 Этот класс определяет ограничения check, определенные в каталоге, которые принадлежат данному пользователю. Ограничение check задает значения данных или форматы, допустимые для одного или нескольких столбцов в таблице.  
  
 В следующей таблице перечислены данные-члены класса и их соответствующие OLE DB столбцы. В разделе [строк CHECK_CONSTRAINTS](https://msdn.microsoft.com/en-us/library/ms712845.aspx) в *Справочник программиста OLE DB* Дополнительные сведения о схеме и столбцы.  
  
|Члены данных|Столбцы OLE DB|  
|------------------|--------------------|  
|m_szCatalog|CONSTRAINT_CATALOG|  
|m_szSchema|CONSTRAINT_SCHEMA|  
|m_szName|CONSTRAINT_NAME|  
|m_szCheckClause|CHECK_CLAUSE|  
|m_szDescription|DESCRIPTION|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRestrictions](../../data/oledb/crestrictions-class.md)