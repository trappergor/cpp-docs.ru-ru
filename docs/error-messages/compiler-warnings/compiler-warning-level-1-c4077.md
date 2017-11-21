---
title: "Предупреждение (уровень 1) C4077 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4077
dev_langs: C++
helpviewer_keywords: C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4d177d9d9bc5ce24e31b918b5651f2db1208b2c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4077"></a>Предупреждение компилятора (уровень 1) C4077
неизвестный параметр check_stack  
  
 Старая форма прагмы **check_stack** используется с неизвестным аргументом. Аргумент должен быть `+`, `-`, `(on)`, `(off)`или быть пустым.  
  
 Компилятор игнорирует эту прагму и оставляет проверку стека неизмененной.  
  
## <a name="example"></a>Пример  
  
```  
// C4077.cpp  
// compile with: /W1 /LD  
#pragma check_stack yes // C4077  
#pragma check_stack +    // Correct old form  
#pragma check_stack (on) // Correct new form  
```