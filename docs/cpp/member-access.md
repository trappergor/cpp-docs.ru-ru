---
title: Доступ к членам
ms.date: 11/04/2016
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
ms.openlocfilehash: 34527f818b135fd5af629ebb69feaffd03b715fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617302"
---
# <a name="member-access"></a>Доступ к членам

Доступ к членам класса можно управлять путем перегрузки оператора доступа члена (**->**). В данном случае этот оператор считается унарным оператором, и функция перегруженного оператора должна быть функцией-членом класса. Поэтому объявление такой функции выглядит следующим образом.

## <a name="syntax"></a>Синтаксис

```
class-type *operator->()
```

## <a name="remarks"></a>Примечания

где *типа класса* — это имя класса, к которому принадлежит этот оператор. Функция оператора доступа к члену должна быть нестатической функцией-членом.

Этот оператор используется (часто вместе с оператором разыменования указателя) для реализации интеллектуальных указателей, которые проверяют указатели до разыменования или подсчета.

Языковой элемент **.** оператор доступа к члену не могут быть перегружены.

## <a name="see-also"></a>См. также

[Перегрузка операторов](../cpp/operator-overloading.md)