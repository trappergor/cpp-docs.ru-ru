---
title: Оператор const_cast
ms.date: 11/04/2016
f1_keywords:
- const_cast_cpp
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
ms.openlocfilehash: 389ef84149031fd602ff9ded15d34869258ffd52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613997"
---
# <a name="constcast-operator"></a>Оператор const_cast

Удаляет **const**, **volatile**, и **__unaligned** атрибуты из класса.

## <a name="syntax"></a>Синтаксис

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>Примечания

Указатель на объект любого типа или указатель на данные-член можно явно преобразовать в тип, идентичны, за исключением **const**, **volatile**, и **__unaligned** квалификаторы. Для указателей и ссылок результат будет указывать на исходный объект. Для указателей на данные-члены результат будет указывать на тот же член, что и исходный указатель (uncast) на данные-член. В зависимости от типа объекта, на который осуществляется ссылка, операция записи с помощью результирующего указателя, ссылки или указателя на данные-член может привести к неопределенному поведению.

Нельзя использовать **const_cast** оператор для непосредственного переопределения постоянного состояния константной переменной.

**Const_cast** оператор преобразует значение пустого указателя в значение пустого указателя конечного типа.

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

В строке, содержащей **const_cast**, тип данных **это** указатель находится `const CCTest *`. **Const_cast** оператор изменяет тип данных **это** указатель на `CCTest *`, позволяя член `number` изменяемой. Приведение выполняется только для оставшейся части оператора, в котором оно указано.

## <a name="see-also"></a>См. также

[Операторы приведения](../cpp/casting-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)