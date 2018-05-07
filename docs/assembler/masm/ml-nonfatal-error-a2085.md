---
title: Некритичная ошибка ML A2085 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f0a014810679f0b48f79198b1335240f5cd6a8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="ml-nonfatal-error-a2085"></a>Некритичная ошибка ML A2085
**инструкция или регистрация, не принимается в текущем режиме ЦП**  
  
 Была предпринята попытка использовать инструкции, регистрации или ключевое слово, которое недопустимо для текущего режима процессора.  
  
 Например, требуется 32-разрядные регистры [.386](../../assembler/masm/dot-386.md) или более поздней версии. Регистрирует управления, такие как CR0 требуется привилегированный режим [.386P](../../assembler/masm/dot-386p.md) или более поздней версии. Эта ошибка может также возникать для **NEAR32**, **FAR32**, и **плоский** ключевые слова, которые требуют. **386** или более поздней версии.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)