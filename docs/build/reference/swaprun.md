---
title: -SWAPRUN | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /swaprun
dev_langs:
- C++
helpviewer_keywords:
- /SWAPRUN editbin option
- -SWAPRUN editbin option
- SWAPRUN editbin option
ms.assetid: 6eefd7f3-ca47-48e3-8509-323d27cf4ae7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6e8af5b23d2e6cd0759f75c4054e0a811f687e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375052"
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