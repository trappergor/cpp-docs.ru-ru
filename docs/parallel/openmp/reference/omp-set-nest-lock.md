---
title: omp_set_nest_lock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nest_lock OpenMP function
ms.assetid: b98ed889-ff8e-4217-a3e9-3993ed8699af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e7ca097219297038728adc3924980e8c91e25ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438591"
---
# <a name="ompsetnestlock"></a>omp_set_nest_lock

Блокирует выполнение потока, пока не станет доступна блокировка.

## <a name="syntax"></a>Синтаксис

```
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) , инициализированный с [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md).

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.3 функции omp_set_lock и omp_set_nest_lock функции](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

## <a name="examples"></a>Примеры

См. в разделе [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) пример использования `omp_set_nest_lock`.

## <a name="see-also"></a>См. также

[Функции](../../../parallel/openmp/reference/openmp-functions.md)