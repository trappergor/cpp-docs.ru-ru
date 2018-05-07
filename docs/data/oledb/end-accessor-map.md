---
title: END_ACCESSOR_MAP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- END_ACCESSOR_MAP
dev_langs:
- C++
helpviewer_keywords:
- END_ACCESSOR_MAP macro
ms.assetid: ede813c7-46c9-48a6-aa1a-8ebf38e92023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 647e581a86564221ad409caf9addd03ae3d11fb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="endaccessormap"></a>END_ACCESSOR_MAP
Отмечает конец карты записей метода доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
END_ACCESSOR_MAP()  
  
```  
  
## <a name="remarks"></a>Примечания  
 Для нескольких методов доступа в наборе строк, необходимо указать `BEGIN_ACCESSOR_MAP` и использовать `BEGIN_ACCESSOR` макрос для каждого отдельного метода доступа. Макрос `BEGIN_ACCESSOR` выполняется с помощью макроса `END_ACCESSOR` . `BEGIN_ACCESSOR_MAP` Завершилась макрос `END_ACCESSOR_MAP` макрос.  
  
## <a name="example"></a>Пример  
 В разделе [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)