---
title: Класс parallel_unsequenced_policy
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_unsequenced_policy
ms.openlocfilehash: 92b4e3ce3743fdd3d5ba112a333b2306829b95d4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268786"
---
# <a name="parallelunsequencedpolicy-class"></a>Класс parallel_unsequenced_policy

Используется как уникальный тип для устранения неоднозначности перегрузки параллельный алгоритм и указать, что параллельный алгоритм выполнения может быть параллелизован и преобразованы в векторный формат.

## <a name="syntax"></a>Синтаксис

```cpp
class execution::parallel_unsequenced_policy;
```

## <a name="remarks"></a>Примечания

Во время выполнения параллельного алгоритма с `execution::parallel_unsequenced_policy` политики, если вызов функции доступа элемент завершается через неперехваченное исключение `terminate()` должны вызываться.
