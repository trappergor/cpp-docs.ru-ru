---
title: 'Декларатор ссылки lvalue: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
ms.openlocfilehash: 595f2b683d2abb4cdc8a328dc6e86338ab90f214
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178071"
---
# <a name="lvalue-reference-declarator-amp"></a>Декларатор ссылки lvalue: &amp;

Содержит адрес объекта, но синтаксически ведет себя подобно объекту.

## <a name="syntax"></a>Синтаксис

```
type-id & cast-expression
```

## <a name="remarks"></a>Remarks

Ссылку lvalue можно считать другим именем для объекта. Объявление ссылки lvalue состоит из необязательного списка спецификаторов, за которым следует декларатор ссылки. Ссылка должна быть инициализирована и не может быть изменена.

Любой объект, адрес которого можно преобразовать в некоторый тип указателя, можно также преобразовать в аналогичный ссылочный тип. Например, любой объект, адрес которого можно преобразовать в тип `char *`, можно также преобразовать в тип `char &`.

Не путайте объявления ссылок с использованием [оператора взятия адреса](../cpp/address-of-operator-amp.md). Когда *идентификатору* `&`предшествует тип, например **int** или **char**, *идентификатор* объявляется как ссылка на тип. Если перед *идентификатором* `&`не указан тип, используется оператор взятия адреса.

## <a name="example"></a>Пример

В следующем примере демонстрируется декларатор ссылки путем объявления объекта `Person` и ссылки на этот объект. Поскольку `rFriend` является ссылкой на `myFriend`, при обновлении любой из этих переменных изменяется один и тот же объект.

```cpp
// reference_declarator.cpp
// compile with: /EHsc
// Demonstrates the reference declarator.
#include <iostream>
using namespace std;

struct Person
{
    char* Name;
    short Age;
};

int main()
{
   // Declare a Person object.
   Person myFriend;

   // Declare a reference to the Person object.
   Person& rFriend = myFriend;

   // Set the fields of the Person object.
   // Updating either variable changes the same object.
   myFriend.Name = "Bill";
   rFriend.Age = 40;

   // Print the fields of the Person object to the console.
   cout << rFriend.Name << " is " << myFriend.Age << endl;
}
```

```Output
Bill is 40
```

## <a name="see-also"></a>См. также раздел

[Справочные материалы](../cpp/references-cpp.md)<br/>
[Аргументы функции ссылочного типа](../cpp/reference-type-function-arguments.md)<br/>
[Возвращаемые значения функции ссылочного типа](../cpp/reference-type-function-returns.md)<br/>
[Ссылки на указатели](../cpp/references-to-pointers.md)
