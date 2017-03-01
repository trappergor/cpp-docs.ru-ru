---
title: "Перечисления &lt;atomic&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 94167b5068e3fb1370528d42c80d338a486cd68e
ms.lasthandoff: 02/24/2017

---
# <a name="ltatomicgt-enums"></a>Перечисления &lt;atomic&gt;
  
##  <a name="a-namememoryorderenuma--memoryorder-enum"></a><a name="memory_order_enum"></a>Перечисление memory_order  
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




