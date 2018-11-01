---
title: Ошибка компилятора C2797
ms.date: 11/04/2016
f1_keywords:
- C2797
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
ms.openlocfilehash: 8ae8c4b8755e6f9c89c0706b0644f220761bd9c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616246"
---
# <a name="compiler-error-c2797"></a>Ошибка компилятора C2797

(Устарело) Инициализация списка внутри списка инициализатора членов или инициализатора нестатических данных не реализован.

Это предупреждение является устаревшим в Visual Studio 2015. В Visual Studio 2013 и более ранних версиях компилятор Visual C++ не реализует инициализация списка внутри список инициализации членов или инициализатор члена нестатических данных. До Visual Studio 2013 Update 3 в таких случаях инициализация автоматически преобразовывалась в вызов функции, что могло приводить к получению неверного кода. В Visual Studio 2013 Update 3 в таких случаях выводится ошибка.

Этот пример создает C2797:

```
#include <vector>
struct S {
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'

    std::vector<int> v1;
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'
};

```

Этот пример также создает C2797:

```
struct S1 {
    int i;
};

struct S2 {
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664
    S1 s1;
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664
};

```

Чтобы устранить эту проблему, используйте явное создание внутренних списков. Например:

```
#include <vector>
typedef std::vector<int> Vector;
struct S {
    S() : v1(Vector{1}) {}

    Vector v1;
    Vector v2 = Vector{1, 2};
};

```

Если инициализация списка не требуется:

```
struct S {
    S() : s1("") {}

    std::string s1;
    std::string s2 = std::string("");
};

```

(Компилятор в Visual Studio 2013 делает это неявным образом во всех версиях до Visual Studio 2013 Update 3.)