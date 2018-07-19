---
title: Предупреждение (уровень 1) C4731 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4731
dev_langs:
- C++
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31bdf972ef3791760469251dc4d0bf19627bded2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283885"
---
# <a name="compiler-warning-level-1-c4731"></a>Предупреждение компилятора (уровень 1) C4731
«указатель»: «зарегистрироваться» изменен с помощью встроенного кода ассемблера регистр указателя фрейма  
  
 Регистр указателя фрейма был изменен. Необходимо сохранить и восстановить регистр во встроенной сборке блока или кадр переменная (локальные или параметра, в зависимости от измененного регистра), или код может работать неправильно.  
  
 Следующий пример приводит к возникновению ошибки C4731:  
  
```  
// C4731.cpp  
// compile with: /W1 /LD  
// processor: x86  
// C4731 expected  
void bad(int p) {  
   __asm  
   {  
      mov ebp, 1  
   }  
  
   if (p == 1)  
   {  
      // ...  
   }  
}  
```  
  
 EBP представляет собой указатель фрейма (FPO не допускается) и его изменения. Когда `p` позже ссылаться, он упоминается в связи с `EBP`. Но `EBP` перезаписана по коду, поэтому программа будет работать неправильно и даже может произойти сбой.