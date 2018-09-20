---
title: 2.5.2 конструкция parallel sections | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 073d0561fe4bfbb96ed88681a077da6fc985c963
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402334"
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