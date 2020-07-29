---
title: Предупреждение компилятора (уровень 1) C4436
ms.date: 11/04/2016
f1_keywords:
- C4436
helpviewer_keywords:
- C4436
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
ms.openlocfilehash: 6a15220cb02a48fb11936b69e5830412f1221108
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230679"
---
# <a name="compiler-warning-level-1-c4436"></a>Предупреждение компилятора (уровень 1) C4436

dynamic_cast из виртуального базового объекта "Class1" в "class2" в конструкторе или деструкторе может произойти сбой с частично сконструированным объектом Compiled with/vd2 или define "class2" с #pragma vtordisp (2) в силе

Компилятор обнаружил **`dynamic_cast`** операцию со следующими характеристиками.

- Приведение является указателем базового класса на указатель производного класса.

- Производный класс виртуально наследует базовый класс.

- Производный класс не имеет `vtordisp` поля для виртуального базового класса.

- Приведение находится в конструкторе или деструкторе производного класса или в каком-либо классе, который далее наследует от производного класса.

Предупреждение указывает, что **`dynamic_cast`** может выполняться неправильно, если он работает на частично сконструированном объекте.  Это происходит, если производный конструктор или деструктор работает над подобъектом какого-либо последующего производного объекта.  Если производный класс, указанный в предупреждении, никогда не является производным, это предупреждение можно пропустить.

## <a name="example"></a>Пример

В следующем примере создается C4436 и демонстрируется ошибка создания кода, которая возникает из отсутствующего `vtordisp` поля.

```cpp
// C4436.cpp
// To see the warning and runtime assert, compile with: /W1
// To eliminate the warning and assert, compile with: /W1 /vd2
//       or compile with: /W1 /DFIX
#include <cassert>

struct A
{
public:
    virtual ~A() {}
};

#if defined(FIX)
#pragma vtordisp(push, 2)
#endif
struct B : virtual A
{
    B()
    {
        A* a = static_cast<A*>(this);
        B* b = dynamic_cast<B*>(a);     // C4436
        assert(this == b);              // assert unless compiled with /vd2
    }
};
#if defined(FIX)
#pragma vtordisp(pop)
#endif

struct C : B
{
    int i;
};

int main()
{
    C c;
}
```

## <a name="see-also"></a>См. также раздел

[Оператор dynamic_cast](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[Предупреждение компилятора (уровень 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)
