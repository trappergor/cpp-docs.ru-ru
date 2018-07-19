---
title: static_assert | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- static_assert_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc51fab2dade4c6bed0456dd353258df82722de5
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944753"
---
# <a name="staticassert"></a>static_assert
Проверяет программное утверждение во время компиляции. Если заданное константное выражение имеет значение FALSE, компилятор отображает заданное сообщение, если он указан, и компиляция завершается с ошибкой C2338; в противном случае объявление не оказывает влияния.  
  
## <a name="syntax"></a>Синтаксис  
  
```   
static_assert( constant-expression, string-literal );  

**Visual Studio 2017 and later:**
static_assert( constant-expression ); 
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`constant-expression`|Целочисленное константное выражение, которое можно преобразовать в логическое значение.<br /><br /> Если вычисленное выражение равно нулю (false), отображается параметр `string-literal` и компиляция завершается с ошибкой. Если выражение имеет ненулевое значение (true), **static_assert** объявление не имеет силы.|  
|`string-literal`|Сообщение, которое отображается, если параметр `constant-expression` равен нулю. Сообщение представляет собой строку символов в [базовый набор символов](../c-language/ascii-character-set.md) компилятора; это, а не [многобайтовых или расширенных символов](../c-language/multibyte-and-wide-characters.md).|  
  
## <a name="remarks"></a>Примечания  
 `constant-expression` Параметр **static_assert** представляет объявление *программное утверждение*. Программное утверждение определяет условие, которое должно выполняться на определенном этапе работы программы. Если условие имеет значение true, **static_assert** объявление не имеет силы. Если условие ложно, то утверждение не выполняется, компилятор выводит сообщение в параметре `string-literal` и компиляция завершается ошибкой. В Visual Studio 2017 и более поздних версиях параметр строковый литерал является необязательным. 
  
 **Static_assert** объявление тестирует утверждение программного обеспечения во время компиляции. Напротив [макрос assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) макрос проверяет программное утверждение во время выполнения и сказывается на время выполнения в пространства или времени. **Static_assert** объявление является особенно полезны для отладки шаблонов, так как аргументы шаблона могут быть включены в `constant-expression` параметра.  
  
 Компилятор проверяет **static_assert** объявление наличие синтаксических ошибок, при обнаружении объявления. Если выражение в параметре `constant-expression` не зависит от параметра шаблона, компилятор вычисляет его сразу. В противном случае компилятор вычисляет значение `constant-expression` при создании экземпляра шаблона. Таким образом, компилятор может вывести одно диагностическое сообщение, когда встретит объявление, а второе — когда будет создавать экземпляр шаблона.  
  
 Можно использовать **static_assert** ключевое слово в пространство имен, класс или область видимости блока. ( **Static_assert** ключевое слово является технически объявлением, несмотря на то, что он не вводит новое имя в вашу программу, так как он может использоваться в пределах пространства имен.)  
  
## <a name="description"></a>Описание:  
 В следующем примере **static_assert** объявление содержит область видимости пространства имен. Поскольку компилятору известен размер типа `void *`, выражение вычисляется немедленно.  
  
## <a name="example"></a>Пример  
  
```cpp 
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## <a name="description"></a>Описание:  
 В следующем примере **static_assert** объявление имеет область видимости класса. **Static_assert** проверяет, является ли параметр шаблона *обычные старые данные* тип (POD). Компилятор проверяет **static_assert** объявление, когда он объявлен, но не вычисляет `constant-expression` параметр до `basic_string` класс шаблона создается в `main()`.  
  
## <a name="example"></a>Пример  
  
```cpp 
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
  
## <a name="description"></a>Описание:  
 В следующем примере **static_assert** объявление имеет область видимости блока. **Static_assert** проверяет, является ли размер структуры vmpage размеру страницу равным pagesize виртуальной памяти системы.  
  
## <a name="example"></a>Пример  
  
```cpp 
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
 [Директива #error (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)   
 [Макрос assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Шаблоны](../cpp/templates-cpp.md)   
 [Набор символов ASCII](../c-language/ascii-character-set.md)   
 [Объявления и определения](declarations-and-definitions-cpp.md)