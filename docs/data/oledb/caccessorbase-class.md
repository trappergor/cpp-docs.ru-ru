---
title: Класс CAccessorBase | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorBase
dev_langs:
- C++
helpviewer_keywords:
- CAccessorBase class
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f598f49d279085b23e0bd3b94c48620363b5a816
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090800"
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