---
title: Сохраняемые регистры вызываемого объектов вызывающего объекта | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f65e88c8609d6a2097e9e54c3f52cbd27dce36d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="callercallee-saved-registers"></a>Сохраняемые регистры вызываемого и вызывающего объектов
Регистры RAX, RCX, RDX, R8, R9, R10, R11 считаются временными и должны уничтожаться при вызове функции (если в противном случае безопасность проверяемыми путем анализа как оптимизация всей программы).  
  
 Регистры RBX, RBP, RDI, RSI, RSP, R12, R13, R14 и R15 считаются энергонезависимого и необходимо сохранить и восстановить функцией, использует их.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)