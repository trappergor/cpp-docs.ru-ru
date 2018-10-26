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
ms.openlocfilehash: 97cf6ccad0a3b30c0abfa0076ea9c6a30b205d67
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065204"
---
# <a name="openmp-data-types"></a>Типы данных OpenMP

Содержит ссылки на типы данных, используемые в OpenMP API.

Реализация Visual C++ OpenMP standard включает следующие типы данных.

|Тип данных|Описание|
|---------|-----------|
|[omp_lock_t](#omp-lock-t)|Тип, содержащий состояние блокировки, доступен ли блокировка, или если поток владеет блокировкой.|
|[omp_nest_lock_t](#omp-nest-lock-t)|Тип, содержащий один из следующих элементов информации о блокировке: ли доступна блокировка, и идентификатор потока, которому принадлежит блокировка и вложенности счетчик.|

## <a name="omp-lock-t"></a>omp_lock_t

Тип, содержащий состояние блокировки, доступен ли блокировка, или если поток владеет блокировкой.

Следующие функции используйте `omp_lock_t`:

- [omp_init_lock](openmp-functions.md#omp-init-lock)
- [omp_destroy_lock](openmp-functions.md#omp-destroy-lock)
- [omp_set_lock](openmp-functions.md#omp-set-lock)
- [omp_unset_lock](openmp-functions.md#omp-unset-lock)
- [omp_test_lock](openmp-functions.md#omp-test-lock)

Дополнительные сведения см. в разделе [3.2 функции блокировки](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Пример

См. в разделе [функции omp_init_lock](openmp-functions.md#omp-init-lock) пример использования `omp_lock_t`.

## <a name="omp-nest-lock-t"></a>omp_nest_lock_t

Тип, содержащий следующие сведения о блокировке: ли доступна блокировка, и идентификатор потока, которому принадлежит блокировка и вложенности счетчик.

Следующие функции используйте `omp_nest_lock_t`:

- [omp_init_nest_lock](openmp-functions.md#omp-init-nest-lock)
- [omp_destroy_nest_lock](openmp-functions.md#omp-destroy-nest-lock)
- [omp_set_nest_lock](openmp-functions.md#omp-set-nest-lock)
- [omp_unset_nest_lock](openmp-functions.md#omp-unset-nest-lock)
- [omp_test_nest_lock](openmp-functions.md#omp-test-nest-lock)

Дополнительные сведения см. в разделе [3.2 функции блокировки](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Пример

См. в разделе [omp_init_nest_lock](openmp-functions.md#omp-init-nest-lock) пример использования `omp_nest_lock_t`.
