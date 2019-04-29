---
title: Выводимые зависимости
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: 2382dec960ef93fc2f73987ad27b4670768a68cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291539"
---
# <a name="inferred-dependents"></a>Выводимые зависимости

Выводимая зависимость является производным от правило определения и вычисляется раньше, чем явные зависимые объекты. Если выводимая зависимость является устаревшей по отношению к цели, NMAKE вызывает блок команд для зависимости. Если выводимая зависимость не существует или является устаревшей по отношению к собственным зависимостям, NMAKE сначала обновляет эту зависимость. Дополнительные сведения о выводимые зависимости, см. в разделе [правила вывода](inference-rules.md).

## <a name="see-also"></a>См. также

[Зависимые элементы](dependents.md)
