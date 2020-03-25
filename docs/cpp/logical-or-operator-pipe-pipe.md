---
title: 'Оператор логического ИЛИ: ||'
ms.date: 06/14/2018
f1_keywords:
- '||'
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
ms.openlocfilehash: 94b2bc024dd7223ac7adacc72924f5ee289bab37
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178084"
---
# <a name="logical-or-operator-"></a>Оператор логического ИЛИ: ||

## <a name="syntax"></a>Синтаксис

> Логическое *или-выражение* **||** *логическое и-выражение*

## <a name="remarks"></a>Remarks

Оператор логического или ( **||** ) возвращает логическое значение true, если один или оба операнда имеют значение true, в противном случае возвращает false. Перед вычислением операнды неявно преобразуются в тип **bool** , а результат имеет тип **bool**. Логическое ИЛИ имеет ассоциативность в направлении слева направо.

Операнды оператора логического ИЛИ не обязаны относиться к одному и тому же типу, однако должны иметь целочисленный тип или тип указателя. В качестве операндов часто используются реляционные выражения и выражения равенства.

В выражении логического ИЛИ сначала полностью вычисляется первый операнд и учитываются все побочные эффекты, и лишь после этого вычисление продолжается.

Второй операнд вычисляется только в том случае, если первый имеет значение false (0). Это исключает необязательное вычисление второго операнда, если выражение логического ИЛИ имеет значение true.

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

В приведенном выше примере, если `x` равно `w`, `y` или `z`, то второй аргумент функции `printf` имеет значение true и код выводит значение 1. В противном случае он возвращает значение false и код выводит значение 0. Как только обнаруживается, что одно из значений равно true, вычисление прекращается.

## <a name="operator-keyword-for-124124"></a>Ключевое слово operator для&#124;&#124;

Оператор **or** является текстовым эквивалентом **||** . Существует два способа доступа к оператору **or** в программах: включите файл заголовка \<iso646. h > или Скомпилируйте с параметром компилятора [/Za](../build/reference/za-ze-disable-language-extensions.md) (отключить расширения языка).

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

## <a name="see-also"></a>См. также раздел

[C++Приоритет и ассоциативность встроенных операторов](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Логические операторы в C](../c-language/c-logical-operators.md)
