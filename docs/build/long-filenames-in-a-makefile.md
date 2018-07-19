---
title: Длинные имена файлов в Makefile | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, long filenames
- long filenames
ms.assetid: 626d56fc-8879-46ba-9c2d-dd386c78cccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc199289f80e6ce2f9dbc5317ee439af528a055b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367632"
---
# <a name="long-filenames-in-a-makefile"></a>Длинные имена файлов в makefile
Заключите длинные имена файлов в двойные кавычки, следующим образом:  
  
```  
all : "VeryLongFileName.exe"  
```  
  
## <a name="see-also"></a>См. также  
 [Содержимое файла Makefile](../build/contents-of-a-makefile.md)