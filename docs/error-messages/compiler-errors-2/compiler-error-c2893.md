---
title: Ошибка компилятора C2893
ms.date: 11/04/2016
f1_keywords:
- C2893
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
ms.openlocfilehash: ca603eb94d5d528a7fed15e0320e1f5d88bf0629
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760880"
---
# <a name="compiler-error-c2893"></a>Ошибка компилятора C2893

Не удалось выполнить специализацию шаблона функции "имя шаблона"

Компилятору не удалось специализацию шаблона функции. Эта ошибка может быть вызвана многими причинами.

Как правило, для устранения ошибки C2893 необходимо проверить сигнатуру функции и убедиться, что вы можете создать экземпляр каждого типа.

## <a name="example"></a>Пример

C2893 происходит из-за того, что параметр шаблона `f``T` выводится как `std::map<int,int>`, но `std::map<int,int>` не имеет `data_type` элемента (`T::data_type` не может быть создан с `T = std::map<int,int>`.). Следующий пример приводит к возникновению ошибки C2893.

```cpp
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
