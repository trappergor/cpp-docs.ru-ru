---
title: Предупреждение компилятора (уровень 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 3f1b349599c77bc001911431fe0d83496ca3dfce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199411"
---
# <a name="compiler-warning-level-1-c4804"></a>Предупреждение компилятора (уровень 1) C4804

"операция": ненадежное использование типа "bool" в операции

Это предупреждение используется при непредвиденном использовании `bool` переменной или значения. Например, C4804 создается при использовании таких операторов, как отрицательный унарный оператор ( **-** ) или оператор дополнения (`~`). Компилятор вычисляет выражение.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4804:

```cpp
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```
