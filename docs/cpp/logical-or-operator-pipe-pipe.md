---
title: 'Оператор логического или: ||'
ms.date: 06/14/2018
f1_keywords:
- '||'
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
ms.openlocfilehash: 5db1af870644d1552aeac813edce0985a31d95b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368686"
---
# <a name="logical-or-operator-"></a>Оператор логического или: ||

## <a name="syntax"></a>Синтаксис

> *logical-or-expression* **||** *logical-and-expression*

## <a name="remarks"></a>Примечания

Оператор логического или (**||**) возвращает логическое значение TRUE, если один или оба операнда имеет значение TRUE и в противном случае возвращает FALSE. Операнды неявно преобразуются в тип **bool** предварительного ознакомления, и результат имеет тип **bool**. Логическое ИЛИ имеет ассоциативность в направлении слева направо.

Операнды оператора логического ИЛИ не обязаны относиться к одному и тому же типу, однако должны иметь целочисленный тип или тип указателя. В качестве операндов часто используются реляционные выражения и выражения равенства.

В выражении логического ИЛИ сначала полностью вычисляется первый операнд и учитываются все побочные эффекты, и лишь после этого вычисление продолжается.

Второй операнд вычисляется только в том случае, если первый имеет значение false (0). Это исключает необязательное вычисление второго операнда, если выражение логического ИЛИ имеет значение true.

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

В приведенном выше примере, если `x` равно `w`, `y` или `z`, то второй аргумент функции `printf` имеет значение true и код выводит значение 1. В противном случае он возвращает значение false и код выводит значение 0. Как только обнаруживается, что одно из значений равно true, вычисление прекращается.

## <a name="operator-keyword-for-124124"></a>Ключевое слово оператора&#124;&#124;

**Или** оператор является текстовым эквивалентом **||**. Существует два способа для доступа к **или** оператор в программах: включить файл заголовка \<iso646.h >, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).

## <a name="example"></a>Пример

```cpp
// expre_Logical_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate logical OR
#include <iostream>
using namespace std;
int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b || b > c yields "
         << (a < b || b > c) << endl
         << "The false expression "
         << "a > b || b > c yields "
         << (a > b || b > c) << endl;
}
```

## <a name="see-also"></a>См. также

[Встроенные операторы C++ приоритет и ассоциативность операторов](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Логические операторы в C](../c-language/c-logical-operators.md)