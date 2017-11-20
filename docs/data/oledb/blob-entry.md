---
title: "BLOB_ENTRY | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BLOB_ENTRY
dev_langs: C++
helpviewer_keywords: BLOB_ENTRY macro
ms.assetid: 89e40678-0869-49ed-b502-0fa2630a9081
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ac3a4760777b2a6b4cb5d24787c3ae5edb6c3640
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="blobentry"></a>BLOB_ENTRY
При использовании `BEGIN_COLUMN_MAP` и `END_COLUMN_MAP` для привязки больших двоичных объектов ([больших двоичных ОБЪЕКТОВ](https://msdn.microsoft.com/en-us/library/ms711511.aspx)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BLOB_ENTRY(  
nOrdinal  
,  
 IID  
,   
flags  
,   
data  
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
  
## <a name="example"></a>Пример  
 В разделе [способ получения большого двоичного ОБЪЕКТА?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)