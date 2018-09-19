---
title: Вывести зависимости и правила | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c13ae7784ff40b39642ce26fd062a1aab80f2d4c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707555"
---
# <a name="inferred-dependents-and-rules"></a>Выводимые зависимости и правила

NMAKE предполагает выводимую зависимость для целевого объекта, если существует применимое правило вывода. Правило применяется, если:

- *toext* соответствует расширению целевого объекта.

- *fromext* расширение файла, который имеет базовое имя целевого объекта и что существует в каталоге текущей или заданной совпадений.

- *fromext* в [. СУФФИКСЫ](../build/dot-directives.md); никакие другие *fromext* в соответствующее правило имеет более высокий **. СУФФИКСЫ** приоритет.

- Отсутствует явная зависимость с более высокой **. СУФФИКСЫ** приоритет.

Выводимые зависимости может вызвать непредвиденные побочные эффекты. Если блок описания целевого объекта команды, NMAKE выполняет эти команды вместо команды в правиле.

## <a name="see-also"></a>См. также

[Правила вывода](../build/inference-rules.md)