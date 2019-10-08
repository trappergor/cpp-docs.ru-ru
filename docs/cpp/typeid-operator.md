---
title: Оператор typeid
ms.date: 10/04/2019
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
ms.openlocfilehash: 93a2d3c494cd5aadafedcaaae9ec72809d633a4a
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998747"
---
# <a name="typeid-operator"></a>Оператор typeid

## <a name="syntax"></a>Синтаксис

```
typeid(type-id)
typeid(expression)
```

## <a name="remarks"></a>Примечания

Оператор **typeid** позволяет определить тип объекта во время выполнения.

Результатом **typeid** является `const type_info&`. Значение является ссылкой на объект `type_info`, представляющий либо *тип-ID* , либо тип *выражения*в зависимости от используемой формы **typeid** . Дополнительные сведения см. в разделе [класс type_info](../cpp/type-info-class.md).

Оператор **typeid** не работает с управляемыми типами (абстрактными деклараторами или экземплярами). Сведения о получении <xref:System.Type> указанного типа см. в разделе [typeid](../extensions/typeid-cpp-component-extensions.md).

Оператор **typeid** выполняет проверку во время выполнения при применении к l-значению типа полиморфизма, где истинный тип объекта не может быть определен с помощью предоставленной статической информации. К таким случаям относятся следующие.

- Ссылка на класс

- Указатель, разыменование с `*`

- Указатель в индексе (`[ ]`). (Нельзя использовать индекс с указателем на полиморфизм типа.)

Если *выражение* указывает на тип базового класса, но объект на самом деле является типом, производным от этого базового класса, то в результате возвращается `type_info` ссылка на производный класс. *Выражение* должно указывать на полиморфизм типа (класс с виртуальными функциями). В противном случае результатом является `type_info` для статического класса, на который ссылается *выражение*. Кроме того, указатель должен быть разыменован таким образом, чтобы использовался объект, на который он указывает. Без разыменования указателя результатом будет `type_info` для указателя, а не то, на что он указывает. Пример:

```cpp
// expre_typeid_Operator.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <typeinfo>

class Base {
public:
   virtual void vvfunc() {}
};

class Derived : public Base {};

using namespace std;
int main() {
   Derived* pd = new Derived;
   Base* pb = pd;
   cout << typeid( pb ).name() << endl;   //prints "class Base *"
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"
   delete pd;
}
```

Если *выражение* ссылается на указатель и значение этого указателя равно нулю, **typeid** вызывает [исключение bad_typeid](../cpp/bad-typeid-exception.md). Если указатель не указывает на допустимый объект, возникает исключение `__non_rtti_object`. Указывает, что попытка анализа RTTI, вызвавшего ошибку, вызвана тем, что объект является каким-то недопустимым. (Например, это неверный указатель, или код не был скомпилирован с помощью [/GR](../build/reference/gr-enable-run-time-type-information.md)).

Если *выражение* не является указателем, а не ссылкой на базовый класс объекта, результатом является ссылка `type_info`, представляющая статический тип *выражения*. *Статический тип* выражения ссылается на тип выражения, так как он известен во время компиляции. Семантика исполнения игнорируется при оценке статического типа выражения. Кроме того, ссылки по возможности игнорируются при определении статического типа выражения:

```cpp
// expre_typeid_Operator_2.cpp
#include <typeinfo>

int main()
{
   typeid(int) == typeid(int&); // evaluates to true
}
```

**typeid** можно также использовать в шаблонах для определения типа параметра шаблона:

```cpp
// expre_typeid_Operator_3.cpp
// compile with: /c
#include <typeinfo>
template < typename T >
T max( T arg1, T arg2 ) {
   cout << typeid( T ).name() << "s compared." << endl;
   return ( arg1 > arg2 ? arg1 : arg2 );
}
```

## <a name="see-also"></a>См. также

[Сведения о типах среды выполнения](../cpp/run-time-type-information.md)\
[Ключевые слова](../cpp/keywords-cpp.md)
