---
title: Ограничения обработчиков исключений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f739152b502a156dc62dfab279e5ad044cfff99
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения обработчиков исключений
Главное ограничение на использование обработчиков в коде состоит в том, что оператор `goto` не может использоваться для перехода в блок оператора `__try`. Входить в этот блок необходимо только через обычный поток управления. При желании вы можете переходить из блока оператора `__try`, а также создавать вложенные обработчики исключений.  
  
## <a name="see-also"></a>См. также  
 [Написание обработчика исключений](../cpp/writing-an-exception-handler.md)   
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)