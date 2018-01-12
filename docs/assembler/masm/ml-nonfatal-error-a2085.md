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
ms.workload: cplusplus
ms.openlocfilehash: f987b775c13b0e477fd5c1d215d556069535a0fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2085"></a>Некритичная ошибка ML A2085
**инструкция или регистрация, не принимается в текущем режиме ЦП**  
  
 Была предпринята попытка использовать инструкции, регистрации или ключевое слово, которое недопустимо для текущего режима процессора.  
  
 Например, требуется 32-разрядные регистры [.386](../../assembler/masm/dot-386.md) или более поздней версии. Регистрирует управления, такие как CR0 требуется привилегированный режим [.386P](../../assembler/masm/dot-386p.md) или более поздней версии. Эта ошибка может также возникать для **NEAR32**, **FAR32**, и **плоский** ключевые слова, которые требуют. **386** или более поздней версии.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)