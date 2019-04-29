---
title: Ошибка компилятора C2248
ms.date: 11/04/2016
f1_keywords:
- C2248
helpviewer_keywords:
- C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
ms.openlocfilehash: d9b9a6c04e7e9a5d88df516125280b6b23894a01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302558"
---
# <a name="compiler-error-c2248"></a>Ошибка компилятора C2248

"*член*": невозможно получить доступ к "*access_level*«член объявлен в классе»*класс*"

Члены производного класса не может получить доступ к `private` члены базового класса. Не удается получить доступ к `private` или `protected` членами экземпляров класса.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2248 при закрытый или защищенные члены класса доступны из вне класса. Чтобы устранить эту проблему, не обращаться к этим членам непосредственно за пределами класса. Используйте открытый член данных и функции-члены для взаимодействия с классом.

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

Еще одна проблема соответствия, который предоставляет C2248 является использование шаблона друзей и специализации. Чтобы устранить эту проблему, объявите дружественные функции шаблонов с помощью <> списка параметр пустой шаблон или параметры конкретного шаблона.

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

Еще одна проблема соответствия, который предоставляет C2248 при попытке объявления дружественного класса, если класс не является видимым для объявлением дружественной функции в области класса. Чтобы устранить эту проблему, предоставьте статус дружественной сборки, для включающего класса.

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