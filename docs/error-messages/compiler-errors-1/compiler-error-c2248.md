---
title: Ошибка компилятора C2248 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2248
dev_langs:
- C++
helpviewer_keywords:
- C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e48da84824b2069216c2ab3aca82ea9528251638
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172136"
---
# <a name="compiler-error-c2248"></a>Ошибка компилятора C2248
"*член*": не удается получить доступ к "*access_level*«член объявлен в классе»*класс*"  
  
Члены производного класса не может получить доступ к `private` членов базового класса. Не удается получить доступ к `private` или `protected` члены экземпляров класса.  
  
## <a name="example"></a>Пример  
  
Следующий пример приводит к возникновению ошибки C2248 при закрытый или защищенные члены класса доступны из вне класса. Чтобы устранить эту проблему, не доступа этих членов непосредственно за пределами класса. Используйте открытый член данных и функции-члены для взаимодействия с классом.  
  
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
  
Другая проблема совместимости, предоставляющую C2248 заключается в использовании дружественных шаблонов и специализации. Чтобы устранить эту проблему, объявите дружественной функции шаблона с помощью пустого шаблона параметра список <> или параметры конкретного шаблона.  
  
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
  
Другая проблема совместимости, предоставляющую C2248 при попытке объявления дружественного класса, если класс не является видимым для дружественное объявление в области класса. Чтобы устранить эту проблему, следует предоставьте статус дружественного включающего класса.  
  
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