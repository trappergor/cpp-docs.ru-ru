---
title: nullptr (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
ms.openlocfilehash: 05aaaa8a0d0056e0f5318f5e9329d90824760728
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515639"
---
# <a name="nullptr--ccli-and-ccx"></a>nullptr (C++/CLI и C++/CX)

Ключевое слово **nullptr** представляет *значение пустого указателя*. Значение пустого указателя показывает, что тип дескриптора объекта, внутреннего указателя или собственного указателя не указывает на объект.

**nullptr** используется с управляемым или машинным кодом. Компилятор выводит соответствующие, но различные инструкции для управляемых и машинных значений пустых указателей. Дополнительные сведения об использовании версии этого ключевого слова в соответствии со стандартом ISO C++ см. в разделе [nullptr](../cpp/nullptr.md).

Ключевое слово **__nullptr** относится только к системам Microsoft и имеет то же значение, что и ключевое слово **nullptr**, но применяется только для машинного кода. При использовании **nullptr** с машинным кодом C/C++ и последующей компиляции с параметром компилятора [/clr](../build/reference/clr-common-language-runtime-compilation.md) компилятор не может определить, какое значение пустого указателя — машинное или управляемое — обозначается ключевым словом **nullptr**. Чтобы устранить эту проблему, используйте **nullptr** для указания управляемого значения или **__nullptr**, чтобы указать машинное значение.

Ключевое слово **nullptr** эквивалентно **Nothing** в Visual Basic и **null** в C#.

## <a name="usage"></a>Использование

Ключевое слово **nullptr** можно использовать везде, где может применяться дескриптор, собственный указатель или аргумент функции.

Ключевое слово **nullptr** не является типом, и его использование не поддерживается со следующими элементами:

- [sizeof](../cpp/sizeof-operator.md)

- [typeid](../cpp/typeid-operator.md)

- `throw nullptr` (однако `throw (Object^)nullptr;` будет работать)

Ключевое слово **nullptr** можно применять при инициализации следующих типов указателей:

- собственного указателя;

- дескриптора среды выполнения Windows;

- управляемого дескриптора;

- управляемого внутреннего указателя.

Ключевое слово **nullptr** можно использовать для проверки ссылки указателя или дескриптора на значение NULL, прежде чем ссылка будет использоваться.

Вызовы функций для языков, использующих значения пустых указателей для проверки ошибок, должны правильно интерпретироваться.

Нельзя инициализировать дескриптор нулем. Можно использовать только **nullptr**. При присвоении константы 0 дескриптору объекта создаются упакованный тип `Int32` и приведение к типу `Object^`.

## <a name="example"></a>Пример

В приведенном ниже примере кода показано, что ключевое слово **nullptr** может использоваться везде, где может применяться дескриптор, собственный указатель или аргумент функции. Также в этом примере показано, что ключевое слово **nullptr** может использоваться для проверки ссылки перед ее применением.

```cpp
// mcpp_nullptr.cpp
// compile with: /clr
value class V {};
ref class G {};
void f(System::Object ^) {}

int main() {
// Native pointer.
   int *pN = nullptr;
// Managed handle.
   G ^pG = nullptr;
   V ^pV1 = nullptr;
// Managed interior pointer.
   interior_ptr<V> pV2 = nullptr;
// Reference checking before using a pointer.
   if (pN == nullptr) {}
   if (pG == nullptr) {}
   if (pV1 == nullptr) {}
   if (pV2 == nullptr) {}
// nullptr can be used as a function argument.
   f(nullptr);   // calls f(System::Object ^)
}
```

## <a name="example"></a>Пример

В следующем примере кода показано, что **nullptr** и ноль можно взаимозаменяемо использовать для собственных указателей.

```cpp
// mcpp_nullptr_1.cpp
// compile with: /clr
class MyClass {
public:
   int i;
};

int main() {
   MyClass * pMyClass = nullptr;
   if ( pMyClass == nullptr)
      System::Console::WriteLine("pMyClass == nullptr");

   if ( pMyClass == 0)
      System::Console::WriteLine("pMyClass == 0");

   pMyClass = 0;
   if ( pMyClass == nullptr)
      System::Console::WriteLine("pMyClass == nullptr");

   if ( pMyClass == 0)
      System::Console::WriteLine("pMyClass == 0");
}
```

```Output
pMyClass == nullptr

pMyClass == 0

pMyClass == nullptr

pMyClass == 0
```

## <a name="example"></a>Пример

В приведенном ниже примере кода показано, что **nullptr** интерпретируется как дескриптор любого типа или как собственный указатель на любой тип. В случае перегрузки функции с дескрипторами различных типов создается ошибка неоднозначности. **nullptr** необходимо явно приводить к типу.

```cpp
// mcpp_nullptr_2.cpp
// compile with: /clr /LD
void f(int *){}
void f(int ^){}

void f_null() {
   f(nullptr);   // C2668
   // try one of the following lines instead
   f((int *) nullptr);
   f((int ^) nullptr);
}
```

## <a name="example"></a>Пример

В следующем примере кода показано, что допускается приведение **nullptr**, которое возвращает указатель или дескриптор типа приведения, содержащий значение **nullptr**.

```cpp
// mcpp_nullptr_3.cpp
// compile with: /clr /LD
using namespace System;
template <typename T>
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type

int main() {
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)

   // Delete the following line to resolve.
   f(nullptr);

   f(0);   // T = int, call f(int)
}
```

## <a name="example"></a>Пример

В следующем примере кода показано, что **nullptr** можно использовать в качестве параметра функции.

```cpp
// mcpp_nullptr_4.cpp
// compile with: /clr
using namespace System;
void f(Object ^ x) {
   Console::WriteLine("test");
}

int main() {
   f(nullptr);
}
```

```Output
test
```

## <a name="example"></a>Пример

В следующем примере кода показано, что если при объявлении дескрипторы не инициализируются явно, они по умолчанию инициализируются значением **nullptr**.

```cpp
// mcpp_nullptr_5.cpp
// compile with: /clr
using namespace System;
ref class MyClass {
public:
   void Test() {
      MyClass ^pMyClass;   // gc type
      if (pMyClass == nullptr)
         Console::WriteLine("NULL");
   }
};

int main() {
   MyClass ^ x = gcnew MyClass();
   x -> Test();
}
```

```Output
NULL
```

## <a name="example"></a>Пример

В следующем примере кода показано, что **nullptr** можно присвоить собственному указателю при компиляции с параметром `/clr`.

```cpp
// mcpp_nullptr_6.cpp
// compile with: /clr
int main() {
   int * i = 0;
   int * j = nullptr;
}
```

## <a name="requirements"></a>Требования

Параметр компилятора. (Необязателен; поддерживается всеми параметрами создания кода, включая `/ZW` и `/clr`)

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)<br/>
[nullptr](../cpp/nullptr.md)