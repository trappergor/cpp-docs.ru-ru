---
title: OMP_SCHEDULE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 507067be30db019536ef222a62335244eabfaada
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413865"
---
# <a name="ompschedule"></a>OMP_SCHEDULE

Изменяет поведение [расписание](../../../parallel/openmp/reference/schedule.md) предложение при `schedule(runtime)` указывается в `for` или `parallel for` директива.

## <a name="syntax"></a>Синтаксис

```
set OMP_SCHEDULE[=type[,size]]
```

## <a name="arguments"></a>Аргументы

*size*<br/>
(Необязательно) Указывает размер итераций. `size` Должно быть положительным целым числом. Значение по умолчанию равно 1, за исключением случаев `type` является статическим. Не является допустимым, если `type` является `runtime`.

*type*<br/>
Тип расписания:

- `dynamic`

- `guided`

- `runtime`

- `static`

## <a name="remarks"></a>Примечания

Значение по умолчанию в Visual C++ реализации стандарта OpenMP — `OMP_SCHEDULE=static,0`.

Дополнительные сведения см. в разделе [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).

## <a name="example"></a>Пример

Следующая команда задает **OMP_SCHEDULE** переменной среды:

```
set OMP_SCHEDULE="guided,2"
```

Следующая команда отображает текущее значение параметра **OMP_SCHEDULE** переменной среды:

```
set OMP_SCHEDULE
```

## <a name="see-also"></a>См. также

[Переменные среды](../../../parallel/openmp/reference/openmp-environment-variables.md)