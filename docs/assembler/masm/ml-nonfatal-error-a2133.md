---
title: "Некритичная ошибка ML A2133 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2133
dev_langs: C++
helpviewer_keywords: A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64619e6e14ce0268516c6c688c9a2bdeb5ea7a11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2133"></a>Некритичная ошибка ML A2133
**перезаписываются INVOKE значение регистра**  
  
 Регистр была передана в качестве аргумента в процедуру, но код, созданный [INVOKE](../../assembler/masm/invoke.md) для передачи других аргументов уничтожения содержимое регистра.  
  
 Регистры AX, AL, AH, EAX, DX, DL Диффи-Хелмана и EDX может использоваться код на языке ассемблера, для выполнения преобразования данных.  
  
 Используйте другой регистр.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)