---
title: Приоритет правил вывода | Документы Microsoft
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
ms.openlocfilehash: 36d462d4222cbfc143dd7487d4cb6b1b8bb3ba3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368490"
---
# <a name="precedence-in-inference-rules"></a>Приоритет правил вывода
Если правило определения определяется многократно, NMAKE использует определение наивысшего приоритета. Следующий список показывает порядок приоритета от самого высокого до самого низкого:  
  
1.  Правило определения, определенное в файле makefile; приоритет имеют более поздние определения.  
  
2.  Правило определения, определенное в файле Tools.ini; приоритет имеют более поздние определения.  
  
3.  Предварительно определенное правило определения.  
  
## <a name="see-also"></a>См. также  
 [Правила вывода](../build/inference-rules.md)