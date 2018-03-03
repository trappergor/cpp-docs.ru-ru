---
title: "Сохраняемые регистры вызываемого объектов вызывающего объекта | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 61e8d57c177ded8102f257cf84adedc0de0e312a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="callercallee-saved-registers"></a>Сохраняемые регистры вызываемого и вызывающего объектов
Регистры RAX, RCX, RDX, R8, R9, R10, R11 считаются временными и должны уничтожаться при вызове функции (если в противном случае безопасность проверяемыми путем анализа как оптимизация всей программы).  
  
 Регистры RBX, RBP, RDI, RSI, RSP, R12, R13, R14 и R15 считаются энергонезависимого и необходимо сохранить и восстановить функцией, использует их.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)