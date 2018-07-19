---
title: Класс CDynamicStringAccessorA | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorA
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d6d05ac97846f55cf65d4010179b28d2b543ef66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096487"
---
# <a name="cdynamicstringaccessora-class"></a>Класс CDynamicStringAccessorA
Дает возможность доступа к источнику данных, если у вас нет сведений о схеме базы данных (базовая структура).  
  
## <a name="syntax"></a>Синтаксис

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>Примечания  
 Они оба запроса, что поставщик извлечь все данные из хранилища данных в виде строковых данных, но `CDynamicStringAccessor` запросов ANSI строковые данные.  
  
 `CDynamicStringAccessorA` наследует **GetString** и `SetString` из `CDynamicStringAccessor`. При использовании этих методов в `CDynamicStringAccessorA` объекта, ***BaseType*** — **CHAR**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-класс](../../data/oledb/caccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)