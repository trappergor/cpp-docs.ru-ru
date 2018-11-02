---
title: Поддержка характеристик типов компилятором (C + +/ CLI и C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- __is_simple_value_class
- __has_trivial_destructor
- __has_assign
- __is_union
- __is_class
- __is_abstract
- __has_trivial_assign
- __has_virtual_destructor
- __is_ref_array
- __is_base_of
- __has_copy
- __is_polymorphic
- __has_nothrow_constructor
- __is_ref_class
- __is_delegate
- __is_convertible_to
- __is_value_class
- __is_interface_class
- __has_nothrow_copy
- __is_sealed
- __has_trivial_constructor
- __has_trivial_copy
- __is_enum
- __has_nothrow_assign
- __has_finalizer
- __is_empty
- __is_pod
- __has_user_destructor
helpviewer_keywords:
- __is_class keyword [C++]
- __is_pod keyword [C++]
- __is_delegate keyword [C++]
- __is_value_class keyword [C++]
- __has_copy keyword [C++]
- __has_nothrow_copy keyword [C++]
- __is_interface_class keyword [C++]
- __is_sealed keyword [C++]
- __is_convertible_to keyword [C++]
- __is_ref_class keyword [C++]
- __has_trivial_copy keyword [C++]
- __has_user_destructor keyword [C++]
- __is_abstract keyword [C++]
- __is_empty keyword [C++]
- __has_trivial_assign keyword [C++]
- __has_nothrow_constructor keyword [C++]
- __is_ref_array keyword [C++]
- __is_base_of keyword [C++]
- __has_nothrow_assign keyword [C++]
- __has_virtual_destructor keyword [C++]
- __has_finalizer keyword [C++]
- __is_union keyword [C++]
- __has_assign keyword [C++]
- __has_trivial_destructor keyword [C++]
- __is_polymorphic keyword [C++]
- __is_enum keyword [C++]
- __is_simple_value_class keyword [C++]
- __has_trivial_constructor keyword [C++]
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
ms.openlocfilehash: 5cd4d7feef01d1b7bedd407357c618ba208d06f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536192"
---
# <a name="compiler-support-for-type-traits-ccli-and-ccx"></a>Поддержка характеристик типов компилятором (C + +/ CLI и C + +/ CX)

Компилятор Microsoft C++ поддерживает *признаки типов* C + +/ CLI и C + +/ CX расширения, которые указывают различные характеристики типов во время компиляции.

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="remarks"></a>Примечания

Признаки типов особенно важны для программистов, создающих библиотеки.

Следующий список содержит признаки типов, поддерживаемые компилятором. Все признаки типов возвращают **false** при несоблюдении условия, указанного по имени признака типа.

(В списке ниже примеры кода представлены только в C + +/ CLI. Но соответствующий признак типа также поддерживается в C + +/ CX Если не указано иное. Термин, «тип платформы» относится к типов среды выполнения Windows или типами среды CLR.)

- `__has_assign(` *Тип* `)`

   Возвращает **true** Если тип платформы или собственный тип содержит оператор присваивания копии.

    ```cpp
    ref struct R {
    void operator=(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_assign(R));
    }
    ```

- `__has_copy(` *Тип* `)`

   Возвращает **true** Если тип платформы или собственный тип содержит конструктор копии.

    ```cpp
    ref struct R {
    R(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_copy(R));
    }
    ```

- `__has_finalizer(` *Тип* `)`

   (Не поддерживается в C + +/ CX.) Возвращает **true** Если тип среды CLR имеет метод завершения. См. в разделе [деструкторы и методы завершения в разделе: определение и использование классов и структур (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) Дополнительные сведения.

    ```cpp
    using namespace System;
    ref struct R {
    ~R() {}
    protected:
    !R() {}
    };

    int main() {
    Console::WriteLine(__has_finalizer(R));
    }
    ```

- `__has_nothrow_assign(` *Тип* `)`

   Возвращает **true** Если оператор присваивания копии имеет пустую спецификацию исключений.

    ```cpp
    #include <stdio.h>
    struct S {
    void operator=(S& r) throw() {}
    };

    int main() {
    __has_nothrow_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_constructor(` *Тип* `)`

   Возвращает **true** Если конструктор по умолчанию имеет пустую спецификацию исключений.

    ```cpp
    #include <stdio.h>
    struct S {
    S() throw() {}
    };

    int main() {
    __has_nothrow_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_copy(` *Тип* `)`

   Возвращает **true** Если конструктор копии имеет пустую спецификацию исключений.

    ```cpp
    #include <stdio.h>
    struct S {
    S(S& r) throw() {}
    };

    int main() {
    __has_nothrow_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_assign(` *Тип* `)`

   Возвращает **true** Если тип имеет оператор присваивания тривиальным, созданный компилятором.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_constructor(` *Тип* `)`

   Возвращает **true** Если тип содержит тривиальный, созданный компилятором конструктор.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_copy(` *Тип* `)`

   Возвращает **true** Если тип имеет конструктор копии тривиальным, созданный компилятором.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_destructor(` *Тип* `)`

   Возвращает **true** Если тип содержит тривиальный, созданный компилятором деструктор.

    ``` cpp
    // has_trivial_destructor.cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_user_destructor(` *Тип* `)`

   Возвращает **true** Если тип платформы или собственный тип содержит объявленный пользователем деструктор.

    ```cpp
    // has_user_destructor.cpp

    using namespace System;
    ref class R {
    ~R() {}
    };

    int main() {
    Console::WriteLine(__has_user_destructor(R));
    }
    ```

- `__has_virtual_destructor(` *Тип* `)`

   Возвращает **true** Если тип содержит виртуальный деструктор.

   Признак `__has_virtual_destructor` также работает с типами платформ, и любой определенный пользователем деструктор в типе платформы является виртуальным деструктором.

    ```cpp
    // has_virtual_destructor.cpp
    #include <stdio.h>
    struct S {
    virtual ~S() {}
    };

    int main() {
    __has_virtual_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_abstract(` *Тип* `)`

   Возвращает **true** Если тип является абстрактным типом. Дополнительные сведения о собственных абстрактных типах см. в разделе [абстрактные классы](../cpp/abstract-classes-cpp.md).

   Признак `__is_abstract` также работает с типами платформ. Интерфейс хотя бы с одним членом является абстрактным типом, как и ссылочный тип по крайней мере с одним абстрактным членом. Дополнительные сведения об абстрактных типах платформ см. в разделе [абстрактный](../windows/abstract-cpp-component-extensions.md).

    ```cpp
    // is_abstract.cpp
    #include <stdio.h>
    struct S {
    virtual void Test() = 0;
    };

    int main() {
    __is_abstract(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_base_of(` `base` `,` `derived` `)`

   Возвращает **true** Если первый тип является базовым классом второго типа, если оба типа одинаковы.

   Признак `__is_base_of` также работает с типами платформ. Например, он вернет **true** Если первый тип — [класс интерфейса](../windows/interface-class-cpp-component-extensions.md) и второй тип реализует интерфейс.

    ```cpp
    // is_base_of.cpp
    #include <stdio.h>
    struct S {};
    struct T : public S {};

    int main() {
    __is_base_of(S, T) == true ?
    printf("true\n") : printf("false\n");

    __is_base_of(S, S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_class(` *Тип* `)`

   Возвращает **true** Если тип является собственным классом или структурой.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_class(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_convertible_to(` `from` `,`  `to` `)`

   Возвращает **true** Если первый тип можно преобразовать во второй.

    ```cpp
    #include <stdio.h>
    struct S {};
    struct T : public S {};

    int main() {
    S * s = new S;
    T * t = new T;
    s = t;
    __is_convertible_to(T, S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_delegate(` *Тип* `)`

   Возвращает **true** Если `type` является делегатом. Дополнительные сведения см. в разделе [делегата (C + +/ CLI и C + +/ CX)](../windows/delegate-cpp-component-extensions.md).

    ```cpp
    delegate void MyDel();
    int main() {
    System::Console::WriteLine(__is_delegate(MyDel));
    }
    ```

- `__is_empty(` *Тип* `)`

   Возвращает **true** Если тип не содержит экземпляр данных членов.

    ```cpp
    #include <stdio.h>
    struct S {
    int Test() {}
    static int i;
    };
    int main() {
    __is_empty(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_enum(` *Тип* `)`

   Возвращает **true** Если тип является собственным перечислением.

    ```cpp
    // is_enum.cpp
    #include <stdio.h>
    enum E { a, b };

    struct S {
    enum E2 { c, d };
    };

    int main() {
    __is_enum(E) == true ?
    printf("true\n") : printf("false\n");

    __is_enum(S::E2) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_interface_class(` *Тип* `)`

   Возвращает **true** Если передается интерфейс платформы. Дополнительные сведения см. в разделе [класс интерфейса](../windows/interface-class-cpp-component-extensions.md).

    ```cpp
    // is_interface_class.cpp

    using namespace System;
    interface class I {};
    int main() {
    Console::WriteLine(__is_interface_class(I));
    }
    ```

- `__is_pod(` *Тип* `)`

   Возвращает **true** ли тип класса или объединения с нет конструктора или закрытых или защищенных нестатических членов, без базовых классов и виртуальных функций. Дополнительные сведения о POD см. в разделах 8.5.1/1, 9/4 и 3.9/10 стандарта C++.

   Для фундаментальных типов признак `__is_pod` возвращает значение false.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_pod(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_polymorphic(` *Тип* `)`

   Возвращает **true** если собственный тип содержит виртуальные функции.

    ```cpp
    #include <stdio.h>
    struct S {
    virtual void Test(){}
    };

    int main() {
    __is_polymorphic(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_ref_array(` *Тип* `)`

   Возвращает **true** Если передается массив платформы. Дополнительные сведения см. в разделе [массивы](../windows/arrays-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    int main() {
    array<int>^ x = gcnew array<int>(10);
    Console::WriteLine(__is_ref_array(array<int>));
    }
    ```

- `__is_ref_class(` *Тип* `)`

   Возвращает **true** Если передается ссылочный класс. Дополнительные сведения об определяемых пользователем ссылочных типах см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    ref class R {};
    int main() {
    Console::WriteLine(__is_ref_class(Buffer));
    Console::WriteLine(__is_ref_class(R));
    }
    ```

- `__is_sealed(` *Тип* `)`

   Возвращает **true** Если передается платформа или собственный тип, отмеченный как запечатанный. Дополнительные сведения см. в разделе [запечатанный](../windows/sealed-cpp-component-extensions.md).

    ```cpp
    ref class R sealed{};
    int main() {
    System::Console::WriteLine(__is_sealed(R));
    }
    ```

- `__is_simple_value_class(` *Тип* `)`

   Возвращает **true** Если передается тип значения, не содержит ссылок в кучу сборщиком мусора. Дополнительные сведения о типах значений, определяемых пользователем, см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    ref class R {};
    value struct V {};
    value struct V2 {
    R ^ r;   // not a simnple value type
    };

    int main() {
    Console::WriteLine(__is_simple_value_class(V));
    Console::WriteLine(__is_simple_value_class(V2));
    }
    ```

- `__is_union(` *Тип* `)`

   Возвращает **true** является ли тип объединения.

    ```cpp
    #include <stdio.h>
    union A {
    int i;
    float f;
    };

    int main() {
    __is_union(A) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_value_class(` *Тип* `)`

   Возвращает **true** Если передается тип значения. Дополнительные сведения о типах значений, определяемых пользователем, см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).

    ```cpp
    value struct V {};

    int main() {
    System::Console::WriteLine(__is_value_class(V));
    }
    ```

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="remarks"></a>Примечания

`__has_finalizer(` *Тип* `)` Признак типа не поддерживается, поскольку эта платформа не поддерживает методы завершения.

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для данной возможности в рамках этой платформы).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

**Пример**

В следующем примере кода показано использование шаблона класса для предоставления признака типа компилятора при компиляции `/clr`. Дополнительные сведения см. в разделе [среды выполнения Windows и управляемые шаблоны](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).

```cpp
// compiler_type_traits.cpp
// compile with: /clr
using namespace System;

template <class T>
ref struct is_class {
   literal bool value = __is_ref_class(T);
};

ref class R {};

int main () {
   if (is_class<R>::value)
      Console::WriteLine("R is a ref class");
   else
      Console::WriteLine("R is not a ref class");
}
```

```Output
R is a ref class
```

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](../windows/component-extensions-for-runtime-platforms.md)