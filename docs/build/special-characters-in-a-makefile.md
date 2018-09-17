---
title: Специальные символы в файле Makefile | Документация Майкрософт
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
ms.openlocfilehash: 3ae77e769672dcc88a9dd41c901424c8c8150e6b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709368"
---
# <a name="special-characters-in-a-makefile"></a>Специальные символы в файле makefile

Чтобы использовать специальный знак NMAKE как буквенный символ, поместите знак вставки (^) перед ним. NMAKE игнорирует крышки, которые предшествуют другие символы. Специальные символы — это:

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

Знак вставки (^) в строку в кавычках рассматривается как символ литерала. Курсор в конце строки вставляет символ новой строки в строку или макрос.

В макросах, обратную косую черту (\\) за новой строкой символ заменяется пробелом.

В командах символ процента (%) — это описатель файла. Для представления % буквально в команде, укажите двойной знак процента (%) вместо одного. В других ситуациях NMAKE интерпретирует единый %, буквально, но он всегда интерпретирует значение типа double %% как единый объект %. Таким образом для представления литерала %%, укажите либо три знака процента, %%%, либо четыре, %%%.

Чтобы использовать знак доллара ($) как буквенный символ в команде, укажите два знака доллара ($). Этот метод также может использоваться в других ситуациях, где ^ $ работает.

## <a name="see-also"></a>См. также

[Содержимое файла Makefile](../build/contents-of-a-makefile.md)