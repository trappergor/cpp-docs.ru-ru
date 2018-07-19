---
title: COLUMN_NAME_TYPE_SIZE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_NAME_TYPE_SIZE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_NAME_TYPE_SIZE macro
ms.assetid: b10f8ef9-78ce-4ec9-b4cc-4278271a46dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2c937a5f0f91eb72486d7f1044eb1ec8729011f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098034"
---
# <a name="columnnametypesize"></a>COLUMN_NAME_TYPE_SIZE
Представляет привязку в наборе строк для конкретного столбца в наборе строк. Аналогично [COLUMN_NAME](../../data/oledb/column-name.md), за исключением того, что этот макрос также принимает тип данных и размер.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `pszName`  
 [in] Указатель на имя столбца. Имя должно быть строкой в Юникоде. Это можно сделать, поместив «L» перед именем, например: `L"MyColumn"`.  
  
 `wType`  
 [in] Тип данных.  
  
 `nLength`  
 [in] Объем данных в байтах.  
  
 `data`  
 [in] Соответствующего члена данных в записи пользователя.  
  
## <a name="remarks"></a>Примечания  
 В разделе [COLUMN_NAME](../../data/oledb/column-name.md) сведения о том, где **COLUMN_NAME_\***  используются макросы.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME](../../data/oledb/column-name.md)   
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)