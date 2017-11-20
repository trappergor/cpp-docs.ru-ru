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
ms.openlocfilehash: 0a71f69f141e92e7134d6048de67301198a667c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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