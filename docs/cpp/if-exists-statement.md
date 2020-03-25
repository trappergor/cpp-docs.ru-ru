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
ms.openlocfilehash: ea136ac0312b78519fe2d8ea88ace4d8b0d69946
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178422"
---
# <a name="__if_exists-statement"></a>Оператор __if_exists

Оператор **__if_exists** проверяет, существует ли указанный идентификатор. Если идентификатор существует, выполняется определенный блок операторов.

## <a name="syntax"></a>Синтаксис

```
__if_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Параметры

|Параметр|Description|
|---------------|-----------------|
|*identifier*|Идентификатор, наличие которого требуется проверить.|
|*инструкции*|Одна или несколько инструкций для выполнения, если *идентификатор* существует.|

## <a name="remarks"></a>Remarks

> [!CAUTION]
>  Для достижения наиболее достоверных результатов используйте инструкцию **__if_exists** в следующих ограничениях.

- Примените оператор **__if_exists** только к простым типам, а не к шаблонам.

- Примените оператор **__if_exists** к идентификаторам внутри или за пределами класса. Не применяйте оператор **__if_exists** к локальным переменным.

- Используйте оператор **__if_exists** только в теле функции. За пределами тела функции оператор **__if_exists** может проверять только полностью определенные типы.

- При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.

Дополнение к оператору **__if_exists** является оператором [__if_not_exists](../cpp/if-not-exists-statement.md) .

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

[Операторы выбора](../cpp/selection-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Оператор __if_not_exists](../cpp/if-not-exists-statement.md)
