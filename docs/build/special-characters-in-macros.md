---
title: "Специальные символы в макросах | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d954abc593fcba3887da4f7ee4bd5ce1e443e18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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