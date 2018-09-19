---
title: Предупреждение компилятора (уровень 4) C4437 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11d234f7f264f051042ae99900875b8e570fa66a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118652"
---
# <a name="compiler-warning-level-4-c4437"></a>Предупреждение компилятора (уровень 4) C4437

приведение dynamic_cast из виртуального базового типа «class1» в «class2» может завершиться ошибкой в некоторых контекстах компиляции с/vd2 или определить «класс2» с помощью #pragma vtordisp(2), фактически

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Компилятор обнаружил `dynamic_cast` операции со следующими характеристиками.

- Приведение находится из указателя базового класса в производном классе указатель.

- Производный класс наследует практически базового класса.

- Производный класс не имеет `vtordisp` для виртуального базового.

- Приведение не найден в конструктор или деструктор производного класса, или какие-либо классы, который далее наследует от производного класса (в противном случае — Предупреждение компилятора выдачи C4436).

Предупреждение означает, что `dynamic_cast` может неправильно работать правильно при работе на частично сконструированным объектам.  Такая ситуация возникает при вызове внешней функции из конструктор или деструктор класса, который наследует производного класса, который называется в предупреждении.  Если производный класс, который называется в предупреждении никогда не дальнейших производным, или включающей функции не вызывается во время создания объекта или уничтожения, предупреждение можно игнорировать.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4437 и демонстрирует проблему создания кода, возникают из-за отсутствующих `vtordisp` поля.

```cpp
// C4437.cpp
// To see the warning and runtime assert, compile with: /W4
// To eliminate the warning and assert, compile with: /W4 /vd2
//       or compile with: /W4 /DFIX
#pragma warning(default : 4437)
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
        func();
    }

    void func()
    {
        A* a = static_cast<A*>(this);
        B* b = dynamic_cast<B*>(a);     // C4437
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
[Предупреждение компилятора (уровень 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)