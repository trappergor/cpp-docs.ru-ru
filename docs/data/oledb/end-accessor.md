---
title: "END_ACCESSOR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: END_ACCESSOR
dev_langs: C++
helpviewer_keywords: END_ACCESSOR macro
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f0dceb1fe648a67d10fb18b353a5de54fa39caee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="endaccessor"></a>END_ACCESSOR
Помечает конец записи метода доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
END_ACCESSOR( )  
  
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
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)