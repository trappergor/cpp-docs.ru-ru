---
title: "Поддержка характеристик типов компилятором (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__is_simple_value_class"
  - "__has_trivial_destructor"
  - "__has_assign"
  - "__is_union"
  - "__is_class"
  - "__is_abstract"
  - "__has_trivial_assign"
  - "__has_virtual_destructor"
  - "__is_ref_array"
  - "__is_base_of"
  - "__has_copy"
  - "__is_polymorphic"
  - "__has_nothrow_constructor"
  - "__is_ref_class"
  - "__is_delegate"
  - "__is_convertible_to"
  - "__is_value_class"
  - "__is_interface_class"
  - "__has_nothrow_copy"
  - "__is_sealed"
  - "__has_trivial_constructor"
  - "__has_trivial_copy"
  - "__is_enum"
  - "__has_nothrow_assign"
  - "__has_finalizer"
  - "__is_empty"
  - "__is_pod"
  - "__has_user_destructor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__is_class - ключевое слово [C++]"
  - "__is_pod - ключевое слово [C++]"
  - "__is_delegate - ключевое слово [C++]"
  - "__is_value_class - ключевое слово [C++]"
  - "__has_copy - ключевое слово [C++]"
  - "__has_nothrow_copy - ключевое слово [C++]"
  - "__is_interface_class - ключевое слово [C++]"
  - "__is_sealed - ключевое слово [C++]"
  - "__is_convertible_to - ключевое слово [C++]"
  - "__is_ref_class - ключевое слово [C++]"
  - "__has_trivial_copy - ключевое слово [C++]"
  - "__has_user_destructor - ключевое слово [C++]"
  - "__is_abstract - ключевое слово [C++]"
  - "__is_empty - ключевое слово [C++]"
  - "__has_trivial_assign - ключевое слово [C++]"
  - "__has_nothrow_constructor - ключевое слово [C++]"
  - "__is_ref_array - ключевое слово [C++]"
  - "__is_base_of - ключевое слово [C++]"
  - "__has_nothrow_assign - ключевое слово [C++]"
  - "__has_virtual_destructor - ключевое слово [C++]"
  - "__has_finalizer - ключевое слово [C++]"
  - "__is_union - ключевое слово [C++]"
  - "__has_assign - ключевое слово [C++]"
  - "__has_trivial_destructor - ключевое слово [C++]"
  - "__is_polymorphic - ключевое слово [C++]"
  - "__is_enum - ключевое слово [C++]"
  - "__is_simple_value_class - ключевое слово [C++]"
  - "__has_trivial_constructor - ключевое слово [C++]"
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Поддержка характеристик типов компилятором (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Компилятор поддерживает *Введите признаков*, представляющие различные характеристики типа во время компиляции.  
  
## <a name="all-runtimes"></a>Все среды выполнения  
 **Примечания**  
  
 Признаки типов особенно важны для программистов, создающих библиотеки.  
  
 Ниже перечислены признаки типов, поддерживаемые компилятором. Если условие, заданное по имени признака типа, не выполняется, все признаки типов возвращают значение `false`.  
  
 (В следующем списке, примеры кода представлены только в [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]. но соответствующий признак типа также поддерживается в [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)], если не указано иное. Термин "тип платформы" относится к типам [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] или типам среды CLR).  
  
-   `__has_assign(` `type` `)`  
  
     Возвращает значение true, если тип платформы или собственный тип содержит оператор присваивания копии.  
  
    ```  
  
    ref struct R {  
    void operator=(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_assign(R));  
    }  
  
    ```  
  
-   `__has_copy(` `type` `)`  
  
     Возвращает значение true, если тип платформы или собственный тип содержит конструктор копии.  
  
    ```  
  
    ref struct R {  
    R(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_copy(R));  
    }  
  
    ```  
  
-   `__has_finalizer(` `type` `)`  
  
     (В [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] не поддерживается.) Возвращает значение true, если тип CLR содержит метод завершения. В разделе [деструкторы и методы завершения в Visual C++](../misc/destructors-and-finalizers-in-visual-cpp.md) Подробнее.  
  
    ```  
  
    using namespace System;  
    ref struct R {  
    ~R() {}  
    protected:  
    !R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_finalizer(R));  
    }  
  
    ```  
  
