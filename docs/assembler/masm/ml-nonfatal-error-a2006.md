---
title: "Некритичная ошибка ML A2006 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2006
dev_langs: C++
helpviewer_keywords: A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c27f859f7841bb1b64fadd2f7051b9e0647f0b15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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