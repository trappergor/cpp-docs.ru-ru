---
title: 4.4 OMP_NESTED
ms.date: 11/04/2016
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
ms.openlocfilehash: e45b8901c56923ab37ca387a5f057c5b41af21f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453629"
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED

`OMP_NESTED` Переменной среды, включает или отключает вложенный параллелизм, если не включен или отключен, вызвав вложенный параллелизм `o` **mp_set_nested** подпрограмма библиотеки. Если значение **TRUE**, вложенные параллелизма включен; если он становится равным **FALSE**вложенного параллелизм отключен. Значение по умолчанию — **FALSE**.

Пример

```
setenv OMP_NESTED TRUE
```

## <a name="cross-reference"></a>Перекрестная ссылка:

- `omp_set_nested` функции, см. в разделе [разделе 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) на странице 40.