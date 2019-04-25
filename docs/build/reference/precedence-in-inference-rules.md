---
title: Приоритет правил вывода
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: ca24134fd1829ad3d97ca67b8c30aae3af4109ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319685"
---
# <a name="precedence-in-inference-rules"></a>Приоритет правил вывода

Если правило определения определен многократно, NMAKE использует определение самый высокий приоритет. Ниже показан порядок приоритетов от самого высокого до самого низкого:

1. Правило определения, определенное в файле makefile; приоритет имеют более поздние определения.

1. Правило определения, определенное в файле Tools.ini; приоритет имеют более поздние определения.

1. Предварительно определенное правило определения.

## <a name="see-also"></a>См. также

[Правила вывода](inference-rules.md)
