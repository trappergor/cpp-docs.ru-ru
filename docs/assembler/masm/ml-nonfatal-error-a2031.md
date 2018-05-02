---
title: Некритичная ошибка ML A2031 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2031
dev_langs:
- C++
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4ab35776944604f3133254532d2631460c755983
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="ml-nonfatal-error-a2031"></a>Некритичная ошибка ML A2031
**должен быть индекс или базового регистра**  
  
 Была предпринята попытка использовать регистр, который не был базовым или индексным регистром в выражении памяти.  
  
 Например следующее выражение вызывает эту ошибку.  
  
```  
[ax]  
[bl]  
```  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)