---
title: Специальные символы в макросах | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c271d2f39a4d81776c06a107616170192e82d40d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380177"
---
# <a name="special-characters-in-macros"></a>Специальные символы в макросах
Знак номера (#), после определения служит комментарий. Для указания знака литерал в макрос, используйте знак вставки (^), как и в ^ #.  
  
 Знак доллара ($) служит для вызова макросов. Чтобы указать литерал $, используйте $$.  
  
 Чтобы расширить определение на новую строку, завершение строки обратную косую черту (\\). При вызове макроса символ обратной косой черты и новой строки заменяется пробелом. Чтобы указать обратную косую черту в конце строки, поместите перед ней знак вставки (^) или после него описатель комментария (#).  
  
 Чтобы указать знак новой строки, заканчиваются строку с знак вставки (^), как:  
  
```  
CMDS = cls^  
dir  
```  
  
## <a name="see-also"></a>См. также  
 [Определение макроса NMAKE](../build/defining-an-nmake-macro.md)