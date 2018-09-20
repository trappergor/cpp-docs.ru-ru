---
title: 4.2 OMP_NUM_THREADS | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9996a09661d962eb5e936fdb484c9dd534e46904
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445195"
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS

**OMP_NUM_THREADS** переменной среды задает по умолчанию количество потоков, используемых во время выполнения, если это число изменяется явно, вызвав **omp_set_num_threads** подпрограмма библиотеки или При получении явного **num_threads** предложение на **параллельных** директива.

Значение **OMP_NUM_THREADS** переменной среды должно быть положительным целым числом. Ее результат зависит от того, включен ли динамическую настройку количество потоков. Доступен широкий набор правил о взаимодействии между **OMP_NUM_THREADS** среды переменных и динамические коррекции потоков, см. в разделе 2.3 раздел на странице "8".

Если значение не указано для **OMP_NUM_THREADS** переменной среды, или если указано значение не является положительным целым числом, или если значение больше, чем максимальное число потоков система может поддерживать, количество потоков, используемых определяется реализацией.

Пример

```
setenv OMP_NUM_THREADS 16
```

## <a name="cross-references"></a>Перекрестные ссылки:

- **num_threads** предложение, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".

- **omp_set_num_threads** функции, см. в разделе [разделе 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) на странице 36.

- **omp_set_dynamic** функции, см. в разделе [разделе 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на стр. 39.