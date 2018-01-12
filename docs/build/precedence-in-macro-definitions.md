---
title: "Приоритет в макроопределениях | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7421ef51c37e3724bdb986321581e6736a62e18b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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