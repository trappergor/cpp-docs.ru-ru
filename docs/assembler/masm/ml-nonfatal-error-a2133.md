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
ms.openlocfilehash: 343c2fae3d3c1fe97224e8fac990b29786e50cdf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ml-nonfatal-error-a2133"></a>Некритичная ошибка ML A2133
**перезаписываются INVOKE значение регистра**  
  
 Регистр была передана в качестве аргумента в процедуру, но код, созданный [INVOKE](../../assembler/masm/invoke.md) для передачи других аргументов уничтожения содержимое регистра.  
  
 Регистры AX, AL, AH, EAX, DX, DL Диффи-Хелмана и EDX может использоваться код на языке ассемблера, для выполнения преобразования данных.  
  
 Используйте другой регистр.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)