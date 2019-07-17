---
title: Класс parallel_policy
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 7bb2b095a50e664dfc585e0bd4aaa608a6ad8e95
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268966"
---
# <a name="parallelpolicy-class"></a>Класс parallel_policy

Используется как уникальный тип для устранения неоднозначности перегрузки параллельный алгоритм и указать, что выполнение параллельного алгоритма может выполняться параллельно.

## <a name="syntax"></a>Синтаксис

```cpp
class execution::parallel_policy;
```

## <a name="remarks"></a>Примечания

Во время выполнения параллельного алгоритма с `execution::parallel_policy` политики, если вызов функции доступа элемент завершается через неперехваченное исключение `terminate()` должны вызываться.
