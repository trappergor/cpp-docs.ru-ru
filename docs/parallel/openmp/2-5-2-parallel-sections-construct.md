---
title: 2.5.2 Конструкция parallel sections
ms.date: 11/04/2016
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
ms.openlocfilehash: 1b74dacb9730a14364d7202918ae195cbf691955
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533670"
---
# <a name="252-parallel-sections-construct"></a>2.5.2 Конструкция parallel sections

**Параллельных разделах** директива предоставляет форму ярлык для указания **параллельных** содержит только один регион **разделах** директива. Семантика идентична явно указав **параллельных** непосредственно предшествовать директива **разделах** директива. Синтаксис **параллельных разделах** директива выглядит следующим образом:

```
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

*Предложение* может принимать одно из предложений, принимаемое **параллельных** и **разделах** директивы, за исключением **nowait** предложение.

## <a name="cross-references"></a>Перекрестные ссылки:

- **Параллельные** директив, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".

- **разделы** директив, см. в разделе [разделе 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) на стр.