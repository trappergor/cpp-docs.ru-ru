---
title: CCatalogs, CCatalogInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCatalogs
- m_szName
- CCatalogInfo
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- CCatalogInfo parameter class
- CCatalogs typedef class
- m_szName
- m_szDescription
ms.assetid: 8362cbbd-2f00-4272-8518-fc235c4de193
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a62c0a95e057d3ffa96f59fc1c460de78c031550
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091589"
---
# <a name="ccatalogs-ccataloginfo"></a>CCatalogs, CCatalogInfo
Вызовите typedef-класс **CCatalogs** реализации класса своего параметра **CCatalogInfo**.  
  
## <a name="remarks"></a>Примечания  
 В разделе [классы набора строк схемы и классы Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) Дополнительные сведения об использовании классов typedef.  
  
 Этот класс определяет физические атрибуты, связанные с каталогами, доступными из СУБД.  
  
 В следующей таблице перечислены данные-члены класса и их соответствующие OLE DB столбцы. В разделе [КАТАЛОГОВ набора строк](https://msdn.microsoft.com/en-us/library/ms721241.aspx) в *Справочник программиста OLE DB* Дополнительные сведения о схеме и столбцы.  
  
|Члены данных|Столбцы OLE DB|  
|------------------|--------------------|  
|m_szName|CATALOG_NAME|  
|m_szDescription|DESCRIPTION|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbsch.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRestrictions](../../data/oledb/crestrictions-class.md)