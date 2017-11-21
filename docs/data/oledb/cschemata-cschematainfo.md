---
title: "CSchemata, CSchemataInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEFAULT_CHARACTER_SET_CATALOG
- DEFAULT_CHARACTER_SET_SCHEMA
- m_szCharName
- CSchemataInfo
- m_szCatalog
- m_szCharCatalog
- m_szOwner
- m_szCharSchema
- CSchemata
- m_szName
- DEFAULT_CHARACTER_SET_NAME
dev_langs: C++
helpviewer_keywords:
- m_szCharName
- CSchemata typedef class
- DEFAULT_CHARACTER_SET_NAME
- m_szOwner
- CSchemataInfo parameter class
- DEFAULT_CHARACTER_SET_CATALOG
- m_szCharSchema
- m_szCatalog
- m_szName
- m_szCharCatalog
- DEFAULT_CHARACTER_SET_SCHEMA
ms.assetid: 9d06d65a-c27b-446d-bc42-c7e487b0d9c5
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f1171117cba0d4a6448326d6e45d455557d9442b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cschemata-cschematainfo"></a>CSchemata, CSchemataInfo
Вызовите typedef-класс **CSchemata** реализации класса своего параметра **CSchemataInfo**.  
  
## <a name="remarks"></a>Примечания  
 В разделе [классы набора строк схемы и классы Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) Дополнительные сведения об использовании классов typedef.  
  
 Этот класс указывает схемы, принадлежащие данному пользователю.  
  
 В следующей таблице перечислены данные-члены класса и их соответствующие OLE DB столбцы. В разделе [набора строк СХЕМЫ](https://msdn.microsoft.com/en-us/library/ms716887.aspx) в *Справочник программиста OLE DB* Дополнительные сведения о схеме и столбцы.  
  
|Члены данных|Столбцы OLE DB|  
|------------------|--------------------|  
|m_szCatalog|CATALOG_NAME|  
|m_szName|SCHEMA_NAME|  
|m_szOwner|SCHEMA_OWNER|  
|m_szCharCatalog|DEFAULT_CHARACTER_SET_CATALOG|  
|m_szCharSchema|DEFAULT_CHARACTER_SET_SCHEMA|  
|m_szCharName|DEFAULT_CHARACTER_SET_NAME|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRestrictions](../../data/oledb/crestrictions-class.md)