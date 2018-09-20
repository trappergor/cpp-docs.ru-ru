---
title: omp_set_num_threads | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_num_threads
dev_langs:
- C++
helpviewer_keywords:
- omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae9dbe52dba47208844b73175f20edcc591a3ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444948"
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads

Задает число потоков в последующих параллельных регионов, если не переопределено [num_threads](../../../parallel/openmp/reference/num-threads.md) предложение.

## <a name="syntax"></a>Синтаксис

```
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>Параметры

*num_threads*<br/>
Число потоков в параллельной области.

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.1.1 функция omp_set_num_threads](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).

## <a name="example"></a>Пример

См. в разделе [omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md) пример использования `omp_set_num_threads`.

## <a name="see-also"></a>См. также

[Функции](../../../parallel/openmp/reference/openmp-functions.md)