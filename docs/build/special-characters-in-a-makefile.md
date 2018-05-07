---
title: Специальные символы в файле Makefile | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 157f9ed499ef7a0ac9efdd6bebe118ca593acabb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="special-characters-in-a-makefile"></a>Специальные символы в файле makefile
Чтобы использовать специальный знак NMAKE как буквенный символ, поместите знак вставки (^) перед ней. NMAKE игнорирует стрелки, которые предшествуют другие символы. Специальные символы — это:  
  
 `:  ;  #  (  )  $  ^  \  {  }  !  @  —`  
  
 Знак вставки (^) в строку в кавычках, обрабатывается как символ литерала. Курсор в конце строки вставляет символ новой строки в строку или макрос.  
  
 В макросах, обратную косую черту (\\) и с новой строки символы заменяются пробелом.  
  
 В командах символ процента (%) — это описатель файла. Чтобы представить % буквально в команде, укажите двойной знак процента (%) вместо одного. В других ситуациях NMAKE интерпретирует один %, буквально, но он всегда интерпретирует значение типа double %% как один объект %. Таким образом чтобы представить литерал %%, либо три знака процента, укажите %%%, либо четыре, %%%.  
  
 Чтобы использовать знак доллара ($) как буквенный символ в команде, укажите два знака доллара ($). Этот метод может также использоваться в других ситуациях, где ^ $ работает.  
  
## <a name="see-also"></a>См. также  
 [Содержимое файла Makefile](../build/contents-of-a-makefile.md)