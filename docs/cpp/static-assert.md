---
title: static_assert
ms.date: 07/29/2019
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: 4ac79c23379dd1bf1c85521fdf0c28947d3b7ab9
ms.sourcegitcommit: 20a1356193fbe0ddd1002e798b952917eafc3439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661583"
---
# <a name="staticassert"></a>static_assert

Проверяет программное утверждение во время компиляции. Если указанное константное выражение имеет значение FALSE, компилятор отображает указанное сообщение, если оно предоставлено, и компиляция завершается ошибкой C2338; в противном случае объявление не будет действовать.

## <a name="syntax"></a>Синтаксис

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // C++17 (Visual Studio 2017 and later)
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*константное выражение*|Целочисленное константное выражение, которое можно преобразовать в логическое значение.<br /><br /> Если вычисленное выражение равно нулю (false), то отображается параметр строкового литерала и компиляция завершается ошибкой. Если выражение не равно нулю (true), объявление **static_assert** не оказывает никакого влияния.|
|*string-literal*|Сообщение, которое отображается, если параметр *константного выражения* равен нулю. Сообщение представляет собой строку символов в [базовой кодировке](../c-language/ascii-character-set.md) компилятора; то есть не многобайтовые [или расширенные символы](../c-language/multibyte-and-wide-characters.md).|

## <a name="remarks"></a>Примечания

Параметр *константа-Expression* объявления **static_assert** представляет *программное утверждение*. Программное утверждение определяет условие, которое должно выполняться на определенном этапе работы программы. Если условие истинно, объявление **static_assert** не оказывает никакого влияния. Если условие имеет значение false, то утверждение не выполняется, компилятор отображает сообщение в параметре *строки-литерала* , и компиляция завершается ошибкой. В Visual Studio 2017 и более поздних версиях параметр строкового литерала является необязательным.

Объявление **static_assert** тестирует утверждение программного обеспечения во время компиляции. В отличие от этого, [макросы Assert и функции _ASSERT и _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) проверяют программное утверждение во время выполнения и вызывают затраты времени выполнения в пространстве или времени. Объявление **static_assert** особенно полезно для отладки шаблонов, так как аргументы шаблона могут быть добавлены в параметр *константного выражения* .

Компилятор проверяет объявление **static_assert** для синтаксических ошибок при обнаружении объявления. Компилятор вычисляет параметр константного *выражения* немедленно, если он не зависит от параметра шаблона. В противном случае компилятор вычисляет параметр *константного выражения* при создании экземпляра шаблона. Таким образом, компилятор может вывести одно диагностическое сообщение, когда встретит объявление, а второе — когда будет создавать экземпляр шаблона.

Ключевое слово **static_assert** можно использовать в пространстве имен, класса или области блока. (Ключевое слово **static_assert** является техническим объявлением, хотя оно не вводит новое имя в программу, так как оно может использоваться в области видимости пространства имен.)

## <a name="description"></a>Описание

В следующем примере объявление **static_assert** имеет область пространства имен. Поскольку компилятору известен размер типа `void *`, выражение вычисляется немедленно.

## <a name="example"></a>Пример

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description"></a>Описание

В следующем примере объявление **static_assert** имеет область класса. **Static_assert** проверяет, является ли параметр шаблона *обычным старым типом данных* (Pod). Компилятор проверяет объявление **static_assert** при его объявлении, но не вычисляет `basic_string` параметр константного выражения, пока не будет создан экземпляр шаблона класса в. `main()`

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

## <a name="description"></a>Описание

В следующем примере объявление **static_assert** имеет область видимости блока. **Static_assert** проверяет, что размер структуры вмпаже равен виртуальной памяти PageSize системы.

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

[Утверждение и сообщения об ошибках, предоставленные пользователем (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
[Директива #error (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[Макрос assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[Шаблоны](../cpp/templates-cpp.md)<br/>
[Набор символов ASCII](../c-language/ascii-character-set.md)<br/>
[Объявления и определения](declarations-and-definitions-cpp.md)