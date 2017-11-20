---
title: "Некритичная ошибка ML A2008 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2008
dev_langs: C++
helpviewer_keywords: A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7bcef41e81ea0f3d6229cf828a661fdc8f8fdec4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ml-nonfatal-error-a2008"></a>Некритичная ошибка ML A2008
**Синтаксическая ошибка:**  
  
 Маркер в текущем положении является причиной синтаксической ошибки.  
  
 Мог произойти одно из следующих:  
  
-   Префикс точка был добавлен в или опущена директивы.  
  
-   Зарезервированные слова (такие как **C** или **размер**) использовать в качестве идентификатора.  
  
-   Инструкция была использована, недоступен с выделенной процессора или сопроцессора.  
  
-   Во время выполнения оператора сравнения (например, `==`) был использован в операторе условной сборки вместо оператор сравнения (такие как [EQ](../../assembler/masm/operator-eq.md)).  
  
-   Инструкции или директива указано слишком мало операндов.  
  
-   Использовался устаревший директиву.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)