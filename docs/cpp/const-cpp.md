---
title: const (C++)
ms.date: 11/04/2016
f1_keywords:
- const_cpp
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
ms.openlocfilehash: cc1f117cc5f26edf9cd85461281b925c97fa5225
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180308"
---
# <a name="const-c"></a>const (C++)

При изменении объявления данных ключевое слово **const** указывает, что объект или переменная не являются изменяемыми.

## <a name="syntax"></a>Синтаксис

```
const declaration ;
member-function const ;
```

## <a name="const-values"></a>Значения-константы

Ключевое слово **const** указывает, что значение переменной является константой и сообщает компилятору о том, что программист не сможет его изменить.

```cpp
// constant_values1.cpp
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```

В C++можно использовать ключевое слово **const** вместо директивы препроцессора [#define](../preprocessor/hash-define-directive-c-cpp.md) для определения постоянных значений. Значения, определенные с помощью **const** , подчиняются проверке типа, и их можно использовать вместо константных выражений. В C++можно указать размер массива с переменной **const** следующим образом:

```cpp
// constant_values2.cpp
// compile with: /c
const int maxarray = 255;
char store_char[maxarray];  // allowed in C++; not allowed in C
```

В языке C константные значения по умолчанию имеют внешнюю компоновку, поэтому они могут использоваться только в файлах исходного кода. В языке C++ константные значения по умолчанию имеют внутреннюю компоновку, которая позволяет использовать их в файлах заголовков.

Ключевое слово **const** можно также использовать в объявлениях указателей.

```cpp
// constant_values3.cpp
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```

Указатель на переменную, объявленную как **const** , можно назначить только указателю, который также объявлен как **const**.

```cpp
// constant_values4.cpp
#include <stdio.h>
int main() {
   const char *mybuf = "test";
   char *yourbuf = "test2";
   printf_s("%s\n", mybuf);

   const char *bptr = mybuf;   // Pointer to constant data
   printf_s("%s\n", bptr);

   // *bptr = 'a';   // Error
}
```

Указатели на данные-константы можно использовать в качестве параметров функций, чтобы функция не могла изменять параметр, переданный посредством указателя.

Для объектов, объявленных как **const**, можно вызывать только константные функции членов. Это гарантирует, что константный объект не будет изменен.

```cpp
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```

Для объектов, не объявленных как константы, можно вызывать как константные, так и неконстантные функции-члены. Можно также перегружать функцию-член с помощью ключевого слова **const** . Это позволяет вызывать другую версию функции для постоянных и неконстантных объектов.

Нельзя объявлять конструкторы или деструкторы с ключевым словом **const** .

## <a name="const-member-functions"></a>Функции-члены-константы

Объявление функции-члена с ключевым словом **const** указывает, что функция является функцией "только для чтения", которая не изменяет объект, для которого она вызывается. Функция-член константы не может изменять какие-либо нестатические элементы данных или вызывать функции-члены, не являющиеся константами. Чтобы объявить функцию-член константы, поместите ключевое слово **const** после закрывающей круглой скобки списка аргументов. Ключевое слово **const** требуется как в объявлении, так и в определении.

```cpp
// constant_member_function.cpp
class Date
{
public:
   Date( int mn, int dy, int yr );
   int getMonth() const;     // A read-only function
   void setMonth( int mn );   // A write function; can't be const
private:
   int month;
};

int Date::getMonth() const
{
   return month;        // Doesn't modify anything
}
void Date::setMonth( int mn )
{
   month = mn;          // Modifies data member
}
int main()
{
   Date MyDate( 7, 4, 1998 );
   const Date BirthDate( 1, 18, 1953 );
   MyDate.setMonth( 4 );    // Okay
   BirthDate.getMonth();    // Okay
   BirthDate.setMonth( 4 ); // C2662 Error
}
```

## <a name="c-and-c-const-differences"></a>Различия в C++ C и const

При объявлении переменной в качестве **константы** в файле исходного кода на языке C это можно сделать следующим образом:

```cpp
const int i = 2;
```

Затем эту переменную можно использовать в другом модуле следующим образом:

```cpp
extern const int i;
```

Но чтобы получить такое же поведение в C++, необходимо объявить переменную **const** следующим образом:

```cpp
extern const int i = 2;
```

Если вы хотите объявить переменную **extern** в файле C++ исходного кода для использования в файле исходного кода на языке C, используйте:

```cpp
extern "C" const int x=10;
```

для предотвращения изменения имени компилятором C++.

## <a name="remarks"></a>Remarks

При использовании списка параметров в функции-члене ключевое слово **const** указывает, что функция не изменяет объект, для которого она вызывается.

Дополнительные сведения о **const**см. в следующих разделах:

- [Указатели с ключевыми словами const и volatile](../cpp/const-and-volatile-pointers.md)

- [Квалификаторы типов (Справочник по языку C)](../c-language/type-qualifiers.md)

- [volatile](../cpp/volatile-cpp.md)

- [#define](../preprocessor/hash-define-directive-c-cpp.md)

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)
