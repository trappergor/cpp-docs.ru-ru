---
title: Некритичная ошибка ML A2133 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f240ed6f2e8330017e56334dfcc41be478537c7b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="ml-nonfatal-error-a2133"></a>Некритичная ошибка ML A2133
**перезаписываются INVOKE значение регистра**  
  
 Регистр была передана в качестве аргумента в процедуру, но код, созданный [INVOKE](../../assembler/masm/invoke.md) для передачи других аргументов уничтожения содержимое регистра.  
  
 Регистры AX, AL, AH, EAX, DX, DL Диффи-Хелмана и EDX может использоваться код на языке ассемблера, для выполнения преобразования данных.  
  
 Используйте другой регистр.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)