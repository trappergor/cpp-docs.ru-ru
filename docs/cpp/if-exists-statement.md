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
ms.openlocfilehash: 609d576c6ab3eddca569ed4f19a4024b47b6a1d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374155"
---
# <a name="__if_exists-statement"></a>Оператор __if_exists

В **__if_exists** выписке проверяется, существует ли указанный идентификатор. Если идентификатор существует, выполняется определенный блок операторов.

## <a name="syntax"></a>Синтаксис

```
__if_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Идентификатор*|Идентификатор, наличие которого требуется проверить.|
|*Заявления*|Одна или несколько инструкций для выполнения, если *идентификатор* существует.|

## <a name="remarks"></a>Remarks

> [!CAUTION]
> Для достижения наиболее надежных результатов используйте **__if_exists** заявление под следующими ограничениями.

- Примените **__if_exists** заявление только к простым типам, а не к шаблонам.

- Примените **__if_exists** заявление к идентификаторам как внутри, так и за пределами класса. Не применяйте **__if_exists** заявление к локальным переменным.

- Используйте **__if_exists** заявление только в теле функции. Вне тела функции, **__if_exists** заявление может проверить только полностью определенные типы.

- При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.

Дополнением к **заявлению __if_exists** является [заявление __if_not_exists.](../cpp/if-not-exists-statement.md)

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

## <a name="output"></a>Выходные данные

```Output
In X<T>::Dump()
In A::Dump()
In X<T>::Dump()
T::Dump does not exist
g_bFlag = 1
C::f exists
```

## <a name="see-also"></a>См. также раздел

[Инструкции выбора](../cpp/selection-statements-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)<br/>
[Заявление __if_not_exists](../cpp/if-not-exists-statement.md)
