---
title: "Выводимые зависимости | Документы Microsoft"
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
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 410e52dd9ee9605f6e29b81491bda0f4883e1cf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="inferred-dependents"></a>Выводимые зависимости
Выводимая зависимость создается правило определения и оценивается перед явными зависимостями. Если выводимая зависимость устарела по отношению к цели, NMAKE вызывает для этой зависимости блок команд. Если выводимая зависимость не существует или является устаревшей по отношению к собственным зависимостям, программа NMAKE сначала обновляет эту зависимость. Дополнительные сведения о выводимых зависимостях см. в разделе [правила вывода](../build/inference-rules.md).  
  
## <a name="see-also"></a>См. также  
 [Зависимые элементы](../build/dependents.md)