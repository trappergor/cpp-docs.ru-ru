---
title: Типы данных OpenMP | Документация Майкрософт
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OpenMP data types
- omp_lock_t
- omp_nest_lock_t
dev_langs:
- C++
helpviewer_keywords:
- OpenMP data types
- omp_lock_t OpenMP data type
- omp_nest_lock_t OpenMP data type
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 254dffebc258867088f738b10a11bf48d31bd0a4
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990074"
---
# <a name="openmp-data-types"></a>Типы данных OpenMP

Содержит ссылки на типы данных, используемые в OpenMP API.

Реализация Visual C++ OpenMP standard включает следующие типы данных.

Тип данных                           | Описание
----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[omp_lock_t](#omp-lock-t)           | Тип, содержащий состояние блокировки, доступен ли блокировка, или если поток владеет блокировкой.
[omp_nest_lock_t](#omp-nest-lock-t) | Тип, содержащий один из следующих элементов информации о блокировке: ли доступна блокировка, и идентификатор потока, которому принадлежит блокировка и вложенности счетчик.

## <a name="omp-lock-t"></a>omp_lock_t

Тип, содержащий состояние блокировки, доступен ли блокировка, или если поток владеет блокировкой.

Следующие функции используйте `omp_lock_t`:

- [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)
- [omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)
- [omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)
- [omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)
- [omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)

Дополнительные сведения см. в разделе [3.2 функции блокировки](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Пример

См. в разделе [функции omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) пример использования `omp_lock_t`.

## <a name="omp-nest-lock-t"></a>omp_nest_lock_t

Тип, содержащий следующие сведения о блокировке: ли доступна блокировка, и идентификатор потока, которому принадлежит блокировка и вложенности счетчик.

Следующие функции используйте `omp_nest_lock_t`:

- [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)
- [omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)
- [omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)
- [omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)
- [omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)

Дополнительные сведения см. в разделе [3.2 функции блокировки](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Пример

См. в разделе [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) пример использования `omp_nest_lock_t`.
