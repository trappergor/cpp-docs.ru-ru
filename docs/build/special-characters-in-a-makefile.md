---
title: "Специальные символы в файле Makefile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6c574040d6004516682379a5e64b87c1b92388ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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