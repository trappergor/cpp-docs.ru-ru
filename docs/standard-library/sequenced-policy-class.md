---
title: Класс sequenced_policy
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 63be7166b84fa452f53baf6b6de16831eb657a23
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269196"
---
# <a name="sequencedpolicy-class"></a>Класс sequenced_policy

Используется как уникальный тип для устранения неоднозначности перегрузки параллельного алгоритма и требуют, что выполнение параллельного алгоритма не может выполняться параллельно.

## <a name="syntax"></a>Синтаксис

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>Примечания

Во время выполнения параллельного алгоритма с `execution::sequenced_policy` политики, если вызов функции доступа элемент завершается через неперехваченное исключение `terminate()` должны вызываться.
