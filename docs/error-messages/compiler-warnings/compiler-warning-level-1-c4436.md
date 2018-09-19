---
title: Предупреждение компилятора (уровень 1) C4436 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2484b5420347f49a74d8eb3cdf65a8221741cc63
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076506"
---
# <a name="compiler-warning-level-1-c4436"></a>Предупреждение компилятора (уровень 1) C4436

приведение dynamic_cast из виртуального базового типа «class1» в «class2» в конструктор или деструктор может завершить работу с частично сконструированного объекта компиляции с/vd2 или определите «класс2» с помощью #pragma vtordisp(2) фактически

Компилятор обнаружил `dynamic_cast` операции со следующими характеристиками.

- Приведение находится из указателя базового класса в производном классе указатель.

- Производный класс наследует практически базового класса.

- Производный класс не имеет `vtordisp` для виртуального базового.

- Приведения параметра в конструктор или деструктор производного класса, или какие-либо классы, который далее наследует из производного класса.

Предупреждение указывает `dynamic_cast` может неправильно работать правильно, если он работает на частично сконструированным объектам.  Это происходит, если производного конструктора или деструктора работает на дочерний объект некоторых производных объектов.  Если производный класс с именем в предупреждении никогда не дальнейших производных, предупреждение можно игнорировать.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4436 и демонстрирует проблему создания кода, возникают из-за отсутствующих `vtordisp` поля.

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

## <a name="see-also"></a>См. также

[Оператор dynamic_cast](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[Предупреждение компилятора (уровень 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)