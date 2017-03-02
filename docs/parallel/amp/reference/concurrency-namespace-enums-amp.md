---
title: "Перечисления имен Concurrency (AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b9555023e01cb765ca943fcaaf785cdc2b4e2d0d
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-enums-amp"></a>Перечисления имен Concurrency (AMP)
|||  
|-|-|  
|[Перечисление access_type](#access_type)|[Перечисление queuing_mode](#queuing_mode)|  
  
##  <a name="a-nameaccesstypea--accesstype-enumeration"></a><a name="access_type"></a>Перечисление access_type  
 Тип перечисления, который используется для обозначения различных типов доступа к данным.  
  
```  
enum access_type;  
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`access_type_auto`|Автоматически выбирает лучший `access_type` для сочетания клавиш.|  
|`access_type_none`|Выделенные. Выделение доступно только на сочетания клавиш, а не на ЦП.|  
|`access_type_read`|Совместно. Выделение доступен на сочетания клавиш и для чтения на ЦП.|  
|`access_type_read_write`|Совместно. Выделение доступен на сочетания клавиш и записи на ЦП.|  
|`access_type_write`|Совместно. Выделение доступен на сочетания клавиш и для чтения и записи на ЦП.|  

  
##  <a name="a-namequeuingmodea--queuingmode-enumeration"></a><a name="queuing_mode"></a>Перечисление queuing_mode  
 Указывает режимы очереди, которые поддерживаются сочетания клавиш.  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`queuing_mode_immediate`|Режим постановки в очередь, указывающее любые команды, например, [функция parallel_for_each (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), отправляются на соответствующее устройство сочетаний клавиш по мере их возвращения вызывающему.|  
|`queuing_mode_automatic`|Режим постановки в очередь, указывающее, помещено команды в очереди команд, которые соответствуют [accelerator_view](accelerator-view-class.md) объекта. Команды отправляются на устройство при [accelerator_view::flush](accelerator-view-class.md#flush) вызывается.|   
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

