---
title: Предупреждение компилятора (уровень 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: b55594608eccc5d1e5e764bffb73ecb3787af1e4
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541587"
---
# <a name="compiler-warning-level-4-c4130"></a>Предупреждение компилятора (уровень 4) C4130

"оператор": логическая операция с адресом строковой константы

Использование оператора с адресом строкового литерала создает непредвиденный код.

Следующий пример приводит к возникновению ошибки C4130:

```cpp
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