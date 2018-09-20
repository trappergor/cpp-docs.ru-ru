---
title: 4.4 OMP_NESTED | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1083269f31ebc710da24430635ff8381e3f2147a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419520"
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED

`OMP_NESTED` Переменной среды, включает или отключает вложенный параллелизм, если не включен или отключен, вызвав вложенный параллелизм `o` **mp_set_nested** подпрограмма библиотеки. Если значение **TRUE**, вложенные параллелизма включен; если он становится равным **FALSE**вложенного параллелизм отключен. Значение по умолчанию — **FALSE**.

Пример

```
setenv OMP_NESTED TRUE
```

## <a name="cross-reference"></a>Перекрестная ссылка:

- `omp_set_nested` функции, см. в разделе [разделе 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) на странице 40.