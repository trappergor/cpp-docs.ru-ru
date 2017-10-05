---
title: "static_assert | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- C2338
- static_assert_cpp
- static_assert
dev_langs:
- C++
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1428d890fe079c7ac1fce175686e9776f9c21746
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="staticassert"></a>static_assert
Проверяет программное утверждение во время компиляции. Если заданное константное выражение имеет `false`, компилятор выводит указанное сообщение, если таковой имеется и компиляция завершается с ошибкой C2338; в противном случае объявление не имеет силы.  
  
## <a name="syntax"></a>Синтаксис  
  
```   
static_assert( constant-expression, string-literal );  

**Visual Studio 2017 and later:**
static_assert( constant-expression ); 
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`constant-expression`|Целочисленное константное выражение, которое можно преобразовать в логическое значение.<br /><br /> Если вычисленное выражение равно нулю (false), отображается параметр `string-literal` и компиляция завершается с ошибкой. Если выражение не равно нулю (true), то объявление `static_assert` не имеет силы.|  
|`string-literal`|Сообщение, которое отображается, если параметр `constant-expression` равен нулю. Сообщение представляет собой строку символов в [базовый набор символов](../c-language/ascii-character-set.md) компилятора; это, а не [многобайтовых или расширенных символов](../c-language/multibyte-and-wide-characters.md).|  
  
## <a name="remarks"></a>Примечания  
 `constant-expression` Параметр `static_assert` представляет объявление *программное утверждение*. Программное утверждение определяет условие, которое должно выполняться на определенном этапе работы программы. Если условие истинно, то объявление `static_assert` не имеет силы. Если условие ложно, то утверждение не выполняется, компилятор выводит сообщение в параметре `string-literal` и компиляция завершается ошибкой. В Visual Studio 2017 г. и более поздних версиях параметр строковый литерал является необязательным. 
  
 Объявление `static_assert` проверяет программное утверждение во время компиляции. Напротив [assert, макрос, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) макрос проверяет программное утверждение во время выполнения и негативно сказывается на время выполнения пространства или времени. Объявления `static_assert` особенно полезны для отладки шаблонов, так как аргументы шаблонов можно включить в параметр `constant-expression`.  
  
 Когда компилятор встречает объявление `static_assert`, он проверяет его на наличие синтаксических ошибок. Если выражение в параметре `constant-expression` не зависит от параметра шаблона, компилятор вычисляет его сразу. В противном случае компилятор вычисляет значение `constant-expression` при создании экземпляра шаблона. Таким образом, компилятор может вывести одно диагностическое сообщение, когда встретит объявление, а второе — когда будет создавать экземпляр шаблона.  
  
 Ключевое слово `static_assert` можно использовать в области видимости пространства имен, класса или блока. (Хотя ключевое слово `static_assert` и не добавляет в программу новых имен, технически оно является объявлением, поскольку его можно использовать в области видимости пространства имен.)  
  
## <a name="description"></a>Описание  
 В следующем примере объявление `static_assert` имеет область видимости пространства имен. Поскольку компилятору известен размер типа `void *`, выражение вычисляется немедленно.  
  
## <a name="example"></a>Пример  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## <a name="description"></a>Описание  
 В следующем примере объявление `static_assert` имеет область видимости класса. `static_assert` Проверяет, является ли параметр шаблона *обычные старые данные* тип (POD). Компилятор проверяет объявление `static_assert` при объявлении, но не принимает параметр `constant-expression` до тех пор, пока в функции `basic_string` не будет создаваться экземпляр шаблона класса `main()`.  
  
## <a name="example"></a>Пример  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(std::is_pod<CharT>::value,  
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
  
## <a name="description"></a>Описание  
 В следующем примере объявление `static_assert` имеет область видимости блока. Выражение в объявлении `static_assert` проверяет, равен ли размер структуры VMPage размеру страницу в виртуальной памяти системы.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [Утверждение и предоставляемые пользователем сообщения (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [#error директивы (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)   
 [Макрос assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Шаблоны](../cpp/templates-cpp.md)   
 [Набор символов ASCII](../c-language/ascii-character-set.md)   
 [Объявления и определения](declarations-and-definitions-cpp.md)
