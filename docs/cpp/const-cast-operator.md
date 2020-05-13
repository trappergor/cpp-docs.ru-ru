---
title: Оператор const_cast
ms.date: 11/04/2016
f1_keywords:
- const_cast_cpp
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
ms.openlocfilehash: d2711142e4aa73cc0119949876e7e593067cd45d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180346"
---
# <a name="const_cast-operator"></a>Оператор const_cast

Удаляет атрибуты **const**, **volatile**и **__unaligned** из класса.

## <a name="syntax"></a>Синтаксис

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>Remarks

Указатель на любой тип объекта или указатель на член данных можно явно преобразовать в тип, идентичный, за исключением квалификаторов **const**, **volatile**и **__unaligned** . Для указателей и ссылок результат будет указывать на исходный объект. Для указателей на данные-члены результат будет указывать на тот же член, что и исходный указатель (uncast) на данные-член. В зависимости от типа объекта, на который осуществляется ссылка, операция записи с помощью результирующего указателя, ссылки или указателя на данные-член может привести к неопределенному поведению.

Оператор **const_cast** нельзя использовать для непосредственного переопределения состояния константы константной переменной.

Оператор **const_cast** преобразует нулевое значение указателя в значение указателя null целевого типа.

## <a name="example"></a>Пример

```cpp
// expre_const_cast_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CCTest {
public:
   void setNumber( int );
   void printNumber() const;
private:
   int number;
};

void CCTest::setNumber( int num ) { number = num; }

void CCTest::printNumber() const {
   cout << "\nBefore: " << number;
   const_cast< CCTest * >( this )->number--;
   cout << "\nAfter: " << number;
}

int main() {
   CCTest X;
   X.setNumber( 8 );
   X.printNumber();
}
```

В строке, содержащей **const_cast**, тип данных **этого** указателя `const CCTest *`. Оператор **const_cast** изменяет тип **данных указателя на** `CCTest *`, позволяя изменять `number` элементов. Приведение выполняется только для оставшейся части оператора, в котором оно указано.

## <a name="see-also"></a>См. также раздел

[Операторы приведения](../cpp/casting-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
