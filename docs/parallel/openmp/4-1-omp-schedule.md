---
title: 4.1 OMP_SCHEDULE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cbdad5ab56ea6979ae2b5952b092b5e85c7bdfa8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433456"
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE

**OMP_SCHEDULE** применяется только к **для** и **параллельных для** директивы, которые имеют тип расписания **среды выполнения**. Размер типа и блока расписание для таких циклов можно задать во время выполнения, задав переменную среды для любого типа распознается расписание и необязательный *chunk_size*.

Для **для** и **параллельных для** директивы, которые имеют тип расписания не **среды выполнения**, **OMP_SCHEDULE** учитывается. Значение по умолчанию для этой переменной среды определяется реализацией. Если необязательный *chunk_size* имеет значение, значение должно быть положительным. Если *chunk_size* не задано, предполагается, что значение 1, в частности, за исключением **статический** расписание. Для **статический** расписание, размер блока по умолчанию присваивается пространство итерации цикла, деленное на количество потоков, которые применены к циклу.

Пример

```
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

## <a name="cross-references"></a>Перекрестные ссылки:

- **для** директив, см. в разделе [разделе 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) на стр. 11.

- **Параллельные для** директив, см. в разделе [разделе 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) стр.