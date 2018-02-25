---
title: "Класс CAccessorBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccessorBase
dev_langs:
- C++
helpviewer_keywords:
- CAccessorBase class
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 030e06c40912a6b32c076b86f4a7456177b4ce93
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="caccessorbase-class"></a>Класс CAccessorBase
Все методы доступа в шаблонах OLE DB являются производными от этого класса. `CAccessorBase` позволяет одному набору строк для управления несколько методов доступа. Он также предоставляет привязки параметров и выходных столбцов.  
  
## <a name="syntax"></a>Синтаксис

```cpp
// Replace with syntax  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Закрыть](../../data/oledb/caccessorbase-close.md)|Закрывает методы доступа.|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|Извлекает дескриптор метода доступа.|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|Получает число методов доступа, созданный классом.|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|Проверяет, является ли указанный метод доступа автоматическим.|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|Освобождает методы доступа.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)