---
title: OMP_DYNAMIC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_DYNAMIC
dev_langs:
- C++
helpviewer_keywords:
- OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b02a2a4d660057ab83da39add7fd32bcff3e6d90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392142"
---
# <a name="ompdynamic"></a>OMP_DYNAMIC

Указывает, может ли изменять количество потоков в параллельной области OpenMP, время выполнения.

## <a name="syntax"></a>Синтаксис

```
set OMP_DYNAMIC[=TRUE | =FALSE]
```

## <a name="remarks"></a>Примечания

`OMP_DYNAMIC` Переменной среды могут быть переопределены [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) функции.

Значение по умолчанию в Visual C++ реализации стандарта OpenMP — `OMP_DYNAMIC=FALSE`.

Дополнительные сведения см. в разделе [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).

## <a name="example"></a>Пример

Следующая команда задает `OMP_DYNAMIC` переменной среды в значение TRUE:

```
set OMP_DYNAMIC=TRUE
```

Следующая команда отображает текущее значение параметра `OMP_DYNAMIC` переменной среды:

```
set OMP_DYNAMIC
```

## <a name="see-also"></a>См. также

[Переменные среды](../../../parallel/openmp/reference/openmp-environment-variables.md)