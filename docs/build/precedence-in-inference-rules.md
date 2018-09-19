---
title: Приоритет правил вывода | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4f2e7ff55e935b7e425b552ba85f47f134c6b80
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725235"
---
# <a name="precedence-in-inference-rules"></a>Приоритет правил вывода

Если правило определения определен многократно, NMAKE использует определение самый высокий приоритет. Ниже показан порядок приоритетов от самого высокого до самого низкого:

1. Правило определения, определенное в файле makefile; приоритет имеют более поздние определения.

1. Правило определения, определенное в файле Tools.ini; приоритет имеют более поздние определения.

1. Предварительно определенное правило определения.

## <a name="see-also"></a>См. также

[Правила вывода](../build/inference-rules.md)