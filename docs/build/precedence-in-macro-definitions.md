---
title: Приоритет в макроопределениях | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce6f0acc898dc719d2252d5cc59dff92bda4a98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368617"
---
# <a name="precedence-in-macro-definitions"></a>Приоритет в макроопределениях
Если макрос имеет несколько определений, NMAKE использует определение наивысшего приоритета. Ниже перечислены порядок приоритета от наибольшего к наименьшему.  
  
1.  Макрос, определенный в командной строке  
  
2.  Макрос, определенный в файле makefile или включаемого файла  
  
3.  Наследуемый макрос переменной среды  
  
4.  Макрос, определенный в файле Tools.ini  
  
5.  Предопределенный макрос, таких как [CC](../build/command-macros-and-options-macros.md) и [AS](../build/command-macros-and-options-macros.md)  
  
 Используйте /E макросы, унаследованные от переменных среды для переопределения makefile макросов с тем же именем. Используйте **! UNDEF** для переопределения командной строки.  
  
## <a name="see-also"></a>См. также  
 [Определение макроса NMAKE](../build/defining-an-nmake-macro.md)