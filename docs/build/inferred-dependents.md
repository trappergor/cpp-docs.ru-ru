---
title: Выводимые зависимости
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: 958a33c29be0d68fee1044fff1d81235ea9370c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641380"
---
# <a name="inferred-dependents"></a>Выводимые зависимости

Выводимая зависимость является производным от правило определения и вычисляется раньше, чем явные зависимые объекты. Если выводимая зависимость является устаревшей по отношению к цели, NMAKE вызывает блок команд для зависимости. Если выводимая зависимость не существует или является устаревшей по отношению к собственным зависимостям, NMAKE сначала обновляет эту зависимость. Дополнительные сведения о выводимые зависимости, см. в разделе [правила вывода](../build/inference-rules.md).

## <a name="see-also"></a>См. также

[Зависимые элементы](../build/dependents.md)