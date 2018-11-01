---
title: Класс add_rvalue_reference
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_rvalue_reference
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
ms.openlocfilehash: e5e658f16657c0021b78175e87d122a3accd11eb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443669"
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

*T*<br/>
Тип для изменения.

## <a name="remarks"></a>Примечания

`add_rvalue_reference` Классе имеется член с именем `type`, который является псевдонимом для типа ссылки rvalue к параметру шаблона *T*. Семантика сворачивания ссылок подразумевает, что для типов без объектов и функции, не являющейся *T*, `T&&` — *T*. Например, если *T* является типом ссылки lvalue `add_rvalue_reference<T>::type` является ссылочным типом lvalue, а не ссылкой rvalue.

Для удобства \<type_traits > определяет вспомогательный шаблон `add_rvalue_reference_t`, в котором псевдонимы `type` членом `add_rvalue_reference`.

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

Пространство имен: std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс add_lvalue_reference](../standard-library/add-lvalue-reference-class.md)<br/>
[Класс is_rvalue_reference](../standard-library/is-rvalue-reference-class.md)<br/>
