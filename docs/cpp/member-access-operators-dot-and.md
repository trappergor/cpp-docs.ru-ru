---
title: Операторы доступа к членам:. и -&gt; | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- .
- ->
dev_langs:
- C++
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c02183b3dc03c785ef5a6a08da80dd8435288b0a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112776"
---
# <a name="member-access-operators--and--gt"></a>Операторы доступа к членам:. и -&gt;

## <a name="syntax"></a>Синтаксис

```
postfix-expression . name
postfix-expression -> name
```

## <a name="remarks"></a>Примечания

Операторы доступа к членам **.** и **->** используются для обращения к членам структур, объединений и классов. Выражения доступа к членам имеют значение и тип выбранного члена.

Предусмотрено две формы выражения доступа к члену:

1. В первой форме *Постфиксное выражение* представляет значение типа структуры, класса или типа объединения, и *имя* именует член указанной структуры, объединения или класса. Значение операции совпадает с *имя* и является l значением, если *Постфиксное выражение* является l значением.

1. Во второй форме *Постфиксное выражение* представляет указатель на структуру, объединение или класс, и *имя* именует член указанной структуры, объединения или класса. Значение совпадает с *имя* и является l значением. **->** Оператор разыменовывает указатель. Поэтому выражения `e->member` и `(*e).member` (где *e* представляет указатель) дают одинаковые результаты (кроме случая, когда операторы **->** или <strong>\*</strong> являются перегруженными).

## <a name="example"></a>Пример

В следующем примере показаны обе формы оператора доступа к членам.

```cpp
// expre_Selection_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

struct Date {
   Date(int i, int j, int k) : day(i), month(j), year(k){}
   int month;
   int day;
   int year;
};

int main() {
   Date mydate(1,1,1900);
   mydate.month = 2;
   cout  << mydate.month << "/" << mydate.day
         << "/" << mydate.year << endl;

   Date *mydate2 = new Date(1,1,2000);
   mydate2->month = 2;
   cout  << mydate2->month << "/" << mydate2->day
         << "/" << mydate2->year << endl;
   delete mydate2;
}
```

```Output
2/1/1900
2/1/2000
```

## <a name="see-also"></a>См. также

[Постфиксные выражения](../cpp/postfix-expressions.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Классы и структуры](../cpp/classes-and-structs-cpp.md)<br/>
[Члены структур и объединений](../c-language/structure-and-union-members.md)