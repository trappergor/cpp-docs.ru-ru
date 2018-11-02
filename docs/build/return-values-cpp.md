---
title: Возвращаемые значения (C++)
ms.date: 11/04/2016
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
ms.openlocfilehash: 047058a18597384a3da47d1c22874c7a297f1a48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463575"
---
# <a name="return-values-c"></a>Возвращаемые значения (C++)

Скалярное возвращаемое значение не больше 64 битов возвращается посредством RAX (сюда входят типы __m64). Нескалярные типы, включая типы с плавающей точкой, тип Double и векторные типы, такие как [__m128](../cpp/m128.md), [__m128i](../cpp/m128i.md), [__m128d](../cpp/m128d.md) , возвращаются в XMM0. Состояние неиспользуемых битов в возвращаемом значении в RAX или XMM0 не определяется.

Определенные пользователем типы можно вернуть из глобальных функций и статических функций-членов по значению. Для возврата в RAX по значению длина определенных пользователем типов должна быть 1, 2, 4, 8, 16, 32 или 64 бита; типы должны быть без определенного пользователем конструктора, деструктора или оператора назначения копирования; без частных или защищенных нестатических данных-членов; без нестатических данных-членов ссылочного типа; без базовых классов; без виртуальных функций и без данных-членов, которые также не соответствуют этим требованиям. (Фактически это — определение типа C ++ 03 POD. Поскольку определение изменилось в стандарте C ++ 11, не рекомендуется использовать `std::is_pod` для этого теста.) В противном случае вызывающий объект берет на себя ответственность за выделение памяти и передачу указателя для возвращаемого значения в качестве первого аргумента. Последующие аргументы затем перемещаются на один аргумент вправо. Тот же указатель должен быть возвращен вызываемой стороной в RAX.

В приведенных ниже примерах показан способ передачи параметров и возвращаемых значений для функций с указанными объявлениями.

## <a name="example-of-return-value-1---64-bit-result"></a>Пример возвращаемого значения 1 – 64 бит результат

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

## <a name="example-of-return-value-2---128-bit-result"></a>Пример возвращаемого значения результат 2 128 бит

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

## <a name="example-of-return-value-3---user-type-result-by-pointer"></a>Пример возвращаемого значения 3 — результат пользовательского типа по указатель

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

## <a name="example-of-return-value-4---user-type-result-by-value"></a>Пример возвращаемого значения 4 — результат пользовательского типа по значению

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="see-also"></a>См. также

[Соглашение о вызовах](../build/calling-convention.md)