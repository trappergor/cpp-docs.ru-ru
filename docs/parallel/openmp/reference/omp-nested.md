---
title: OMP_NESTED | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c90878ce96cf1639c983be899ba13eccf1f040e8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376549"
---
# <a name="ompnested"></a>OMP_NESTED

Указывает, включен ли вложенный параллелизм, если не включена или отключена с помощью вложенных параллелизма `omp_set_nested`.

## <a name="syntax"></a>Синтаксис

```
set OMP_NESTED[=TRUE | =FALSE]
```

## <a name="remarks"></a>Примечания

`OMP_NESTED` Переменной среды могут быть переопределены [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) функции.

Значение по умолчанию в Visual C++ реализации стандарта OpenMP — `OMP_DYNAMIC=FALSE`.

Дополнительные сведения см. в разделе [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).

## <a name="example"></a>Пример

Следующая команда задает `OMP_NESTED` переменной среды в значение TRUE:

```
set OMP_NESTED=TRUE
```

Следующая команда отображает текущее значение параметра `OMP_NESTED` переменной среды:

```
set OMP_NESTED
```

## <a name="see-also"></a>См. также

[Переменные среды](../../../parallel/openmp/reference/openmp-environment-variables.md)