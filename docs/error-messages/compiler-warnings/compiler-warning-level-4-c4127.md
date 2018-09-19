---
title: Предупреждение компилятора (уровень 4) C4127 | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 561173e2b451a0b736d97042667a2fb14b3a7eb7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094901"
---
# <a name="compiler-warning-level-4-c4127"></a>Предупреждение компилятора (уровень 4) C4127

> условное выражение является константой

## <a name="remarks"></a>Примечания

Управляющее выражение оператора `if` или цикла `while` является константой. Из-за их идиоматичной повсеместно, начиная с Visual Studio 2015 с обновлением 3, тривиальные константы, например 1 или `true` срабатывание предупреждения, если только они получены в результате операции в выражении.

Если управляющее выражение оператора `while` цикла является константой, так как выход из цикла в середине, рассмотрите возможность замены `while` цикл `for` цикла. Можно опустить инициализацию, проверку завершения и шаг приращения цикла `for` цикле, что приводит к циклу неограниченное так же, как `while(1)`, и вы можете выйти из цикла из тела `for` инструкции.

## <a name="example"></a>Пример

В следующем примере показано два способа C4127 создается и показано, как использовать цикл предотвратить появление предупреждения:

```cpp
// C4127.cpp
// compile with: /W4
#include <stdio.h>
int main() {
   if (true) {}           // OK in VS2015 update 3 and later
   if (1 == 1) {}         // C4127
   while (42) { break; }  // C4127

   // OK
   for ( ; ; ) {
      printf("test\n");
      break;
   }
}
```