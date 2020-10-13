---
title: static_assert
ms.date: 07/29/2019
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: bf796b853d21d33d97e25c05101b7486e1eb112f
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008858"
---
# <a name="static_assert"></a>static_assert

Проверяет программное утверждение во время компиляции. Если указанное константное выражение имеет значение **`false`** , компилятор отображает указанное сообщение, если оно предоставлено, и компиляция завершается ошибкой C2338; в противном случае объявление не оказывает никакого влияния.

## <a name="syntax"></a>Синтаксис

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // C++17 (Visual Studio 2017 and later)
```

### <a name="parameters"></a>Параметры

*константное выражение*\
Целочисленное константное выражение, которое можно преобразовать в логическое значение. Если вычисленное выражение равно нулю (false), то отображается параметр *строкового литерала* и компиляция завершается ошибкой. Если выражение не равно нулю (true), **`static_assert`** объявление не оказывает никакого влияния.

*строковый литерал*\
Сообщение, которое отображается, если параметр *константного выражения* равен нулю. Сообщение представляет собой строку символов в [базовой кодировке](../c-language/ascii-character-set.md) компилятора; то есть не [многобайтовые или расширенные символы](../c-language/multibyte-and-wide-characters.md).

## <a name="remarks"></a>Комментарии

Параметр *константного выражения* **`static_assert`** объявления представляет *программное утверждение*. Программное утверждение определяет условие, которое должно выполняться на определенном этапе работы программы. Если условие имеет значение true, **`static_assert`** объявление не оказывает никакого влияния. Если условие имеет значение false, то утверждение не выполняется, компилятор отображает сообщение в параметре *строки-литерала* , и компиляция завершается ошибкой. В Visual Studio 2017 и более поздних версиях параметр строкового литерала является необязательным.

В **`static_assert`** объявлении проверяется программное утверждение во время компиляции. В отличие от этого, [макросы Assert и функции _ASSERT и _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) проверяют программное утверждение во время выполнения и приводят к затратам времени выполнения в пространстве или времени. **`static_assert`** Объявление особенно полезно для отладки шаблонов, так как аргументы шаблона могут быть добавлены в параметр *константного выражения* .

Компилятор проверяет **`static_assert`** объявление на наличие синтаксических ошибок при обнаружении объявления. Компилятор вычисляет параметр *константного выражения* немедленно, если он не зависит от параметра шаблона. В противном случае компилятор вычисляет параметр *константного выражения* при создании экземпляра шаблона. Таким образом, компилятор может вывести одно диагностическое сообщение, когда встретит объявление, а второе — когда будет создавать экземпляр шаблона.

**`static_assert`** Ключевое слово можно использовать в пространстве имен, класса или области видимости блока. ( **`static_assert`** Ключевое слово является техническим объявлением, хотя оно не вводит новое имя в программу, так как оно может использоваться в области видимости пространства имен.)

## <a name="description-of-static_assert-with-namespace-scope"></a>Описание `static_assert` области пространства имен

В следующем примере **`static_assert`** объявление имеет область пространства имен. Поскольку компилятору известен размер типа `void *`, выражение вычисляется немедленно.

## <a name="example-static_assert-with-namespace-scope"></a>Пример: `static_assert` с областью пространства имен

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description-of-static_assert-with-class-scope"></a>Описание `static_assert` с областью видимости класса

В следующем примере **`static_assert`** объявление имеет область класса. **`static_assert`** Проверяет, является ли параметр шаблона *обычным старым типом данных* (Pod). Компилятор проверяет **`static_assert`** объявление при объявлении, но не вычисляет параметр *константного выражения* до тех пор, пока не `basic_string` будет создан экземпляр шаблона класса в `main()` .

## <a name="example-static_assert-with-class-scope"></a>Пример: `static_assert` с областью класса

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

## <a name="description-of-static_assert-with-block-scope"></a>Описание `static_assert` с областью видимости блока

В следующем примере **`static_assert`** объявление имеет область видимости блока. **`static_assert`** Проверяет, равен ли размер структуры вмпаже виртуальной памяти PageSize системы.

## <a name="example-static_assert-at-block-scope"></a>Пример: `static_assert` в области видимости блока

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

## <a name="see-also"></a>См. также статью

[Утверждение и сообщения об ошибках, предоставленные пользователем (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
[Директива #error (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[Макрос assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[Шаблоны](../cpp/templates-cpp.md)<br/>
[Набор символов ASCII](../c-language/ascii-character-set.md)<br/>
[Объявления и определения](declarations-and-definitions-cpp.md)
