---
title: 3.1.8 функция omp_get_dynamic | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c30f49eaf91353d6a7cd9bd26e0e10e95cb6acd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426787"
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 Функция omp_get_dynamic

**Omp_get_dynamic** функция возвращает ненулевое значение, если динамическую настройку потоков и в противном случае возвращает 0. Он следующий:

```
#include <omp.h>
int omp_get_dynamic(void);
```

Если реализация не использует динамическую настройку число потоков, эта функция всегда возвращает 0.

## <a name="cross-references"></a>Перекрестные ссылки:

- Описание динамического потока коррекции, см. в разделе [разделе 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на стр. 39.