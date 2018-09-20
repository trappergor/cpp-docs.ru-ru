---
title: omp_get_dynamic | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2b5a285ef019cd1752b60065f7040d9a937ce38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389893"
---
# <a name="ompgetdynamic"></a>omp_get_dynamic

Возвращает значение, указывающее, если число потоков, доступных в последующих параллельной области могут быть изменены при время выполнения.

## <a name="syntax"></a>Синтаксис

```
int omp_get_dynamic();
```

## <a name="return-value"></a>Возвращаемое значение

Если значение ненулевое, динамическую настройку потоков включен.

## <a name="remarks"></a>Примечания

Динамическую настройку потоков указывается с помощью [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) и [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md).

Дополнительные сведения см. в разделе [3.1.7 функция omp_set_dynamic](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

## <a name="example"></a>Пример

См. в разделе [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) пример использования `omp_get_dynamic`.

## <a name="see-also"></a>См. также

[Функции](../../../parallel/openmp/reference/openmp-functions.md)