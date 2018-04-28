---
title: Некритичная ошибка ML A2096 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2096
dev_langs:
- C++
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e5d07afa864c9f6f4214de953aa9e03fe0e7e4f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="ml-nonfatal-error-a2096"></a>Некритичная ошибка ML A2096
**Сегмент, группы или ожидается регистр**  
  
 Сегмент или группы ожидался, но не найден.  
  
 Произошло одно из следующих:  
  
-   Левый операнд, указанный с сегментом переопределить оператор (**:**) не сегмент регистра (CS, DS, SS, ES, FS или GS), имя группы, имя сегмента или выражение сегмента.  
  
-   [Предположим, ЧТО](../../assembler/masm/assume.md) директива передан сегмент регистра без адрес допустимым сегмента, регистр, группы или специальные **плоский** группы.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)