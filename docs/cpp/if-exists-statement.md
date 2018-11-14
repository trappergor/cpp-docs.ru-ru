---
title: Оператор __if_exists
ms.date: 11/04/2016
f1_keywords:
- __if_exists_cpp
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
ms.openlocfilehash: 9d5a0b24bb08a9485b2d212058fa8f0bd82e5842
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326632"
---
# <a name="ifexists-statement"></a>Оператор __if_exists

**__If_exists** инструкции проверяет, является ли указанный идентификатор существует. Если идентификатор существует, выполняется определенный блок операторов.

## <a name="syntax"></a>Синтаксис

```
__if_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*identifier*|Идентификатор, наличие которого требуется проверить.|
|*Инструкции*|Один или несколько операторов для выполнения, если *идентификатор* существует.|

## <a name="remarks"></a>Примечания

> [!CAUTION]
>  Для достижения самых надежных результатов используйте **__if_exists** инструкции с учетом следующих ограничений.

- Применить **__if_exists** инструкцию, чтобы только простые типы, не шаблоны.

- Применить **__if_exists** инструкции к идентификаторам как внутри, так и вне класса. Не устанавливайте **__if_exists** инструкции для локальных переменных.

- Используйте **__if_exists** инструкции только в теле функции. За пределами тела функции **__if_exists** инструкция может проверять только полностью определенные типы.

- При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.

Дополнением к **__if_exists** инструкция является [__if_not_exists](../cpp/if-not-exists-statement.md) инструкции.

## <a name="example"></a>Пример

Обратите внимание, что в этом примере используются шаблоны, что не рекомендуется.

```cpp
// the__if_exists_statement.cpp
// compile with: /EHsc
#include <iostream>

template<typename T>
class X : public T {
public:
   void Dump() {
      std::cout << "In X<T>::Dump()" << std::endl;

      __if_exists(T::Dump) {
         T::Dump();
      }

      __if_not_exists(T::Dump) {
         std::cout << "T::Dump does not exist" << std::endl;
      }
   }
};

class A {
public:
   void Dump() {
      std::cout << "In A::Dump()" << std::endl;
   }
};

class B {};

bool g_bFlag = true;

class C {
public:
   void f(int);
   void f(double);
};

int main() {
   X<A> x1;
   X<B> x2;

   x1.Dump();
   x2.Dump();

   __if_exists(::g_bFlag) {
      std::cout << "g_bFlag = " << g_bFlag << std::endl;
   }

   __if_exists(C::f) {
      std::cout << "C::f exists" << std::endl;
   }

   return 0;
}
```

## <a name="output"></a>Вывод

```Output
In X<T>::Dump()
In A::Dump()
In X<T>::Dump()
T::Dump does not exist
g_bFlag = 1
C::f exists
```

## <a name="see-also"></a>См. также

[Операторы выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор __if_not_exists](../cpp/if-not-exists-statement.md)