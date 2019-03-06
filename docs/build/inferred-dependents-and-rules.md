---
title: Выводимые зависимости и правила
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: 125d64c47fb8ac9cd86269bedf246a131eda57e7
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414847"
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
