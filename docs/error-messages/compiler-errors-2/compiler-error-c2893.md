---
title: Ошибка компилятора C2893 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2893
dev_langs:
- C++
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73d4f838f030db3667b08295006c2ea1df94c87b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026183"
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