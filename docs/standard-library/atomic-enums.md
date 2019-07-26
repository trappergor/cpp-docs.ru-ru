---
title: Перечисления &lt;atomic&gt;
ms.date: 11/04/2016
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
helpviewer_keywords:
- std::memory_order
ms.openlocfilehash: 14b816177593a9f6dade60e36676a37f724fc209
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457598"
---
# <a name="ltatomicgt-enums"></a>Перечисления &lt;atomic&gt;

## <a name="memory_order_enum"></a>Перечисление memory_order

Предоставляет символьные имена для операций синхронизации в областях памяти. Эти операции влияют на то, как присвоения в одном потоке становятся видимыми в другом.

```cpp
typedef enum memory_order {
    memory_order_relaxed,
    memory_order_consume,
    memory_order_acquire,
    memory_order_release,
    memory_order_acq_rel,
    memory_order_seq_cst,
} memory_order;
```

### <a name="enumeration-members"></a>Члены перечисления

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
