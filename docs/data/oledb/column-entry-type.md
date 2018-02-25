---
title: "COLUMN_ENTRY_TYPE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_TYPE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_TYPE macro
ms.assetid: ac424261-ff6c-443b-a197-2cec8d78d738
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: de5ead25c4e1c95b98411602a420cc424ff0c716
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="columnentrytype"></a>COLUMN_ENTRY_TYPE
Представляет привязку к указанному столбцу в базе данных. Поддерживает `type` параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `nOrdinal`  
 [in] Номер столбца.  
  
 `wType`  
 [in] Тип данных записи в столбце.  
  
 `data`  
 [in] Соответствующего члена данных в записи пользователя.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос – это специализированный вариант [COLUMN_ENTRY](../../data/oledb/column-entry.md) макрос, который служит для указания типа данных.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)