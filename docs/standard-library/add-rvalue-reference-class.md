---
title: Класс add_rvalue_reference
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_rvalue_reference
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
ms.openlocfilehash: 6d7cc1d45ed3b963de0a0a004c1696ddbf0af440
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623917"
---
# <a name="add_rvalue_reference-class"></a>Класс add_rvalue_reference

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

## <a name="remarks"></a>Комментарии

`add_rvalue_reference`Класс содержит член с именем `type` , который является псевдонимом для типа ссылки rvalue на параметр шаблона *T*. Семантика свертывания ссылок подразумевает, что для типов, не являющихся объектами и не являющихся функциями *t*, `T&&` является *t*. Например, если *T* является ссылочным типом lvalue, `add_rvalue_reference<T>::type` то является ссылочным типом lvalue, а не ссылкой rvalue.

Для удобства \<type_traits> определяет вспомогательный шаблон, `add_rvalue_reference_t` который является псевдонимом `type` члена `add_rvalue_reference` .

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

Заголовок: \<type_traits>

Пространство имен: std

## <a name="see-also"></a>См. также раздел

[<type_traits>](type-traits.md)\
[Класс add_lvalue_reference](add-lvalue-reference-class.md)\
[Класс is_rvalue_reference](is-rvalue-reference-class.md)
