---
title: "Приоритет правил вывода | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7374da0541fc66464947af5a7b2ea7ea7b5c1d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-inference-rules"></a>Приоритет правил вывода
Если правило определения определяется многократно, NMAKE использует определение наивысшего приоритета. Следующий список показывает порядок приоритета от самого высокого до самого низкого:  
  
1.  Правило определения, определенное в файле makefile; приоритет имеют более поздние определения.  
  
2.  Правило определения, определенное в файле Tools.ini; приоритет имеют более поздние определения.  
  
3.  Предварительно определенное правило определения.  
  
## <a name="see-also"></a>См. также  
 [Правила вывода](../build/inference-rules.md)