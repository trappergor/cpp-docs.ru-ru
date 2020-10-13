---
title: nullptr (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
ms.openlocfilehash: 7e9cf88fdc0444f736f1cfac0d06dfc675a162cc
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008355"
---
# <a name="nullptr--ccli-and-ccx"></a>nullptr (C++/CLI и C++/CX)

**`nullptr`** Ключевое слово представляет *значение пустого указателя*. Значение пустого указателя показывает, что тип дескриптора объекта, внутреннего указателя или собственного указателя не указывает на объект.

Используйте **`nullptr`** с управляемым или машинным кодом. Компилятор выводит соответствующие, но различные инструкции для управляемых и машинных значений пустых указателей. Дополнительные сведения об использовании версии этого ключевого слова в соответствии со стандартом ISO C++ см. в разделе [nullptr](../cpp/nullptr.md).

Ключевое слово **__nullptr** — это ключевое слово Microsoft, которое имеет то же значение **`nullptr`** , что и, но применяется только к машинному коду. Если используется **`nullptr`** с машинным кодом C/C++, а затем компилируется с параметром компилятора [/CLR](../build/reference/clr-common-language-runtime-compilation.md) , компилятор не может определить, **`nullptr`** указывает ли значение исходного или управляемого указателя NULL. Чтобы сделать свою намерение понятной для компилятора, используйте **`nullptr`** для указания управляемого значения или **__nullptr** , чтобы указать собственное значение.

**`nullptr`** Ключевое слово эквивалентно значению **Nothing** в Visual Basic и **null** в C#.

## <a name="usage"></a>Использование

**`nullptr`** Ключевое слово можно использовать в любом месте, где может использоваться маркер, собственный указатель или аргумент функции.

**`nullptr`** Ключевое слово не является типом и не поддерживается для использования с:

- [sizeof](../cpp/sizeof-operator.md)

- [типа](../cpp/typeid-operator.md)

- `throw nullptr` (однако `throw (Object^)nullptr;` будет работать)

**`nullptr`** Ключевое слово можно использовать при инициализации следующих типов указателей:

- собственного указателя;

- дескриптора среды выполнения Windows;

- управляемого дескриптора;

- управляемого внутреннего указателя.

**`nullptr`** Ключевое слово можно использовать для проверки, имеет ли ссылка указателя или обработчика значение null перед использованием ссылки.

Вызовы функций для языков, использующих значения пустых указателей для проверки ошибок, должны правильно интерпретироваться.

Нельзя инициализировать нулевой маркер; **`nullptr`** можно использовать только. При присвоении константы 0 дескриптору объекта создаются упакованный тип `Int32` и приведение к типу `Object^`.

## <a name="example-nullptr-keyword"></a>Пример: `nullptr` ключевое слово

В следующем примере кода показано, что **`nullptr`** ключевое слово можно использовать везде, где можно использовать обработчик, собственный указатель или аргумент функции. В примере показано, что **`nullptr`** ключевое слово можно использовать для проверки ссылки перед ее использованием.

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

## <a name="example-use-nullptr-and-zero-interchangeably"></a>Пример. Использование `nullptr` и нулевое взаимозаменяемость

В следующем примере кода показано, что **`nullptr`** и ноль могут использоваться в собственных указателях в качестве взаимозаменяемых.

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

## <a name="example-interpret-nullptr-as-a-handle"></a>Пример: интерпретировать `nullptr` как маркер

В следующем примере кода показано, что **`nullptr`** интерпретируется как Handle в любой тип или собственный указатель на любой тип. В случае перегрузки функции с дескрипторами различных типов создается ошибка неоднозначности. Необходимо **`nullptr`** явно привести к типу.

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

## <a name="example-cast-nullptr"></a>Пример: CAST `nullptr`

В следующем примере кода показано, что приведение **`nullptr`** разрешено и возвращает указатель или обработчик для типа приведения, содержащего **`nullptr`** значение.

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

## <a name="example-pass-nullptr-as-a-function-parameter"></a>Пример. Передача `nullptr` в качестве параметра функции

В следующем примере кода показано, что **`nullptr`** можно использовать в качестве параметра функции.

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

## <a name="example-default-initialization"></a>Пример: инициализация по умолчанию

В следующем примере кода показано, что когда дескрипторы объявляются и не инициализируются явно, они инициализируются значением по умолчанию **`nullptr`** .

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

## <a name="example-assign-nullptr-to-a-native-pointer"></a>Пример. Назначение `nullptr` в собственный указатель

В следующем примере кода показано, что **`nullptr`** можно присвоить собственный указатель при компиляции с помощью `/clr` .

```cpp
// mcpp_nullptr_6.cpp
// compile with: /clr
int main() {
   int * i = 0;
   int * j = nullptr;
}
```

## <a name="requirements"></a>Требования

Параметр компилятора: необязателен; поддерживается всеми параметрами создания кода, включая `/ZW` и `/clr`.

## <a name="see-also"></a>См. также статью

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)<br/>
[nullptr](../cpp/nullptr.md)
