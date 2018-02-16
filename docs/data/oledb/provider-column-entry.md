---
title: "PROVIDER_COLUMN_ENTRY | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROVIDER_COLUMN_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY macro
ms.assetid: 7921cfc1-aa9c-493e-8fc4-9d4294cafe72
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 698ff2c122366bca87d71c812ce6f4e115f2534b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="providercolumnentry"></a>PROVIDER_COLUMN_ENTRY
Представляет отдельного столбца, поддерживаемых поставщиком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY (name  
, ordinal, member )  
```  
  
#### <a name="parameters"></a>Параметры  
 *name*  
 [in] Имя столбца.  
  
 `ordinal`  
 [in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
 `member`  
 [in] В переменной-члена `dataClass` соответствующий столбец.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)