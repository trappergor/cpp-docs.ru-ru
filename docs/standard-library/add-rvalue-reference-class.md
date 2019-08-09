---
title: Класс add_rvalue_reference
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_rvalue_reference
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
ms.openlocfilehash: 64694f2428c1dd536df4d242a17f3f011cfb290c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456540"
---
# <a name="addrvaluereference-class"></a>Класс add_rvalue_reference

Создает ссылочный тип rvalue параметра-шаблона, если он является типом объекта или функции. В противном случае из-за семантики сворачивания ссылок этот тип является таким же, как параметр шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```

### <a name="parameters"></a>Параметры

*T*\
Тип для изменения.

## <a name="remarks"></a>Примечания

Класс содержит член с именем `type`, который является псевдонимом для типа ссылки rvalue на параметр шаблона *T.* `add_rvalue_reference` Семантика свертывания ссылок подразумевает, что для типов, не являющихся объектами и не являющихся функциями t `T&&` , является *t*. Например, если *T* является ссылочным типом lvalue, `add_rvalue_reference<T>::type` то является ссылочным типом lvalue, а не ссылкой rvalue.

Для удобства \<type_traits > определяет вспомогательный `add_rvalue_reference_t`шаблон, `add_rvalue_reference`который является псевдонимом `type` члена.

## <a name="example"></a>Пример

В данном примере кода используется static_assert, чтобы показать, как ссылочные типы rvalue создаются с помощью `add_rvalue_reference` и `add_rvalue_reference_t`, и что результат `add_rvalue_reference` в ссылочном типе lvalue не является ссылкой rvalue, но сворачивается до ссылочного типа lvalue.

```cpp
// ex_add_rvalue_reference.cpp
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp
#include <type_traits>
#include <iostream>
#include <string>

using namespace std;
int main()
{
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,
        "Expected add_rvalue_reference_t<string> to be string&&");
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,
        "Expected add_rvalue_reference_t<string*> to be string*&&");
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,
        "Expected add_rvalue_reference_t<string&> to be string&");
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,
        "Expected add_rvalue_reference_t<string&&> to be string&&");
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;
    return 0;
}

/*Output:
All static_assert tests of add_rvalue_reference passed.
*/
```

## <a name="requirements"></a>Требования

Заголовок: \<type_traits >

Пространство имен: STD

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[Класс add_lvalue_reference](../standard-library/add-lvalue-reference-class.md)\
[Класс is_rvalue_reference](../standard-library/is-rvalue-reference-class.md)
