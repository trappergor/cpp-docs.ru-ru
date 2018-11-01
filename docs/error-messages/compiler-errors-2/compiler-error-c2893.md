---
title: Ошибка компилятора C2893
ms.date: 11/04/2016
f1_keywords:
- C2893
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
ms.openlocfilehash: f1fad1ad18af54945ef32dadaac50a6de4dbd62f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455189"
---
# <a name="compiler-error-c2893"></a>Ошибка компилятора C2893

Сбой при специализации шаблона функции «имя шаблона»

Сбой при специализации шаблона функции компилятор. Может быть множество причин этой ошибки.

Как правило способ устранить ошибку C2893 — просмотрите сигнатуру функции и убедитесь, что можно создать экземпляр любого типа.

## <a name="example"></a>Пример

C2893 происходит потому, что `f`на параметр шаблона `T` должен был быть `std::map<int,int>`, но `std::map<int,int>` не имеет члена `data_type` (`T::data_type` не может быть создан при помощи `T = std::map<int,int>`.). Следующий пример приводит к возникновению ошибки C2893.

```
// C2893.cpp
// compile with: /c /EHsc
#include<map>
using namespace std;
class MyClass {};

template<class T>
inline typename T::data_type
// try the following line instead
// inline typename  T::mapped_type
f(T const& p1, MyClass const& p2);

template<class T>
void bar(T const& p1) {
    MyClass r;
    f(p1,r);   // C2893
}

int main() {
   map<int,int> m;
   bar(m);
}
```