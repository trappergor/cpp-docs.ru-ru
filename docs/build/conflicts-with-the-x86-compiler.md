---
title: "Конфликтует с x86 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b2b9c4cf871e8436a8da34a862d205541e7dc5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="conflicts-with-the-x86-compiler"></a>Конфликты с компилятором x86
Типы данных, размер которых больше, чем 4 байта не выровнены автоматически в стеке при использовать x86 компилятора для компиляции приложения. Поскольку архитектура x86 компилятора является выровненных стека размером 4 байта, что-либо больше, чем 4 байта, например, 64-разрядное целое число, не может автоматически выравниваться по 8 байтам адреса.  
  
 Работа с данными без выравнивания имеет два ограничения.  
  
-   Он может занять больше времени для доступа к Невыровненные расположения, чем требуется для доступа к выровненные расположениям.  
  
-   Невыровненные расположения не может использоваться в блокируемые операции.  
  
 Если требуется более строгая выравнивание используйте `__declspec(align(N)) on your variable declarations`. Это заставляет компилятор динамически выравнивать стек в соответствии с требованиями. Тем не менее динамическому изменению стека во время выполнения может привести к более медленному выполнению приложения.  
  
## <a name="see-also"></a>См. также  
 [Типы и хранилище](../build/types-and-storage.md)   
 [align](../cpp/align-cpp.md)