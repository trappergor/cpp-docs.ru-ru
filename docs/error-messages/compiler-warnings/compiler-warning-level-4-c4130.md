---
title: Предупреждение компилятора (уровень 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: 1b1fb72d68309a4bef56ccd844ad30d967bbadbd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552949"
---
# <a name="compiler-warning-level-4-c4130"></a>Предупреждение компилятора (уровень 4) C4130

"оператор": логическая операция с адресом строковой константы

Использование оператора с адресом строкового литерала создает непредвиденный код.

Следующий пример приводит к возникновению ошибки C4130:

```
// C4130.cpp
// compile with: /W4
int main()
{
   char *pc;
   pc = "Hello";
   if (pc == "Hello") // C4130
   {
   }
}
```

Оператор **if** сравнивает значение, сохраненное в указателе `pc` на адрес строки "Hello", который выделяется отдельно каждый раз, когда строка встречается в коде. Оператор **if** не сравнивает строку, на которую указывает `pc` , со строкой "Hello".

Для сравнения строк используйте функцию `strcmp` .