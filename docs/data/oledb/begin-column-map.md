---
title: "BEGIN_COLUMN_MAP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_COLUMN_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_COLUMN_MAP macro
ms.assetid: d6ffe633-e0da-4e33-8faa-f7f259d05420
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9edcaa47bccf0665ddeabf4e65e16ab1642de885
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="begincolumnmap"></a>BEGIN_COLUMN_MAP
Отмечает начало карты записей столбцов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BEGIN_COLUMN_MAP(  
x  
 )  
  
```  
  
#### <a name="parameters"></a>Параметры  
 *x*  
 [входные данные] Имя класса записей пользователя, производного от `CAccessor`.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос используется при наличии одного метода доступа в наборе строк. При наличии нескольких методов доступа в наборе строк, используйте [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
 Макрос `BEGIN_COLUMN_MAP` выполняется с помощью макроса `END_COLUMN_MAP` . Этот макрос используется, если имеется только один метод доступа, необходимый для записи пользователя.  
  
 Столбцы соответствуют полям в наборе строк, который нужно привязать.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример карты столбцов и параметров.  
  
 <!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)