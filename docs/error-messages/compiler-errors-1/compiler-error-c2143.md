---
title: Ошибка компилятора C2143
ms.date: 11/04/2016
f1_keywords:
- C2143
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
ms.openlocfilehash: 310083a650f842c6c0f0912efe1ceddb66c4fd6f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214754"
---
# <a name="compiler-error-c2143"></a>Ошибка компилятора C2143

Синтаксическая ошибка: отсутствует "токен1" перед "токен2"

Компилятору требуется специальный маркер (т. е. элемент языка, отличный от пробела) и вместо него найти другой токен.

Ознакомьтесь со [справочником по языку C++](../../cpp/cpp-language-reference.md) , чтобы определить, где код синтаксически неверен. Так как компилятор может сообщить об этой ошибке после того, как она встречает строку, которая вызывает проблему, проверьте несколько строк кода, предшествующих ошибке.

C2143 может возникать в разных ситуациях.

Это может произойти, если за оператором, который может определить имя ( `::` , `->` и `.` ), должно следовать ключевое слово **`template`** , как показано в следующем примере:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143
    {
    };
};
```

По умолчанию в C++ предполагается, что `Ty::PutFuncType` он не является шаблоном, поэтому следующий пример `<` интерпретируется как знак "меньше".  Необходимо явно сообщить компилятору, что `PutFuncType` является шаблоном, чтобы он мог правильно проанализировать угловую скобку. Чтобы исправить эту ошибку, используйте **`template`** ключевое слово в имени зависимого типа, как показано ниже:

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct
    {
    };
};
```

C2143 может возникать, когда используется **/CLR** и **`using`** директива содержит синтаксическую ошибку:

```cpp
// C2143a.cpp
// compile with: /clr /c
using namespace System.Reflection;   // C2143
using namespace System::Reflection;
```

Это также может произойти при попытке компиляции файла исходного кода с помощью синтаксиса CLR без использования **/CLR**:

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

Первый символ, не являющийся пробелом, следующий за **`if`** оператором, должен быть открывающей скобкой. Компилятор не может преобразовать что-либо еще:

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

C2143 может возникать, если в строке, где обнаружена ошибка, или в одной из строк, указанных выше, пропущена закрывающая фигурная скобка, круглая скобка или точка с запятой.

```cpp
// C2143d.cpp
// compile with: /c
class X {
   int member1;
   int member2   // C2143
} x;
```

Или при наличии недопустимого тега в объявлении класса:

```cpp
// C2143e.cpp
class X {
   int member;
} x;

class + {};   // C2143 + is an invalid tag name
class ValidName {};   // OK
```

Или, если метка не присоединена к оператору. Если необходимо поместить метку отдельно, например, в конце составного оператора, присоедините ее к оператору NULL:

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

Эта ошибка может возникать при неквалифицированном вызове типа в стандартной библиотеке C++:

```cpp
// C2143g.cpp
// compile with: /EHsc /c
#include <vector>
static vector<char> bad;   // C2143
static std::vector<char> good;   // OK
```

Или отсутствует **`typename`** ключевое слово Missing:

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

Или при попытке определить явное создание экземпляра:

```cpp
// C2143i.cpp
// compile with: /EHsc /c
// template definition
template <class T>
void PrintType(T i, T j) {}

template void PrintType(float i, float j){}   // C2143
template void PrintType(float i, float j);   // OK
```

В программе на языке C переменные должны быть объявлены в начале функции, и они не могут быть объявлены после того, как функция выполняет инструкции, не относящиеся к объявлению.

```C
// C2143j.c
int main()
{
    int i = 0;
    i++;
    int j = 0; // C2143
}
```
