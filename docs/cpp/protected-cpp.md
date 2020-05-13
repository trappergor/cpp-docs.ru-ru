---
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 79ca081726c1f26a251763e2533ade730f075e2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317270"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>Синтаксис

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>Remarks

**Защищенное** ключевое слово определяет доступ к членам класса в *списке участников* до следующего фактора доступа **(публичного** или **частного)** или конца определения класса. Члены класса, объявленные **защищенными,** могут использоваться только следующими:

- Функции-члены класса, который изначально объявил эти элементы.

- Дружественные элементы класса, который изначально объявил эти элементы.

- Классы, производные с использованием открытого или защищенного доступа от класса, который изначально объявил эти элементы.

- Прямые производные с использованием закрытого доступа классы, которые также имеют закрытый доступ к защищенным элементам.

При предшествующем названию базового **класса, защищенное** ключевое слово указывает, что публичные и защищенные члены базового класса являются защищенными членами его производных классов.

Защищенные члены не являются частными, как **частные** члены, которые доступны только для членов класса, в котором они объявлены, но они не являются публичными, как **общественные** члены, которые доступны в любой функции.

Защищенные члены, которые также объявлены **статичными,** доступны любому другу или функции члена производного класса. Защищенные члены, которые не объявлены **статичными,** доступны друзьям и функциям членов в производном классе только через указатель на, ссылку или объект производного класса.

Для получения соответствующей [public](../cpp/public-cpp.md)информации [private](../cpp/private-cpp.md) [см.](../cpp/friend-cpp.md) [Controlling Access to Class Members](member-access-control-cpp.md)

## <a name="clr-specific"></a>Специально для /clr

В типах CLR ключевые слова для спецификации доступа СЗ **(государственные,** **частные**и **защищенные)** могут влиять на видимость типов и методов в отношении сборок. Для получения дополнительной информации [см.](member-access-control-cpp.md)

> [!NOTE]
> Файлы, компилированные с [помощью /LN,](../build/reference/ln-create-msil-module.md) не подвержены такому поведению. В этом случае все управляемые классы (открытые или закрытые) будут видны.

## <a name="end-clr-specific"></a>КОНЕЦ специально для /clr

## <a name="example"></a>Пример

```cpp
// keyword_protected.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class X {
public:
   void setProtMemb( int i ) { m_protMemb = i; }
   void Display() { cout << m_protMemb << endl; }
protected:
   int  m_protMemb;
   void Protfunc() { cout << "\nAccess allowed\n"; }
} x;

class Y : public X {
public:
   void useProtfunc() { Protfunc(); }
} y;

int main() {
   // x.m_protMemb;         error, m_protMemb is protected
   x.setProtMemb( 0 );   // OK, uses public access function
   x.Display();
   y.setProtMemb( 5 );   // OK, uses public access function
   y.Display();
   // x.Protfunc();         error, Protfunc() is protected
   y.useProtfunc();      // OK, uses public access function
                        // in derived class
}
```

## <a name="see-also"></a>См. также раздел

[Управление доступом к членам классов](member-access-control-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
