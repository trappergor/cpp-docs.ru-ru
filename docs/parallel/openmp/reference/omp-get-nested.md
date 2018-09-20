---
title: omp_get_nested | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20a7378ba7e7f6dcec55cfe265dd0873bdc1fd38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46371957"
---
# <a name="ompgetnested"></a>omp_get_nested

Возвращает значение, указывающее, включена ли вложенные параллелизма.

## <a name="syntax"></a>Синтаксис

```
int omp_get_nested( );
```

## <a name="return-value"></a>Возвращаемое значение

Если значение ненулевое, включен вложенный параллелизм.

## <a name="remarks"></a>Примечания

Вложенный параллелизм указывается с помощью [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) и [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md).

Дополнительные сведения см. в разделе [3.1.10 функция omp_get_nested](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).

## <a name="example"></a>Пример

См. в разделе [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) пример использования `omp_get_nested`.

## <a name="see-also"></a>См. также

[Функции](../../../parallel/openmp/reference/openmp-functions.md)