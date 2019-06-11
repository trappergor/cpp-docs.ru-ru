---
title: abstract (C++/CLI and C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- abstract
- abstract_cpp
helpviewer_keywords:
- abstract keyword [C++]
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
ms.openlocfilehash: d5060f1a0950b9b2ac2638b99ff157983944a3bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516169"
---
# <a name="abstract--ccli-and-ccx"></a>abstract (C++/CLI and C++/CX)

Ключевое слово **abstract** объявляет, что:

- Тип можно использовать в качестве базового типа, но экземпляр самого тип не может быть создан.

- Функция-член типа может определяться только в производном типе.

## <a name="all-platforms"></a>Все платформы

### <a name="syntax"></a>Синтаксис

*class-declaration* *class-identifier* **abstract {}**

**virtual** *return-type* *member-function-identifier* **() abstract ;**

### <a name="remarks"></a>Примечания

В первом примере синтаксиса объявляется абстрактный класс. Компонент *class-declaration* может быть либо собственным объявлением C++ (**class** или **struct**), либо объявлением расширения C++ (**ref class** или **ref struct**), если указан параметр компилятора `/ZW` или `/clr`.

Во втором примере синтаксиса объявляется абстрактная виртуальная функция-член. Объявление функции абстрактной — то же, что и объявление ее чистой виртуальной функцией. Объявление функции-члена абстрактной также приводит к тому, что включающий класс объявляется как абстрактный.

Ключевое слово **abstract** поддерживается в машинном коде и в коде платформы, то есть он может компилироваться как с параметром компилятора `/ZW` или `/clr`, так и без него.

Во время компиляции можно определить, является ли тип абстрактным, с помощью признака типа `__is_abstract(type)`. Подробные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

Ключевое слово **abstract** является контекстно-зависимым описателем переопределения. Подробные сведения о контекстно-зависимых ключевых словах см. в статье [Context-Sensitive Keywords (C++/CLI and C++/CX)](context-sensitive-keywords-cpp-component-extensions.md) (Контекстно-зависимые ключевые слова (C++/CLI and C++/CX)). Подробные сведения об описателях переопределения см. в статье [How to: Declare Override Specifiers in Native Compilations](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md) (Практическое руководство. Объявление описателей переопределения в компиляциях в машинный код).

## <a name="windows-runtime"></a>Среда выполнения Windows

Подробные сведения см. в статье [Ref classes and structs (C++/CX)](../cppcx/ref-classes-and-structs-c-cx.md) (Ссылочные классы и структуры (C++/CX)).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере кода возникает ошибка, поскольку класс `X` помечен как **abstract**.

```cpp
// abstract_keyword.cpp
// compile with: /clr
ref class X abstract {
public:
   virtual void f() {}
};

int main() {
   X ^ MyX = gcnew X;   // C3622
}
```

В следующем примере кода возникает ошибка, поскольку он создает экземпляр собственного класса, помеченного как **abstract**. Эта ошибка будет возникать как с параметром компилятора `/clr`, так и без него.

```cpp
// abstract_keyword_2.cpp
class X abstract {
public:
   virtual void f() {}
};

int main() {
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'
                    // cannot be instantiated. See declaration of 'X'}
```

В следующем примере кода возникает ошибка, поскольку функция `f` включает определение, но помечена как **abstract**. Последняя инструкция в примере показывает, что объявление абстрактной виртуальной функции эквивалентно объявлению чистой виртуальной функции.

```cpp
// abstract_keyword_3.cpp
// compile with: /clr
ref class X {
public:
   virtual void f() abstract {}   // C3634
   virtual void g() = 0 {}   // C3634
};
```

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
