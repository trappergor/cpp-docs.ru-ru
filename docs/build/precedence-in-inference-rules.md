---
title: Приоритет правил вывода
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: 30dee54c99115c076f7662bafb8aa22d97f234fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548737"
---
# <a name="precedence-in-inference-rules"></a>Приоритет правил вывода

Если правило определения определен многократно, NMAKE использует определение самый высокий приоритет. Ниже показан порядок приоритетов от самого высокого до самого низкого:

1. Правило определения, определенное в файле makefile; приоритет имеют более поздние определения.

1. Правило определения, определенное в файле Tools.ini; приоритет имеют более поздние определения.

1. Предварительно определенное правило определения.

## <a name="see-also"></a>См. также

[Правила вывода](../build/inference-rules.md)