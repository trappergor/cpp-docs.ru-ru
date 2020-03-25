---
title: Разрешение имен зависимых типов
ms.date: 11/04/2016
ms.assetid: 34066bb4-0c79-4fd8-bda7-539a60a277ab
ms.openlocfilehash: e9954eab2793f9adf0de75775563df0ae6f063f3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161159"
---
# <a name="name-resolution-for-dependent-types"></a>Разрешение имен зависимых типов

Используйте **TypeName** для уточненных имен в определениях шаблонов, чтобы сообщить компилятору, что заданное полное имя определяет тип. Дополнительные сведения см. в разделе [TypeName](../cpp/typename.md).

```cpp
// template_name_resolution1.cpp
#include <stdio.h>
template <class T> class X
{
public:
   void f(typename T::myType* mt) {}
};

class Yarg
{
public:
   struct myType { };
};

int main()
{
   X<Yarg> x;
   x.f(new Yarg::myType());
   printf("Name resolved by using typename keyword.");
}
```

```Output
Name resolved by using typename keyword.
```

Поиск имен для зависимых имен проверяет имена из контекста определения шаблона. в следующем примере этот контекст найдет `myFunction(char)`— и контекст создания экземпляра шаблона. В следующем примере создается экземпляр шаблона в Main. Таким образом, `MyNamespace::myFunction` видна с момента создания экземпляра и выбирается в качестве лучшего соответствия. В случае переименования функции `MyNamespace::myFunction` вместо нее будет вызываться функция `myFunction(char)`.

Разрешение имен выполняется так, как если бы они были зависимыми. Однако при наличии любой возможности конфликта рекомендуется использовать полные имена.

```cpp
// template_name_resolution2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

void myFunction(char)
{
   cout << "Char myFunction" << endl;
}

template <class T> class Class1
{
public:
   Class1(T i)
   {
      // If replaced with myFunction(1), myFunction(char)
      // will be called
      myFunction(i);
}
};

namespace MyNamespace
{
   void myFunction(int)
   {
      cout << "Int MyNamespace::myFunction" << endl;
   }
};

using namespace MyNamespace;

int main()
{
   Class1<int>* c1 = new Class1<int>(100);
}
```

### <a name="output"></a>Выходные данные

```Output
Int MyNamespace::myFunction
```

### <a name="template-disambiguation"></a>Устранение неоднозначности шаблона

Visual Studio 2012 применяет стандартные правила C++ 98/03/11 для устранения неоднозначности с помощью ключевого слова "Template". В следующем примере Visual Studio 2010 принимает как несоответствующие строки, так и согласованные строки.  Visual Studio 2012 принимает только строки соответствия.

```cpp
#include <iostream>
#include <ostream>
#include <typeinfo>
using namespace std;

template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    #if defined(NONCONFORMANT)
        typedef typename AY::Rebind<X>::Other AX; // nonconformant
    #elif defined(CONFORMANT)
        typedef typename AY::template Rebind<X>::Other AX; // conformant
    #else
        #error Define NONCONFORMANT or CONFORMANT.
    #endif
};

int main() {
    cout << typeid(Container<int, Allocator<float>>::AX).name() << endl;
}
```

Соответствие правилам устранения неоднозначности необходимо соблюдать, поскольку по умолчанию C++ предполагает, что `AY::Rebind` не является шаблоном, в результате чего компилятор интерпретирует знак "`<`" как "меньше чем". Чтобы компилятор мог правильно интерпретировать знак "`Rebind`" как угловую скобку, он должен знать, что `<` — это шаблон.

## <a name="see-also"></a>См. также раздел

[Разрешение имен](../cpp/templates-and-name-resolution.md)
