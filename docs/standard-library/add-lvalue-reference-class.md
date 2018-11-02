---
title: Класс add_lvalue_reference
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_lvalue_reference
helpviewer_keywords:
- add_lvalue_reference
ms.assetid: 9933afc2-ad0d-465d-98fe-7d547fa3efe2
ms.openlocfilehash: 8dbb4f91da8d7a0bf0a90b3edc4fce2918d52a9b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668550"
---
# <a name="addlvaluereference-class"></a>Класс add_lvalue_reference

Делает из типа ссылку на тип.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct add_lvalue_reference;

template <class T>
using add_lvalue_reference_t = typename add_lvalue_reference<T>::type;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип для изменения.

## <a name="remarks"></a>Примечания

Экземпляр модификатора типа содержит модифицированный тип, который является *T* Если *T* является ссылкой lvalue, в противном случае `T&`.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

using namespace std;
int main()
{
    int val = 0;
    add_lvalue_reference_t<int> p = (int&)val;
    p = p;  // to quiet "unused" warning
    cout << "add_lvalue_reference_t<int> == "
        << typeid(p).name() << endl;

    return (0);
}
```

```Output
add_lvalue_reference_t<int> == int
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс remove_reference](../standard-library/remove-reference-class.md)<br/>
