---
title: "BLOB_ENTRY_STATUS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BLOB_ENTRY_STATUS
dev_langs: C++
helpviewer_keywords: BLOB_ENTRY_STATUS macro
ms.assetid: 191007f4-dfcc-4ae2-a7fc-6f7899accc9f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0cc0805147908703b880cb826b0363acecfa4902
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="blobentrystatus"></a>BLOB_ENTRY_STATUS
При использовании `BEGIN_COLUMN_MAP` или `BEGIN_ACCESSOR_MAP` для привязки больших двоичных объектов ([больших двоичных ОБЪЕКТОВ](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Аналогично [BLOB_ENTRY](../../data/oledb/blob-entry.md), за исключением того, что этот макрос также получает состояние столбца большого двоичного ОБЪЕКТА.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BLOB_ENTRY_STATUS(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
,   
status  
 )  
  
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
  
 *status*  
 [out] Статус поля типа BLOB.  
  
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
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)