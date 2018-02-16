---
title: "Класс CAccessorBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
ms.openlocfilehash: 0f57c771f0d129683bde0629f9c28cfbaa897ee4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
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