---
title: 2.5.1 параллельные конструкция for | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfff3b0c17dd098b5d802af61a7ca1f81cb02845
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373965"
---
# <a name="251-parallel-for-construct"></a>2.5.1 Конструкция parallel for

**Параллельных для** директива является ярлыком для **параллельных** область, которая содержит только один **для** директива. Синтаксис **параллельных для** директива выглядит следующим образом:

```
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

Эта директива позволяет использовать все предложения из **параллельных** директивы и **для** директив, за исключением `nowait` предложение, идентичные значения и ограничения. Семантика идентична явно указав **параллельных** непосредственно предшествовать директива **для** директива.

## <a name="cross-references"></a>Перекрестные ссылки:

- **Параллельные** директив, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".

- **для** директив, см. в разделе [разделе 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) на стр. 11.

- Предложения атрибутов данных, см. в разделе [2.7.2 предложения атрибутов совместного использования данных](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на стр. 25.