-   `__has_nothrow_assign(` `type` `)`  
  
     Возвращает значение true, если оператор присваивания копии имеет пустую спецификацию исключений.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    void operator=(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_constructor(` `type` `)`  
  
     Возвращает значение true, если конструктор по умолчанию имеет пустую спецификацию исключений.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S() throw() {}  
    };  
  
    int main() {  
    __has_nothrow_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_copy(` `type` `)`  
  
     Возвращает значение true, если конструктор копии имеет пустую спецификацию исключений.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_assign(` `type` `)`  
  
     Возвращает значение true, если тип содержит тривиальный оператор присваивания, созданный компилятором.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_constructor(` `type` `)`  
  
     Возвращает значение true, если тип содержит тривиальный конструктор, созданный компилятором.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_copy(` `type` `)`  
  
     Возвращает значение true, если тип содержит тривиальный конструктор копии, созданный компилятором.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_destructor(` `type` `)`  
  
     Возвращает значение true, если тип содержит тривиальный деструктор, созданный компилятором.  
  
    ```  
  
    // has_trivial_destructor.cpp  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_user_destructor(` `type` `)`  
  
     Возвращает значение true, если тип платформы или собственный тип содержит объявленный пользователем деструктор.  
  
    ```  
  
    // has_user_destructor.cpp  
  
    using namespace System;  
    ref class R {  
    ~R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_user_destructor(R));  
    }  
  
    ```  
  
-   `__has_virtual_destructor(` `type` `)`  
  
     Возвращает значение true, если тип содержит виртуальный деструктор.  
  
     Признак `__has_virtual_destructor` также работает с типами платформ, и любой определенный пользователем деструктор в типе платформы является виртуальным деструктором.  
  
    ```  
  
    // has_virtual_destructor.cpp  
    #include <stdio.h>  
    struct S {  
    virtual ~S() {}  
    };  
  
    int main() {  
    __has_virtual_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_abstract(` `type` `)`  
  
     Возвращает значение true, если тип является абстрактным. Дополнительные сведения о собственных абстрактных типах см. в разделе [абстрактный](../windows/abstract-cpp-component-extensions.md).  
  
     Признак `__is_abstract` также работает с типами платформ. Интерфейс хотя бы с одним членом является абстрактным типом, как и ссылочный тип по крайней мере с одним абстрактным членом. Дополнительные сведения об абстрактных типах платформ см. в разделе [абстрактные классы](../cpp/abstract-classes-cpp.md)  
  
    ```  
  
    // is_abstract.cpp  
    #include <stdio.h>  
    struct S {  
    virtual void Test() = 0;  
    };  
  
    int main() {  
    __is_abstract(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_base_of(` `base` `,` `derived` `)`  
  
     Возвращает значение true, если первый тип является базовым классом второго типа или оба типа одинаковы.  
  
     Признак `__is_base_of` также работает с типами платформ. Например, будут возвращать значение true, если первый тип [класс интерфейса](../windows/interface-class-cpp-component-extensions.md) и второй тип реализует интерфейс.  
  
    ```  
  
    // is_base_of.cpp  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    __is_base_of(S, T) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_base_of(S, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_class(` `type` `)`  
  
     Возвращает значение true, если тип является собственным классом или структурой.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_class(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_convertible_to(` `from` `,`  `to` `)`  
  
     Возвращает значение true, если первый тип может быть преобразован во второй.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    S * s = new S;  
    T * t = new T;  
    s = t;  
    __is_convertible_to(T, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_delegate(` `type` `)`  
  
     Возвращает значение true, если `type` — делегат. Дополнительные сведения см. в разделе [делегат (расширения компонентов C++)](../windows/delegate-cpp-component-extensions.md).  
  
    ```  
  
    delegate void MyDel();  
    int main() {  
    System::Console::WriteLine(__is_delegate(MyDel));  
    }  
  
    ```  
  
-   `__is_empty(` `type` `)`  
  
     Возвращает значение true, если тип не содержит данных-членов экземпляра.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    int Test() {}  
    static int i;  
    };  
    int main() {  
    __is_empty(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_enum(` `type` `)`  
  
     Возвращает значение true, если тип является собственным перечислением.  
  
    ```  
  
    // is_enum.cpp  
    #include <stdio.h>  
    enum E { a, b };  
  
    struct S {  
    enum E2 { c, d };  
    };  
  
    int main() {  
    __is_enum(E) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_enum(S::E2) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_interface_class(` `type` `)`  
  
     Возвращает значение true, если передается интерфейс платформы. Дополнительные сведения см. в разделе [класс интерфейса](../windows/interface-class-cpp-component-extensions.md).  
  
    ```  
  
    // is_interface_class.cpp  
  
    using namespace System;  
    interface class I {};  
    int main() {  
    Console::WriteLine(__is_interface_class(I));  
    }  
  
    ```  
  
-   `__is_pod(` `type` `)`  
  
     Возвращает значение true, если тип является классом или объединением без конструктора или закрытых либо защищенных нестатических членов, базовых классов и виртуальных функций. Дополнительные сведения о POD см. в разделах 8.5.1/1, 9/4 и 3.9/10 стандарта C++.  
  
     Для фундаментальных типов признак `__is_pod` возвращает значение false.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_pod(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_polymorphic(` `type` `)`  
  
     Возвращает значение true, если собственный тип содержит виртуальные функции.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    virtual void Test(){}  
    };  
  
    int main() {  
    __is_polymorphic(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_ref_array(` `type` `)`  
  
     Возвращает значение true, если передается массив платформы. Дополнительные сведения см. в разделе [массивы](../windows/arrays-cpp-component-extensions.md).  
  
    ```  
  
    using namespace System;  
    int main() {  
    array<int>^ x = gcnew array<int>(10);  
    Console::WriteLine(__is_ref_array(array<int>));  
    }  
  
    ```  
  
-   `__is_ref_class(` `type` `)`  
  
     Возвращает значение true, если передается ссылочный класс. Дополнительные сведения об определяемых пользователем ссылочных типов см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    int main() {  
    Console::WriteLine(__is_ref_class(Buffer));  
    Console::WriteLine(__is_ref_class(R));  
    }  
  
    ```  
  
-   `__is_sealed(` `type` `)`  
  
     Возвращает значение true, если передается платформа или собственный тип, отмеченный как запечатанный. Дополнительные сведения см. в разделе [запечатанные](../windows/sealed-cpp-component-extensions.md).  
  
    ```  
  
    ref class R sealed{};  
    int main() {  
    System::Console::WriteLine(__is_sealed(R));  
    }  
  
    ```  
  
-   `__is_simple_value_class(` `type` `)`  
  
     Возвращает значение true, если передается тип значения, не содержащий ссылки на кучу со сборкой мусора. Дополнительные сведения о типах значений, определяемых пользователем. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    value struct V {};  
    value struct V2 {  
    R ^ r;   // not a simnple value type  
    };  
  
    int main() {  
    Console::WriteLine(__is_simple_value_class(V));  
    Console::WriteLine(__is_simple_value_class(V2));  
    }  
  
    ```  
  
-   `__is_union(` `type` `)`  
  
     Возвращает значение true, если тип является объединением.  
  
    ```  
  
    #include <stdio.h>  
    union A {  
    int i;  
    float f;  
    };  
  
    int main() {  
    __is_union(A) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_value_class(` `type` `)`  
  
     Возвращает значение true, если передается тип значения. Дополнительные сведения о типах значений, определяемых пользователем. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
  
    value struct V {};  
  
    int main() {  
    System::Console::WriteLine(__is_value_class(V));  
    }  
  
    ```  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Примечания**  
  
  `__has_finalizer(`*Тип*`)` Признак типа не поддерживается, поскольку эта платформа не поддерживает методы завершения.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Примечания**  
  
 (Отсутствуют комментарии для данной возможности в рамках этой платформы).  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/clr**  
  
### <a name="examples"></a>Примеры  
 **Пример**  
  
 В следующем примере кода показано, как использовать шаблон класса для предоставления признака типа компилятора **/CLR** компиляции. Дополнительные сведения см. в разделе [среды выполнения Windows и управляемые шаблоны](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).  
  
```  
// compiler_type_traits.cpp  
// compile with: /clr  
using namespace System;  
  
template <class T>  
ref struct is_class {  
   literal bool value = __is_ref_class(T);  
};  
  
ref class R {};  
  
int main () {  
   if (is_class<R>::value)  
      Console::WriteLine("R is a ref class");  
   else  
      Console::WriteLine("R is not a ref class");  
}  
```  
  
 **Выходные данные**  
  
```Output  
R is a ref class  
```  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)