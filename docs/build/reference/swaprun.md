---
title: "-SWAPRUN | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /swaprun
dev_langs:
- C++
helpviewer_keywords:
- /SWAPRUN editbin option
- -SWAPRUN editbin option
- SWAPRUN editbin option
ms.assetid: 6eefd7f3-ca47-48e3-8509-323d27cf4ae7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 249ed999d9a60116875e88553863ef5cd234ade9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="swaprun"></a>/SWAPRUN
```  
/SWAPRUN:{[!]NET|[!]CD}  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр изменяет образ, чтобы операционная система для копирования образа в файл подкачки и запустить его оттуда. Используйте этот параметр для образов, находящихся в сети или на съемный носитель.  
  
 Можно добавить или удалить квалификаторы NET или компакт-диска:  
  
-   NET указывает, что образ находится в сети.  
  
-   Компакт-диска Указывает, что образ находится на компакт-диск или съемный носитель, аналогичные.  
  
-   Используйте! NET и! Для отмены действия квалификаторов NET и CD компакт-диска.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)