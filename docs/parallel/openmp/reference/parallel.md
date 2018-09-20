---
title: Параллельные | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- parallel
dev_langs:
- C++
helpviewer_keywords:
- parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38b5bd4d277987be78cbd3714302c8b7f704b90f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405220"
---
# <a name="parallel"></a>parallel

Определяет параллельной области, который приведен код, который будет выполняться сразу несколько потоков параллельно.

## <a name="syntax"></a>Синтаксис

```
#pragma omp parallel [clauses]
{
   code_block
}
```

## <a name="arguments"></a>Аргументы

*Предложение*<br/>
(Необязательно) Ноль или несколько предложений.  См. в разделе "Примечания" для получения списка предложений, поддерживаемые **параллельных**.

## <a name="remarks"></a>Примечания

**Параллельных** директива поддерживает следующие предложения OpenMP:

- [copyin](../../../parallel/openmp/reference/copyin.md)

- [default](../../../parallel/openmp/reference/default-openmp.md)

- [firstprivate](../../../parallel/openmp/reference/firstprivate.md)

- [if](../../../parallel/openmp/reference/if-openmp.md)

- [num_threads](../../../parallel/openmp/reference/num-threads.md)

- [private](../../../parallel/openmp/reference/private-openmp.md)

- [reduction](../../../parallel/openmp/reference/reduction.md)

- [Общие](../../../parallel/openmp/reference/shared-openmp.md)

**Параллельные** также может использоваться с [разделах](../../../parallel/openmp/reference/sections-openmp.md) и [для](../../../parallel/openmp/reference/for-openmp.md) директивы.

Дополнительные сведения см. в разделе [2.3 конструкция parallel](../../../parallel/openmp/2-3-parallel-construct.md).

## <a name="example"></a>Пример

Следующий пример показано, как настроить количество потоков и определить область параллельной обработки. По умолчанию количество потоков равно числу логических процессоров на компьютере. Например если машины с одним физическим процессором с поддержкой технологии Hyper-Threading, он будет иметь два логических процессора и, следовательно, два потока.

```
// omp_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(4)
   {
      int i = omp_get_thread_num();
      printf_s("Hello from thread %d\n", i);
   }
}
```

```Output
Hello from thread 0
Hello from thread 1
Hello from thread 2
Hello from thread 3
```

## <a name="comment"></a>Комментарий

Обратите внимание, что порядок выходных данных могут различаться на разных компьютерах.

## <a name="see-also"></a>См. также

[Директивы](../../../parallel/openmp/reference/openmp-directives.md)