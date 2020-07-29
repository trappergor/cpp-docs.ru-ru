---
title: Предупреждение компилятора (уровень 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: 7b2fbccfd3b124220d6e310c01adace1d3e112c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219967"
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

**`if`** Оператор сравнивает значение, хранящееся в указателе `pc` , с адресом строки "Hello", которая выделяется отдельно при каждом возникновении строки в коде. **`if`** Инструкция не сравнивает строку, на которую указывает, `pc` со строкой "Hello".

Для сравнения строк используйте функцию `strcmp` .
