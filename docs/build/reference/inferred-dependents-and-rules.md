---
title: Выводимые зависимости и правила
ms.date: 11/04/2016
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
ms.openlocfilehash: b9c3055db0cc173999e1737986166eb334dcf96c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827046"
---
# <a name="inferred-dependents-and-rules"></a>Выводимые зависимости и правила

NMAKE предполагает выводимую зависимость для целевого объекта, если существует применимое правило вывода. Правило применяется, если:

- *toext* соответствует расширению целевого объекта.

- *fromext* расширение файла, который имеет базовое имя целевого объекта и что существует в каталоге текущей или заданной совпадений.

- *fromext* в [. СУФФИКСЫ](dot-directives.md); никакие другие *fromext* в соответствующее правило имеет более высокий **. СУФФИКСЫ** приоритет.

- Отсутствует явная зависимость с более высокой **. СУФФИКСЫ** приоритет.

Выводимые зависимости может вызвать непредвиденные побочные эффекты. Если блок описания целевого объекта команды, NMAKE выполняет эти команды вместо команды в правиле.

## <a name="see-also"></a>См. также

[Правила вывода](inference-rules.md)
