---
title: Приоритет правил вывода
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
ms.openlocfilehash: 99d92985b00f7c05f409b43009eb61cec6d6f1b1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413282"
---
# <a name="precedence-in-inference-rules"></a>Приоритет правил вывода

Если правило определения определен многократно, NMAKE использует определение самый высокий приоритет. Ниже показан порядок приоритетов от самого высокого до самого низкого:

1. Правило определения, определенное в файле makefile; приоритет имеют более поздние определения.

1. Правило определения, определенное в файле Tools.ini; приоритет имеют более поздние определения.

1. Предварительно определенное правило определения.

## <a name="see-also"></a>См. также

[Правила вывода](../build/inference-rules.md)
