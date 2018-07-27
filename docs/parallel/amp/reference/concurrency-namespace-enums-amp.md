---
title: Пространство имен Concurrency перечислений (AMP) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a67b5e77b8ab8c52e55dea96e64a3f16a4d70e39
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695672"
---
# <a name="concurrency-namespace-enums-amp"></a>Пространство имен Concurrency перечислений (AMP)
|||  
|-|-|  
|[Перечисление access_type](#access_type)|[Перечисление queuing_mode](#queuing_mode)|  
  
##  <a name="access_type"></a>  Перечисление access_type  
 Тип перечисления, который используется для обозначения различных типов доступа к данным.  
  
```  
enum access_type;  
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`access_type_auto`|Выберите наиболее подходящий автоматически `access_type` для сочетания клавиш.|  
|`access_type_none`|Выделенные. Выделение доступен только на сочетания клавиш, а не на ЦП.|  
|`access_type_read`|Совместно. Выделение доступна на сочетания клавиш и доступен для чтения на ЦП.|  
|`access_type_read_write`|Совместно. Выделение доступна на сочетания клавиш и доступен для записи на ЦП.|  
|`access_type_write`|Совместно. Выделение доступна на сочетания клавиш и для чтения и записи на ЦП.|  

  
##  <a name="queuing_mode"></a>  Перечисление queuing_mode  
 Указывает режимы очередей, которые поддерживаются сочетания клавиш.  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`queuing_mode_immediate`|Режим постановки в очередь, указывающее, все команды, например, [parallel_for_each (C++ AMP) функция](concurrency-namespace-functions-amp.md#parallel_for_each), отправляются соответствующее устройство сочетаний клавиш, как только они возвращают вызывающему объекту.|  
|`queuing_mode_automatic`|Режим постановки в очередь, указывающее, помещено команды в очереди команд, соответствующий [accelerator_view](accelerator-view-class.md) объекта. Команды отправляются на устройство при [accelerator_view::flush](accelerator-view-class.md#flush) вызывается.|   
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
