---
title: Выводимые зависимости | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 631c5631b60f0e05dd1f1541facc767f35944d3d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701484"
---
# <a name="inferred-dependents"></a>Выводимые зависимости

Выводимая зависимость является производным от правило определения и вычисляется раньше, чем явные зависимые объекты. Если выводимая зависимость является устаревшей по отношению к цели, NMAKE вызывает блок команд для зависимости. Если выводимая зависимость не существует или является устаревшей по отношению к собственным зависимостям, NMAKE сначала обновляет эту зависимость. Дополнительные сведения о выводимые зависимости, см. в разделе [правила вывода](../build/inference-rules.md).

## <a name="see-also"></a>См. также

[Зависимые элементы](../build/dependents.md)