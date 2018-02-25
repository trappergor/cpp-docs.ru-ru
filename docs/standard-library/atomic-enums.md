---
title: "Перечисления &lt;atomic&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
caps.latest.revision: 
helpviewer_keywords:
- std::memory_order
manager: ghogen
ms.openlocfilehash: 5f5c286375699d233d1bc9dadd3f44992309fa0a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltatomicgt-enums"></a>Перечисления &lt;atomic&gt;
  
##  <a name="memory_order_enum"></a>Перечисление memory_order  
 Предоставляет символьные имена для операций синхронизации в областях памяти. Эти операции влияют на то, как присвоения в одном потоке становятся видимыми в другом.  
  
```
typedef enum memory_order {
    memory_order_relaxed,
    memory_order_consume,
    memory_order_acquire,
    memory_order_release,
    memory_order_acq_rel,
    memory_order_seq_cst,
} memory_order;
```  
  
### <a name="remarks"></a>Примечания  
  
|||  
|-|-|  
|`memory_order_relaxed`|Упорядочивание не требуется.|  
|`memory_order_consume`|Операция load действует как операция consume в расположении в памяти.|  
|`memory_order_acquire`|Операция load действует как операция cquire в расположении в памяти.|  
|`memory_order_release`|Операция store действует как операция release в расположении в памяти.|  
|`memory_order_acq_rel`|Объединяет `memory_order_acquire` и `memory_order_release`.|  
|`memory_order_seq_cst`|Объединяет `memory_order_acquire` и `memory_order_release`. Обращения к памяти, которые помечены как `memory_order_seq_cst`, должны быть последовательно согласованными.|  
  
## <a name="see-also"></a>См. также  
 [\<atomic>](../standard-library/atomic.md)



