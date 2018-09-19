---
title: Предупреждение компилятора (уровень 1) C4731 | Документация Майкрософт
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
ms.openlocfilehash: 75117b34e63694cfa6aeec97abf178ff8e61a7da
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086490"
---
# <a name="compiler-warning-level-1-c4731"></a>Предупреждение компилятора (уровень 1) C4731

«указатель»: «регистр» изменен встроенный код ассемблера регистр указателя фрейма

Регистр указателя фрейма был изменен. Необходимо сохранить и восстановить регистр во встроенной сборки блока или фрейм переменной (локальной или параметра, в зависимости от измененного регистра), или ваш код может не работать должным образом.

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

EBP — это указатель фрейма (FPO не допускается) и выполняется его изменение. Когда `p` наступает позже, ссылка на, он указывается относительно `EBP`. Но `EBP` был переопределен в коде, поэтому программа будет работать неправильно и даже может произойти сбой.