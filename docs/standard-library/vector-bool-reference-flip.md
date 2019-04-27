---
title: vector&lt;bool&gt;::reference::flip
ms.date: 11/04/2016
f1_keywords:
- vector/std::vector<bool>::reference::flip
helpviewer_keywords:
- reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
ms.openlocfilehash: 68172de6e50a599d5b1822b83787be3a3a94e037
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205129"
---
# <a name="vectorltboolgtreferenceflip"></a>vector&lt;bool&gt;::reference::flip

Инвертирует логическое значение для элемента вектора [vector\<bool>](../standard-library/vector-bool-class.md) по ссылке.

## <a name="syntax"></a>Синтаксис

```cpp
void flip();
```

## <a name="example"></a>Пример

```cpp
// vector_bool_ref_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    cout << "The vector is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vector<bool>::reference vbref = vb.front();
    vbref.flip();

    cout << "The vector with first element flipped is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

## <a name="output"></a>Вывод

```Output
The vector is:
    true false false true true
The vector with first element flipped is:
    false false false true true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<vector>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[вектор\<bool >:: ссылаться на класс](../standard-library/vector-bool-reference-class.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
