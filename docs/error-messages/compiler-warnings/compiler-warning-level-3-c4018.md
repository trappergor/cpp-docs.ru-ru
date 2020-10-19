---
title: Предупреждение компилятора (уровень 3) C4018
description: Предупреждение компилятора Microsoft C/C++ C4018, его причины и решение.
ms.date: 10/16/2020
f1_keywords:
- C4018
helpviewer_keywords:
- C4018
ms.openlocfilehash: b9d01f6b733c2ca18880aa6f4b6fca9771f8123f
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176169"
---
# <a name="compiler-warning-level-3-c4018"></a>Предупреждение компилятора (уровень 3) C4018

> "*токен*": несоответствие со знаком и без знака

Использование оператора *Token* для сравнения **`signed`** и **`unsigned`** чисел требует, чтобы компилятор преобразует **`signed`** значение в **`unsigned`** .

## <a name="remarks"></a>Remarks

Одним из способов устранения этого предупреждения является попытка приведения одного из двух типов при сравнении **`signed`** **`unsigned`** типов и.

## <a name="example"></a>Пример

В этом примере создается C4018 и демонстрируется его устранение:

```cpp
// C4018.cpp
// compile with: cl /EHsc /W4 C4018.cpp
int main() {
    unsigned int uc = 0;
    int c = 0;
    unsigned int c2 = c; // implicit conversion

    if (uc < c)           // C4018
        uc = 0;

    if (uc < unsigned(c)) // OK
        uc = 0;

    if (uc < c2)          // Also OK
       uc = 0;
}
```

## <a name="see-also"></a>См. также раздел

[Предупреждение компилятора (уровень 4) C4388](c4388.md)\
[Предупреждение компилятора (уровень 4) C4389](compiler-warning-level-4-c4389.md)
