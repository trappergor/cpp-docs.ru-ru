---
title: "Предупреждение (уровень 1) C4077 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4077
dev_langs:
- C++
helpviewer_keywords:
- C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 000301a51098faff00210f323f522e35280418b8
ms.lasthandoff: 04/12/2017

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
