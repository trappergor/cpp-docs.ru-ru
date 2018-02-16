---
title: "PROVIDER_COLUMN_ENTRY_FIXED | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROVIDER_COLUMN_ENTRY_FIXED
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_FIXED macro
ms.assetid: 71f9c9aa-56a0-488b-96ba-5c72da9c71d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f374f5e7d4a2dfd24cdd3b2067b0bda935ce438f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="providercolumnentryfixed"></a>PROVIDER_COLUMN_ENTRY_FIXED
Представляет отдельного столбца, поддерживаемых поставщиком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY_FIXED(name  
, ordinal, dbtype, member )  
```  
  
#### <a name="parameters"></a>Параметры  
 *name*  
 [in] Имя столбца.  
  
 `ordinal`  
 [in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
 `dbtype`  
 [in] Тип данных в [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
 `member`  
 [in] В переменной-члена `dataClass` , сохраняет данные.  
  
## <a name="remarks"></a>Примечания  
 Позволяет указать тип данных столбца.  
  
## <a name="example"></a>Пример  
 В разделе [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)