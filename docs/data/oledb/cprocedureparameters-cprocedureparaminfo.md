---
title: CProcedureParameters CProcedureParamInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szDefault
- CProcedureParameters
- m_bHasDefault
- CProcedureParamInfo
- IS_NULLABLE
- m_szCatalog
- ORDINAL_POSITION
- m_nOrdinalPosition
- NUMERIC_PRECISION
- m_nDataType
- m_szSchema
- CHARACTER_OCTET_LENGTH
- NUMERIC_SCALE
- m_szParameterName
- m_nMaxLength
- CHARACTER_MAXIMUM_LENGTH
- m_nPrecision
- m_szName
- DATA_TYPE
- m_nOctetLength
- m_nType
- m_bIsNullable
- m_nScale
dev_langs:
- C++
helpviewer_keywords:
- NUMERIC_PRECISION
- DATA_TYPE
- ORDINAL_POSITION
- m_nMaxLength
- DESCRIPTION class data member
- m_szParameterName
- m_szSchema
- m_nType
- m_bHasDefault
- CHARACTER_OCTET_LENGTH
- CProcedureParameters typedef class
- m_szCatalog
- m_nPrecision
- m_nOrdinalPosition
- NUMERIC_SCALE
- m_nOctetLength
- IS_NULLABLE
- m_szName
- m_bIsNullable
- CProcedureParamInfo parameter class
- m_szDescription
- m_szDefault
- m_nDataType
- m_nScale
- CHARACTER_MAXIMUM_LENGTH
ms.assetid: 61f8d55a-684a-47a3-b102-068cc3f52d84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0b314d6cabcae91ba3d6b6bfe04d5bcb40e9d0cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097553"
---
# <a name="cprocedureparameters-cprocedureparaminfo"></a>CProcedureParameters CProcedureParamInfo
Вызовите typedef-класс **CProcedureParameters** реализации класса своего параметра **CProcedureParamInfo**.  
  
## <a name="remarks"></a>Примечания  
 В разделе [классы набора строк схемы и классы Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) Дополнительные сведения об использовании классов typedef.  
  
 Этот класс возвращает сведения о параметрах и кодах возврата процедур.  
  
 В следующей таблице перечислены данные-члены класса и их соответствующие OLE DB столбцы. В разделе [строк PROCEDURE_PARAMETERS](https://msdn.microsoft.com/en-us/library/ms713623.aspx) в *Справочник программиста OLE DB* Дополнительные сведения о схеме и столбцы.  
  
|Члены данных|Столбцы OLE DB|  
|------------------|--------------------|  
|m_szCatalog|PROCEDURE_CATALOG|  
|m_szSchema|PROCEDURE_SCHEMA|  
|m_szName|PROCEDURE_NAME|  
|m_szParameterName|PARAMETER_NAME|  
|m_nOrdinalPosition|ORDINAL_POSITION|  
|m_nType|PARAMETER_TYPE|  
|m_bHasDefault|PARAMETER_HASDEFAULT|  
|m_szDefault|PARAMETER_DEFAULT|  
|m_bIsNullable|IS_NULLABLE|  
|m_nDataType|DATA_TYPE|  
|m_nMaxLength|CHARACTER_MAXIMUM_LENGTH|  
|m_nOctetLength|CHARACTER_OCTET_LENGTH|  
|m_nPrecision|NUMERIC_PRECISION|  
|m_nScale|NUMERIC_SCALE|  
|m_szDescription|DESCRIPTION|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRestrictions](../../data/oledb/crestrictions-class.md)