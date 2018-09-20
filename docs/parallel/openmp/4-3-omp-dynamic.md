---
title: 4.3 OMP_DYNAMIC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c15fa9d8c9d86b736bfc577a3b17e9809ec9baaf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439202"
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC

**OMP_DYNAMIC** переменной среды, включает или отключает динамическую настройку количество потоков, доступных для выполнения параллельных регионов, если только явным образом включен или отключен, вызвав динамическуюнастройку**omp_set_dynamic** подпрограмма библиотеки. Его значение должно быть **TRUE** или **FALSE**.

Если значение **TRUE**, число потоков, которые используются для выполнения параллельных регионов можно менять в среде, для наиболее эффективного использования системных ресурсов.  Если значение **FALSE**, динамическую настройку отключен. Условие по умолчанию определяется реализацией.

Пример

```
setenv OMP_DYNAMIC TRUE
```

## <a name="cross-references"></a>Перекрестные ссылки:

- Дополнительные сведения о параллельных регионов см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".

- **omp_set_dynamic** функции, см. в разделе [разделе 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на стр. 39.