---
title: Оператор отслеживаемых ссылок (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- '%'
helpviewer_keywords:
- tracking references
- '% tracking reference [C++]'
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
ms.openlocfilehash: ab1b11d3f8d3416a6e9ed345085d63ce86d56010
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181789"
---
# <a name="tracking-reference-operator-ccli-and-ccx"></a>Оператор отслеживаемых ссылок (C++/CLI и C++/CX)

*Отслеживаемая ссылка* (`%`) действует, как обычная ссылка C++ (`&`). Но если объекту присвоить отслеживаемую ссылку, число ссылок объекта увеличивается.

## <a name="all-platforms"></a>Все платформы

Отслеживаемая ссылка имеет следующие характеристики:

- Присвоение объекту отслеживаемой ссылки увеличивает счетчик ссылок объекта.

- Собственная ссылка (`&`) — это результат разыменования `*`. Отслеживаемая ссылка (`%`) — это результат разыменования `^`. Пока имеется ссылка на объект (`%`), он будет оставаться в памяти в активном состоянии.

- Оператор доступа к членам "точка" (`.`) используется для обращения к членам объекта.

- Отслеживаемые ссылки являются допустимыми для типов значений и дескрипторов (например, `String^`).

- Отслеживаемой ссылке невозможно присвоить значение NULL или **nullptr**. Отслеживаемая ссылка может быть переприсвоена другому допустимому объекту любое число раз при необходимости.

- Отслеживаемую ссылку невозможно использовать в качестве унарного оператора получения адреса.

## <a name="windows-runtime"></a>Среда выполнения Windows

Отслеживаемая ссылка ведет себя как стандартная ссылка C++, за исключением того, что % учитывается при подсчете ссылок. В следующем фрагменте кода показано, как выполнять преобразование между типами % и ^:

```cpp
Foo^ spFoo = ref new Foo();
Foo% srFoo = *spFoo;
Foo^ spFoo2 = %srFoo;
```

В следующем примере показан способ передачи ^ в функцию, которая принимает %.

```cpp
ref class Foo sealed {};

    // internal or private
    void UseFooHelper(Foo% f)
    {
        auto x = %f;
    }

    // public method on ABI boundary
    void UseFoo(Foo^ f)
    {
        if (f != nullptr) { UseFooHelper(*f); }
    }
```

## <a name="common-language-runtime"></a>Среда CLR

В C++/CLI можно использовать отслеживаемую ссылку на дескриптор при привязке к объекту типа CLR в куче со сборкой мусора.

В CLR значение переменной отслеживаемой ссылки обновляется автоматически, когда сборщик мусора перемещает указанный объект.

Отслеживаемая ссылка может быть объявлена только в стеке. Отслеживаемая ссылка не может быть членом класса.

Невозможно создать собственную ссылку C++ на объект, находящийся в куче со сборкой мусора.

Дополнительные сведения об отслеживаемых ссылках C++/CLI см. в следующих разделах:

- [Практическое руководство. Использование отслеживаемых ссылок в C++/CLI](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)

### <a name="examples"></a>Примеры

В следующем примере для C++/CLI показано, как использовать отслеживаемые ссылки в собственных и управляемых типах.

```cpp
// tracking_reference_1.cpp
// compile with: /clr
ref class MyClass {
public:
   int i;
};

value struct MyStruct {
   int k;
};

int main() {
   MyClass ^ x = ref new MyClass;
   MyClass ^% y = x;   // tracking reference handle to reference object

   int %ti = x->i;   // tracking reference to member of reference type

   int j = 0;
   int %tj = j;   // tracking reference to object on the stack

   int * pi = new int[2];
   int % ti2 = pi[0];   // tracking reference to object on native heap

   int *% tpi = pi;   // tracking reference to native pointer

   MyStruct ^ x2 = ref new MyStruct;
   MyStruct ^% y2 = x2;   // tracking reference to value object

   MyStruct z;
   int %tk = z.k;   // tracking reference to member of value type

   delete[] pi;
}
```

В следующем примере для C++/CLI показано, как привязать отслеживаемую ссылку к массиву.

```cpp
// tracking_reference_2.cpp
// compile with: /clr
using namespace System;

int main() {
   array<int> ^ a = ref new array<Int32>(5);
   a[0] = 21;
   Console::WriteLine(a[0]);
   array<int> ^% arr = a;
   arr[0] = 222;
   Console::WriteLine(a[0]);
}
```

```Output
21
222
```
