---
title: Некритичная ошибка ML A2008 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2008
dev_langs:
- C++
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50f7329f698d23f875a29bc316067c39e8d1b8c1
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055223"
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