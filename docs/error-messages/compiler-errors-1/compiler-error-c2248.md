---
title: Ошибка компилятора C2248
ms.date: 11/04/2016
f1_keywords:
- C2248
helpviewer_keywords:
- C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
ms.openlocfilehash: 843676638037aab9544f1fbd8c5c6d56d351e485
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206562"
---
# <a name="compiler-error-c2248"></a>Ошибка компилятора C2248

"*член*": не удается получить доступ к члену "*access_level*", объявленному в классе "*класс*"

Члены производного класса не могут получить доступ к членам `private` базового класса. Доступ к `private` или `protected` членам экземпляров класса невозможен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2248, когда доступ к закрытым или защищенным членам класса осуществляется извне класса. Чтобы устранить эту проблему, не следует обращаться к этим членам непосредственно за пределами класса. Используйте открытые данные элементов и функции элементов для взаимодействия с классом.

```cpp
// C2248_access.cpp
// compile with: cl /EHsc /W4 C2248_access.cpp
#include <stdio.h>

class X {
public:
    int  m_publicMember;
    void setPrivateMember( int i ) {
        m_privateMember = i;
        printf_s("\n%d", m_privateMember);
    }
protected:
    int  m_protectedMember;

private:
    int  m_privateMember;
} x;

int main() {
    x.m_publicMember = 4;
    printf_s("\n%d", x.m_publicMember);
    x.m_protectedMember = 2; // C2248 m_protectedMember is protected
    x.m_privateMember = 3;   // C2248  m_privMemb is private
    x.setPrivateMember(0);   // OK uses public access function
}
```

Еще одна ошибка соответствия, предоставляющая C2248, — это использование друзей и специализации шаблонов. Чтобы устранить эту проблему, объявите дружественные функции шаблонов с помощью пустого списка параметров шаблона < > или конкретных параметров шаблона.

```cpp
// C2248_template.cpp
// compile with: cl /EHsc /W4 C2248_template.cpp
template<class T>
void f(T t) {
    t.i;   // C2248
}

struct S {
private:
    int i;

public:
    S() {}
    friend void f(S);   // refer to the non-template function void f(S)
    // To fix, comment out the previous line and
    // uncomment the following line.
    // friend void f<S>(S);
};

int main() {
    S s;
    f<S>(s);
}
```

Еще одна ошибка соответствия, предоставляющая C2248, — это то, что вы пытаетесь объявить дружественный класс и если класс невидим для дружественного объявления в области класса. Чтобы устранить эту проблему, предоставьте дружественный доступ к включающему классу.

```cpp
// C2248_enclose.cpp
// compile with: cl /W4 /c C2248_enclose.cpp
class T {
    class S {
        class E {};
    };
    friend class S::E;   // C2248
};

class A {
    class S {
        class E {};
        friend class A;  // grant friendship to enclosing class
    };
    friend class S::E;   // OK
};
```
