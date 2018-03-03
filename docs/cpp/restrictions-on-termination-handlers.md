---
title: "Ограничения обработчиков завершения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 71486b167f4e9939d4913b3660ed3513dc02b8f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="restrictions-on-termination-handlers"></a>Ограничения обработчиков завершения
Невозможно использовать инструкцию `goto` для входа в блок инструкций `__try` или `__finally`. Входить в этот блок необходимо только через обычный поток управления. (Впрочем, можно выйти из блока инструкций `__try`). Кроме того, невозможно вложить обработчик исключений или обработчик завершения в блок `__finally`.  
  
 Кроме того, некоторые типы кода, разрешенные в обработчике завершения, дают спорные результаты, поэтому их следует либо не использовать вообще, либо использовать с осторожностью. Один из них — инструкция `goto`, выполняющая выход из блока инструкций `__finally`. Если блок выполняется как часть нормального завершения, ничего необычного не происходит. Однако если система разматывает стек, эта операция останавливается, и текущая функция получает контроль над происходящим, как если бы аномального завершения не было.  
  
 Инструкция `return` внутри блока инструкций `__finally`, по сути, представляет такую же ситуацию. Контроль возвращается непосредственному вызывающему объекту функции, которая содержит обработчик завершения. Если система разматывала стек, этот процесс останавливается, и программа выполняется, как если бы исключения не было создано.  
  
## <a name="see-also"></a>См. также  
 [Написание обработчика завершения](../cpp/writing-a-termination-handler.md)   
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)