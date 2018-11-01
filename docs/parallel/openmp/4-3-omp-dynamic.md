---
title: 4.3 OMP_DYNAMIC
ms.date: 11/04/2016
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
ms.openlocfilehash: 0ea6784159a11fc194d0c1cd16d2316a80b9cd37
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488573"
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC

**OMP_DYNAMIC** переменной среды, включает или отключает динамическую настройку количество потоков, доступных для выполнения параллельных регионов, если только явным образом включен или отключен, вызвав динамическуюнастройку**omp_set_dynamic** подпрограмма библиотеки. Его значение должно быть **TRUE** или **FALSE**.

Если значение **TRUE**, число потоков, которые используются для выполнения параллельных регионов можно менять в среде, для наиболее эффективного использования системных ресурсов.  Если значение **FALSE**, динамическую настройку отключен. Условие по умолчанию определяется реализацией.

Пример

```
setenv OMP_DYNAMIC TRUE
```

## <a name="cross-references"></a>Перекрестные ссылки:

- Дополнительные сведения о параллельных регионов см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".

- **omp_set_dynamic** функции, см. в разделе [разделе 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на стр. 39.