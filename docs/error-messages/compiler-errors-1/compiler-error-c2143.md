---
title: Ошибка компилятора C2143
ms.date: 11/04/2016
f1_keywords:
- C2143
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
ms.openlocfilehash: ed4bc7eea85e5263d59817082caed99bde3d75d5
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520118"
---
# <a name="compiler-error-c2143"></a>Ошибка компилятора C2143

Синтаксическая ошибка: отсутствует «токен1» до «токен2»

Компилятор ожидает определенного маркера (то есть элемента языка не пробел) и вместо этого обнаружен другой токен.

Проверьте [Справочник по языку C++](../../cpp/cpp-language-reference.md) для определения, где синтаксически неправильный код. Поскольку компилятор может сообщить об этой ошибке, после обнаружения строки, которая вызывает проблему, следует проверьте несколько строк кода, вызвавшей ошибку.

C2143 может возникать в различных ситуациях.

Это может произойти, если оператор, который можно уточнить имя (`::`, `->`, и `.`) должно следовать ключевое слово `template`, как показано в этом примере:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143
    {
    };
};
```

По умолчанию C++ предполагает, что `Ty::PutFuncType` не является шаблоном; таким образом, следующее `<` интерпретируется как менее-чем входа.  Необходимо сообщить компилятору явным образом, `PutFuncType` — это шаблон, чтобы он мог правильно интерпретировать знак угловой скобкой. Чтобы исправить эту ошибку, используйте `template` ключевое слово в имени зависимого типа, как показано ниже:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct
    {
    };
};
```

C2143 может произойти при **/CLR** используется и `using` директива содержит синтаксическую ошибку:

```cpp
// C2143a.cpp
// compile with: /clr /c
using namespace System.Reflection;   // C2143
using namespace System::Reflection;
```

Он также может возникнуть при попытке скомпилировать файл исходного кода с помощью синтаксиса CLR без параметра **/CLR**:

```cpp
// C2143b.cpp
ref struct A {   // C2143 error compile with /clr
   void Test() {}
};

int main() {
   A a;
   a.Test();
}
```

Первый отличный от пробела символ, следующий за `if` инструкция должна быть левая круглая скобка. Компилятор не может перевести ничего:

```cpp
// C2143c.cpp
int main() {
   int j = 0;

   // OK
   if (j < 25)
      ;

   if (j < 25)   // C2143
}
```

C2143 может произойти, если закрывающей фигурной скобки, круглой или точкой с запятой отсутствует в строке, когда обнаруживается ошибка или на одну из строк, прямо перед:

```cpp
// C2143d.cpp
// compile with: /c
class X {
   int member1;
   int member2   // C2143
} x;
```

Или, если имеется недопустимый тег в объявлении класса:

```cpp
// C2143e.cpp
class X {
   int member;
} x;

class + {};   // C2143 + is an invalid tag name
class ValidName {};   // OK
```

Или, если метка не присоединен к оператору. Если необходимо поместить метку сам по себе, например, в конце составного оператора, подключите ее к оператором null:

```cpp
// C2143f.cpp
// compile with: /c
void func1() {
   // OK
   end1:
      ;

   end2:   // C2143
}
```

Эта ошибка может возникать, когда вызов типа в стандартной библиотеке C++:

```cpp
// C2143g.cpp
// compile with: /EHsc /c
#include <vector>
static vector<char> bad;   // C2143
static std::vector<char> good;   // OK
```

Или отсутствует `typename` ключевое слово:

```cpp
// C2143h.cpp
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};
template <typename T>
X<T>::Y X<T>::memFunc() {   // C2143
// try the following line instead
// typename X<T>::Y X<T>::memFunc() {
   return Y();
}
```

Или при попытке определить явное создание:

```cpp
// C2143i.cpp
// compile with: /EHsc /c
// template definition
template <class T>
void PrintType(T i, T j) {}

template void PrintType(float i, float j){}   // C2143
template void PrintType(float i, float j);   // OK
```

В программе на языке C переменные должны быть объявлены в начале функции, и они не могут объявляться после эта функция выполняет инструкции, отличные от объявления.

```C
// C2143j.c
int main()
{
    int i = 0;
    i++;
    int j = 0; // C2143
}
```
