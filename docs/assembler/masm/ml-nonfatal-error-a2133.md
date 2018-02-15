---
title: "Некритичная ошибка ML A2133 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adc1929f14b5264717936f1a4aebb8dabd2e439d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ml-nonfatal-error-a2133"></a>Некритичная ошибка ML A2133
**перезаписываются INVOKE значение регистра**  
  
 Регистр была передана в качестве аргумента в процедуру, но код, созданный [INVOKE](../../assembler/masm/invoke.md) для передачи других аргументов уничтожения содержимое регистра.  
  
 Регистры AX, AL, AH, EAX, DX, DL Диффи-Хелмана и EDX может использоваться код на языке ассемблера, для выполнения преобразования данных.  
  
 Используйте другой регистр.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)