---
title: "BLOB_NAME_LENGTH | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BLOB_NAME_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- BLOB_NAME_LENGTH macro
ms.assetid: 38150260-a127-486d-a7ab-0d01b731b6fd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 437c5a355de0c4655fc6beac00d4497c14ea3f2d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="blobnamelength"></a>BLOB_NAME_LENGTH
При использовании `BEGIN_COLUMN_MAP` и `END_COLUMN_MAP` для привязки больших двоичных объектов ([больших двоичных ОБЪЕКТОВ](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Аналогично [BLOB_NAME](../../data/oledb/blob-name.md), за исключением того, что этот макрос также возвращает длину в байтах данных столбца больших двоичных ОБЪЕКТОВ.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )  
```  
  
#### <a name="parameters"></a>Параметры  
 `pszName`  
 [in] Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
 *IID*  
 [in] Интерфейс GUID, таких как **IDD_ISequentialStream**, который применяется для получения большого двоичного ОБЪЕКТА.  
  
 `flags`  
 [in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, **STGM_READ**).  
  
 `data`  
 [in] Соответствующего члена данных в записи пользователя.  
  
 *length*  
 [out] (Фактические) длина в байтах столбца большого двоичного ОБЪЕКТА.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_NAME](../../data/oledb/blob-name.md)   
 [BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)