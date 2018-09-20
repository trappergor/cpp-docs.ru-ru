---
title: omp_unset_nest_lock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_unset_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_nest_lock OpenMP function
ms.assetid: 1721d061-3f9c-45d7-b479-a665cd0a121d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03ea941e793f8c3a9f40e0495442deb71b2ffa93
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402724"
---
# <a name="ompunsetnestlock"></a>omp_unset_nest_lock

Освобождает блокировку вкладываемых.

## <a name="syntax"></a>Синтаксис

```
void omp_unset_nest_lock( 
   omp_nest_lock_t *lock 
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) , инициализированный с [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md), владельцем которых является поток и выполняется в функцию.

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.4 функции omp_unset_lock и omp_unset_nest_lock функции](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

## <a name="example"></a>Пример

См. в разделе [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) пример использования `omp_unset_nest_lock`.

## <a name="see-also"></a>См. также

[Функции](../../../parallel/openmp/reference/openmp-functions.md)