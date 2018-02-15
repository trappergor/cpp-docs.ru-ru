---
title: "Некритичная ошибка ML A2006 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A2006
dev_langs:
- C++
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d758e612d9e072084498b55e4e8b700748af881f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2006"></a>Некритичная ошибка ML A2006
**Неопределенный символ: идентификатор**  
  
 Была предпринята попытка использовать символ, который не был определен.  
  
 Мог произойти одно из следующих:  
  
-   Символ не был определен.  
  
-   Поле не является членом указанной структуры.  
  
-   Символ был определен во включаемом файле, который не был включен.  
  
-   Внешний символ был использован без [EXTERN](../../assembler/masm/extern-masm.md) или [EXTERNDEF](../../assembler/masm/externdef.md) директивы.  
  
-   Была неправильно указано имя символа.  
  
-   Ссылка на метку локальный код вне ее области действия.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)