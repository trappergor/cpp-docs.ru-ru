---
title: "Пространство имен Concurrency перечислений (AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d17378a34698cc80d356983898e0023b76877140
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="concurrency-namespace-enums-amp"></a>Пространство имен Concurrency перечислений (AMP)
|||  
|-|-|  
|[access_type Enumeration](#access_type)|[queuing_mode Enumeration](#queuing_mode)|  
  
##  <a name="access_type"></a>  access_type Enumeration  
 Тип перечисления, который используется для обозначения различных типов доступа к данным.  
  
```  
enum access_type;  
```  
### <a name="values"></a>Значения  
  
|Имя|Описание:|  
|----------|-----------------|  
|`access_type_auto`|Выберите наиболее подходящий автоматически `access_type` для сочетания клавиш.|  
|`access_type_none`|Выделенные. Выделение доступен только на сочетания клавиш, а не на ЦП.|  
|`access_type_read`|Совместно. Выделение доступна на сочетания клавиш и доступен для чтения на ЦП.|  
|`access_type_read_write`|Совместно. Выделение доступна на сочетания клавиш и доступен для записи на ЦП.|  
|`access_type_write`|Совместно. Выделение доступна на сочетания клавиш и для чтения и записи на ЦП.|  

  
##  <a name="queuing_mode"></a>  queuing_mode Enumeration  
 Указывает режимы очередей, которые поддерживаются сочетания клавиш.  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>Значения  
  
|Имя|Описание:|  
|----------|-----------------|  
|`queuing_mode_immediate`|Режим постановки в очередь, указывающее, все команды, например, [parallel_for_each (C++ AMP) функция](concurrency-namespace-functions-amp.md#parallel_for_each), отправляются соответствующее устройство сочетаний клавиш, как только они возвращают вызывающему объекту.|  
|`queuing_mode_automatic`|Режим постановки в очередь, указывающее, помещено команды в очереди команд, соответствующий [accelerator_view](accelerator-view-class.md) объекта. Команды отправляются на устройство при [accelerator_view::flush](accelerator-view-class.md#flush) вызывается.|   
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
