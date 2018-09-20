---
title: функции omp_unset_lock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_unset_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_lock OpenMP function
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe6d24c6d4fe6cd1df1eea6f0e575ff5c7947c56
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417050"
---
# <a name="ompunsetlock"></a>omp_unset_lock

Снимает блокировку.

## <a name="syntax"></a>Синтаксис

```
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) , инициализированный с [функции omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md), владельцем которых является поток и выполняется в функцию.

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.4 функции omp_unset_lock и omp_unset_nest_lock функции](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

## <a name="example"></a>Пример

См. в разделе [функции omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) пример использования `omp_unset_lock`.

## <a name="see-also"></a>См. также

[Функции](../../../parallel/openmp/reference/openmp-functions.md)