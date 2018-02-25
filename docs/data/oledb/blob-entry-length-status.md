---
title: "BLOB_ENTRY_LENGTH_STATUS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- BLOB_ENTRY_LENGTH_STATUS
dev_langs:
- C++
helpviewer_keywords:
- BLOB_ENTRY_LENGTH_STATUS macro
ms.assetid: 09da67de-421b-4853-9a26-760e38324502
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6fe176d984937a39a3f76981f57388a69f21c0f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="blobentrylengthstatus"></a>BLOB_ENTRY_LENGTH_STATUS
При использовании `BEGIN_COLUMN_MAP` и `END_COLUMN_MAP` для привязки больших двоичных объектов ([больших двоичных ОБЪЕКТОВ](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Аналогично [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос также возвращает длину и состояние столбца большого двоичного ОБЪЕКТА.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
BLOB_ENTRY_LENGTH_STATUS(  
    nOrdinal,  
    IID,  
    flags,  
    data,
    length,
    status )  
```  
  
#### <a name="parameters"></a>Параметры  
 `nOrdinal`  
 [in] Номер столбца.  
  
 *IID*  
 [in] Интерфейс GUID, таких как **IDD_ISequentialStream**, который применяется для получения большого двоичного ОБЪЕКТА.  
  
 `flags`  
 [in] Режим хранения помечается как определяются моделью структурированного хранения OLE (например, **STGM_READ**).  
  
 `data`  
 [in] Соответствующего члена данных в записи пользователя.  
  
 *length*  
 [out] (Фактические) длина в байтах столбца большого двоичного ОБЪЕКТА.  
  
 *status*  
 [out] Состояние столбца данных большого двоичного ОБЪЕКТА.  
  
## <a name="example"></a>Пример  
 В разделе [способ получения большого двоичного ОБЪЕКТА?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)