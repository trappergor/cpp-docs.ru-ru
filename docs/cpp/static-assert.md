---
title: static_assert
ms.date: 07/29/2019
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: a3336e9e41e3dc6804c2398d3ef815ba8c471e50
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160909"
---
# <a name="static_assert"></a>static_assert

Проверяет программное утверждение во время компиляции. Если указанное константное выражение имеет значение FALSE, компилятор отображает указанное сообщение, если оно предоставлено, и компиляция завершается ошибкой C2338; в противном случае объявление не будет действовать.

## <a name="syntax"></a>Синтаксис

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // C++17 (Visual Studio 2017 and later)
```

#### <a name="parameters"></a>Параметры

|Параметр|Description|
|---------------|-----------------|
|*константное выражение*|Целочисленное константное выражение, которое можно преобразовать в логическое значение.<br /><br /> Если вычисленное выражение равно нулю (false), то отображается параметр *строкового литерала* и компиляция завершается ошибкой. Если выражение не равно нулю (true), объявление **static_assert** не действует.|
|*string-literal*|Сообщение, которое отображается, если параметр *константного выражения* равен нулю. Сообщение представляет собой строку символов в [базовой кодировке](../c-language/ascii-character-set.md) компилятора; то есть не [многобайтовые или расширенные символы](../c-language/multibyte-and-wide-characters.md).|

## <a name="remarks"></a>Remarks

Параметр *константа-Expression* объявления **static_assert** представляет *программное утверждение*. Программное утверждение определяет условие, которое должно выполняться на определенном этапе работы программы. Если условие имеет значение true, объявление **static_assert** не действует. Если условие имеет значение false, то утверждение не выполняется, компилятор отображает сообщение в параметре *строки-литерала* , и компиляция завершается ошибкой. В Visual Studio 2017 и более поздних версиях параметр строкового литерала является необязательным.

Объявление **static_assert** тестирует утверждение программного обеспечения во время компиляции. В отличие от этого, [макросы Assert и функции _ASSERT и _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) проверяют программное утверждение во время выполнения и приводят к затратам времени выполнения в пространстве или времени. Объявление **static_assert** особенно полезно для отладки шаблонов, так как аргументы шаблона могут быть добавлены в параметр *константного выражения* .

Компилятор проверяет объявление **static_assert** на наличие синтаксических ошибок при обнаружении объявления. Компилятор вычисляет параметр *константного выражения* немедленно, если он не зависит от параметра шаблона. В противном случае компилятор вычисляет параметр *константного выражения* при создании экземпляра шаблона. Таким образом, компилятор может вывести одно диагностическое сообщение, когда встретит объявление, а второе — когда будет создавать экземпляр шаблона.

Можно использовать ключевое слово **static_assert** в области пространства имен, класса или блока. (Ключевое слово **static_assert** технически является объявлением, хотя оно не вводит новое имя в программу, так как оно может использоваться в области видимости пространства имен.)

## <a name="description"></a>Description

В следующем примере объявление **static_assert** имеет область пространства имен. Поскольку компилятору известен размер типа `void *`, выражение вычисляется немедленно.

## <a name="example"></a>Пример

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description"></a>Description

В следующем примере объявление **static_assert** имеет область класса. **Static_assert** проверяет, является ли параметр шаблона *простым типом данных* (Pod). Компилятор проверяет объявление **static_assert** , когда оно объявлено, но не вычисляет параметр *константного выражения* до тех пор, пока не будет создан экземпляр шаблона класса `basic_string` в `main()`.

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

## <a name="description"></a>Description

В следующем примере объявление **static_assert** имеет область видимости блока. **Static_assert** проверяет, равен ли размер структуры вмпаже виртуальной памяти PageSize системы.

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

## <a name="see-also"></a>См. также раздел

[Утверждение и сообщения об ошибках, предоставленные пользователем (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
[Директива #error (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[Макрос assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[Шаблоны](../cpp/templates-cpp.md)<br/>
[Набор символов ASCII](../c-language/ascii-character-set.md)<br/>
[Объявления и определения](declarations-and-definitions-cpp.md)
