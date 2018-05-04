---
title: 'Оператор разрешения области::: | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '::'
dev_langs:
- C++
helpviewer_keywords:
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- ':: operator'
ms.assetid: fd5de9d3-c716-4e12-bae9-03a16fd79a50
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7caea3a32c0bb983518f7610918c78c8c31c63a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="scope-resolution-operator-"></a>Оператор разрешения области: ::
Оператор разрешения области `::` используется для идентификации и устранения неоднозначности идентификаторов, которые используются в разных областях. Дополнительные сведения об области см. в разделе [область](../cpp/scope-visual-cpp.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
:: identifier  
class-name :: identifier  
namespace :: identifier  
enum class :: identifier  
enum struct :: identifier  
```  
  
## <a name="remarks"></a>Примечания  
 `identifier` может быть переменной, функцией или значением перечисления.  
  
## <a name="with-classes-and-namespaces"></a>С классами и пространствами имен  
 В следующем примере показано, каким образом оператор разрешения области используется с пространствами имен и классами:  
  
```cpp  
namespace NamespaceA{  
    int x;  
    class ClassA {  
    public:  
        int x;  
    };  
}  
  
int main() {  
  
    // A namespace name used to disambiguate  
    NamespaceA::x = 1;  
  
    // A class name used to disambiguate  
    NamespaceA::ClassA a1;  
    a1.x = 2;  
  
}  
  
```  
  
 Оператор разрешения области без квалификатора области применяется к глобальному пространству имен.  
  
```cpp  
namespace NamespaceA{  
    int x;  
}  
  
int x;   
  
int main() {  
    int x;  
  
    // the x in main()  
    x = 0;   
    // The x in the global namespace  
    ::x = 1;   
  
    // The x in the A namespace  
    NamespaceA::x = 2;   
}  
```  
  
 Оператор разрешения области можно использовать для идентификации члена пространства имен или пространства имен, которое определяет пространство имен члена в директиве using. В примере ниже `NamespaceC` можно использовать для указания `ClassB`, даже если `ClassB` был объявлен в пространстве имен `NamespaceB`, поскольку `NamespaceB` было определено в `NamespaceC` с помощью директивы using.  
  
```cpp  
namespace NamespaceB {  
    class ClassB {  
    public:  
        int x;  
    };  
}  
  
namespace NamespaceC{  
    using namespace B;  
  
}  
int main() {  
    NamespaceB::ClassB c_b;  
    NamespaceC::ClassB c_c;  
  
    c_b.x = 3;  
    c_c.x = 4;  
}  
  
```  
  
 Можно использовать цепочки операторов разрешения области. В следующем примере `NamespaceD::NamespaceD1` определяет вложенное пространство имен `NamespaceD1`, а `NamespaceE::ClassE::ClassE1` определяет вложенный класс `ClassE1`.  
  
```cpp  
namespace NamespaceD{  
    namespace NamespaceD1{  
        int x;  
    }  
}  
  
namespace NamespaceE{  
  
    class ClassE{  
    public:  
        class ClassE1{  
        public:  
            int x;  
        };  
    };  
}  
  
int main() {  
    NamespaceD:: NamespaceD1::x = 6;  
    NamespaceE::ClassE::ClassE1 e1;  
    e1.x = 7  ;  
}  
  
```  
  
## <a name="with-static-members"></a>Со статическими членами  
 Оператор разрешения области необходимо использовать для вызова статических членов класса.  
  
```cpp  
class ClassG {  
public:  
    static int get_x() { return x;}  
    static int x;  
};  
  
int ClassG::x = 6;  
  
int main() {  
  
    int gx1 = ClassG::x;  
    int gx2 = ClassG::get_x();   
}  
  
```  
  
## <a name="with-scoped-enumerations"></a>С ограниченными перечислениями  
 Оператор разрешения области также используется со значениями ограниченного перечисления [объявления перечислений](../cpp/enumerations-cpp.md), как показано в следующем примере:  
  
```cpp  
enum class EnumA{  
    First,  
    Second,  
    Third  
};  
  
int main() {  
  
    EnumA enum_value = EnumA::First;  
}  
  
```  
  
## <a name="see-also"></a>См. также  
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Пространства имен](../cpp/namespaces-cpp.md)   