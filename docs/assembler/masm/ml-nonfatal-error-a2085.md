---
title: "Некритичная ошибка ML A2085 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2085
dev_langs: C++
helpviewer_keywords: A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d93ec58a7f55a2d875cc07dfbddff103b052f98c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ml-nonfatal-error-a2085"></a>Некритичная ошибка ML A2085
**инструкция или регистрация, не принимается в текущем режиме ЦП**  
  
 Была предпринята попытка использовать инструкции, регистрации или ключевое слово, которое недопустимо для текущего режима процессора.  
  
 Например, требуется 32-разрядные регистры [.386](../../assembler/masm/dot-386.md) или более поздней версии. Регистрирует управления, такие как CR0 требуется привилегированный режим [.386P](../../assembler/masm/dot-386p.md) или более поздней версии. Эта ошибка может также возникать для **NEAR32**, **FAR32**, и **плоский** ключевые слова, которые требуют. **386** или более поздней версии.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)