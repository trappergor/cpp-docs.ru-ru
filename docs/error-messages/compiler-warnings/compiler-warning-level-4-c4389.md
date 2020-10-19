---
title: Предупреждение компилятора (уровень 4) C4389
description: Предупреждение компилятора Microsoft C/C++ C4389, его причины и решение.
ms.date: 10/16/2020
f1_keywords:
- c4389
helpviewer_keywords:
- C4389
ms.openlocfilehash: b06b013151ed12b4f66bb23a7e862992d05e6b30
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176260"
---
# <a name="compiler-warning-level-4-c4389"></a>Предупреждение компилятора (уровень 4) C4389

> "*Equality-оператор*": несоответствие знаков со знаком и без знака

**`==`** **`!=`** Вовлеченная операция OR **`signed`** и **`unsigned`** переменные. Это может привести к утрате данных.

## <a name="remarks"></a>Remarks

Одним из способов устранения этого предупреждения является попытка приведения одного из двух типов при сравнении **`signed`** **`unsigned`** типов и.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4389:

```cpp
// C4389.cpp
// compile with: cl /EHsc /W4 C4389.cpp

int main()
{
   int a = 9;
   unsigned int b = 10;
   int result = 0;

   if (a == b)   // C4389
      result = 1;
   else
      result = 2;

   if (unsigned(a) == b) // OK
      result = 3;
   else
      result = 4;

   return result;
}
```

## <a name="see-also"></a>См. также раздел

[Предупреждение компилятора C4018](compiler-warning-level-3-c4018.md)\
[Предупреждение компилятора (уровень 4) C4388](c4388.md)
