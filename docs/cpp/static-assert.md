---
title: "static_assert | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "C2338"
  - "static_assert_cpp"
  - "static_assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "утверждения [C++], static_assert"
  - "ключевые слова C++, static_assert"
  - "C2338"
  - "static_assert"
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# static_assert
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проверяет программное утверждение во время компиляции.  Если заданное константное выражение имеет значение `false`, то компилятор выводит указанное сообщение и компиляция завершается с ошибкой C2338; в противном случае объявление не имеет силы.  
  
## Синтаксис  
  
```  
static_assert(   
    constant-expression,   
    string-literal   
);  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`constant-expression`|Целочисленное константное выражение, которое можно преобразовать в логическое значение.<br /><br /> Если вычисленное выражение равно нулю \(false\), отображается параметр `string-literal` и компиляция завершается с ошибкой.  Если выражение не равно нулю \(true\), то объявление `static_assert` не имеет силы.|  
|`string-literal`|Сообщение, которое отображается, если параметр `constant-expression` равен нулю.  Это сообщение представляет собой строку символов из [базового набора символов](../c-language/ascii-character-set.md) компилятора \(то есть не содержит [многобайтовых или расширенных символов](../Topic/Multibyte%20and%20Wide%20Characters.md)\).|  
  
## Заметки  
 Параметр `constant-expression` в объявлении `static_assert` представляет собой *программное утверждение*.  Программное утверждение определяет условие, которое должно выполняться на определенном этапе работы программы.  Если условие истинно, то объявление `static_assert` не имеет силы.  Если условие ложно, то утверждение не выполняется, компилятор выводит сообщение в параметре `string-literal` и компиляция завершается ошибкой.  
  
 Объявление `static_assert` проверяет программное утверждение во время компиляции.  В отличие от него, макрос [Макрос assert, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) проверяет утверждения во время выполнения, что замедляет выполнение программы или увеличивает ее размер.  Объявления `static_assert` особенно полезны для отладки шаблонов, так как аргументы шаблонов можно включить в параметр `constant-expression`.  
  
 Когда компилятор встречает объявление `static_assert`, он проверяет его на наличие синтаксических ошибок.  Если выражение в параметре `constant-expression` не зависит от параметра шаблона, компилятор вычисляет его сразу.  В противном случае компилятор вычисляет значение `constant-expression` при создании экземпляра шаблона.  Таким образом, компилятор может вывести одно диагностическое сообщение, когда встретит объявление, а второе — когда будет создавать экземпляр шаблона.  
  
 Ключевое слово `static_assert` можно использовать в области видимости пространства имен, класса или блока. \(Хотя ключевое слово `static_assert` и не добавляет в программу новых имен, технически оно является объявлением, поскольку его можно использовать в области видимости пространства имен.\)  
  
## Описание  
 В следующем примере объявление `static_assert` имеет область видимости пространства имен.  Поскольку компилятору известен размер типа `void *`, выражение вычисляется немедленно.  
  
## Пример  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## Описание  
 В следующем примере объявление `static_assert` имеет область видимости класса.  Выражение в объявлении `static_assert` проверяет, имеет ли параметр шаблона тип *POD*.  Компилятор проверяет объявление `static_assert` при объявлении, но не принимает параметр `constant-expression` до тех пор, пока в функции `main()` не будет создаваться экземпляр шаблона класса `basic_string`.  
  
## Пример  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(tr1::is_pod<CharT>::value,  
                  "Template argument CharT must be a POD type in class template basic_string");  
    // ...  
    };  
}  
struct NonPOD {  
    NonPOD(const NonPOD &) {}  
    virtual ~NonPOD() {}  
};  
int main()  
{  
    std::basic_string<char> bs;  
}  
```  
  
## Описание  
 В следующем примере объявление `static_assert` имеет область видимости блока.  Выражение в объявлении `static_assert` проверяет, равен ли размер структуры VMPage размеру страницу в виртуальной памяти системы.  
  
## Пример  
  
```  
#include <sys/param.h> // defines PAGESIZE  
class VMMClient {  
public:  
    struct VMPage { // ...   
           };  
    int check_pagesize() {  
    static_assert(sizeof(VMPage) == PAGESIZE,  
        "Struct VMPage must be the same size as a system virtual memory page.");  
    // ...  
    }  
// ...  
};  
```  
  
## См. также  
 [Утверждение и сообщения об ошибках, предоставленные пользователем \(C\+\+\)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [Директива \#error](../preprocessor/hash-error-directive-c-cpp.md)   
 [Макрос assert, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Шаблоны](../Topic/Templates%20\(C++\).md)   
 [Набор символов ASCII](../c-language/ascii-character-set.md)   
 [Объявления](../misc/declarations.md)