---
title: "Выводимые зависимости | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eaf75c067b2e96e5ae4a893b56376bfc1b9bd1e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="inferred-dependents"></a>Выводимые зависимости
Выводимая зависимость создается правило определения и оценивается перед явными зависимостями. Если выводимая зависимость устарела по отношению к цели, NMAKE вызывает для этой зависимости блок команд. Если выводимая зависимость не существует или является устаревшей по отношению к собственным зависимостям, программа NMAKE сначала обновляет эту зависимость. Дополнительные сведения о выводимых зависимостях см. в разделе [правила вывода](../build/inference-rules.md).  
  
## <a name="see-also"></a>См. также  
 [Зависимые элементы](../build/dependents.md)