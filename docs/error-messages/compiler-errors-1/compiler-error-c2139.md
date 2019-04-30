---
title: Ошибка компилятора C2139
ms.date: 11/04/2016
f1_keywords:
- C2139
helpviewer_keywords:
- C2139
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
ms.openlocfilehash: 15813216399c0f00fea036cd95443235e7acf4c3
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344904"
---
# <a name="compiler-error-c2139"></a>Ошибка компилятора C2139

«Тип»: неопределенный класс не допускается в качестве аргумента в характеристике внутреннего типа компилятора «характеристика»

Признак типа передан недопустимый аргумент.

Дополнительные сведения см. в разделе [поддержка характеристик типов компилятором](../../extensions/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C2139.

```
// C2139.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T>
struct is_polymorphic {
   static const bool value = __is_polymorphic(T);
};

class C;
class D {};

class E {
public:
   virtual void Test() {}
};

int main() {
   cout << is_polymorphic<C>::value << endl;   // C2139
   cout << is_polymorphic<D>::value << endl;   // OK
   cout << is_polymorphic<E>::value << endl;   // OK
}
```