---
title: Аннотация структур и классов
ms.date: 06/28/2019
ms.topic: conceptual
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
- _Field_z_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
ms.openlocfilehash: fe177e6afea088b59b16bfbd0bff6fa00b526222
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765122"
---
# <a name="annotating-structs-and-classes"></a>Аннотация структур и классов

Вы можете добавить примечание к структурам и членам классов, используя примечания, которые действуют как инварианты — предполагается, что они будут выполнены в любом вызове функции или функции входа и выхода, которая содержит включающую структуру в качестве значения параметров или результатов.

## <a name="struct-and-class-annotations"></a>Заметки структуры и класса

- `_Field_range_(low, high)`

     Поле находится в диапазоне (включительно) от `low` до `high` .  Эквивалент для `_Satisfies_(_Curr_ >= low && _Curr_ <= high)` применяется к аннотированному объекту с помощью соответствующих предусловий или постусловий.

- `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`

     Поле с записываемым размером в элементах (или байтах), как определено в `size`.

- `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`

     Поле с записываемым размером в элементах (или байтах), как определено в `size` и `count` этих элементов (байт), которые доступны для чтения.

- `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`

     Поле с размером в элементах (или байт), доступных для записи и чтения, как определено в `size`.

- `_Field_z_`

     Поле, имеющее строку, завершающуюся нулем.

- `_Struct_size_bytes_(size)`

     Применяется к объявлению структуры или класса.  Указывает, что допустимый объект этого типа может быть больше объявленного типа с количеством байт, указанным в `size`.  Пример:

    ```cpp

    typedef _Struct_size_bytes_(nSize)
    struct MyStruct {
        size_t nSize;
        ...
    };

    ```

     Затем размер буфера в байтах параметра `pM` типа принимает `MyStruct *` значение:

    ```cpp
    min(pM->nSize, sizeof(MyStruct))
    ```

## <a name="example"></a>Например, .

```cpp
#include <sal.h>

// This _Struct_size_bytes_ is equivalent to what below _Field_size_ means.
_Struct_size_bytes_(__builtin_offsetof(MyBuffer, buffer) + bufferSize * sizeof(int))
struct MyBuffer
{
    static int MaxBufferSize;

    _Field_z_
    const char* name;

    int firstField;

    // ... other fields

    _Field_range_(1, MaxBufferSize)
    int bufferSize;

    _Field_size_(bufferSize)        // Preferred way - easier to read and maintain.
    int buffer[]; // Using C99 Flexible array member
};
```

Примечания для этого примера:

- `_Field_z_` равно `_Null_terminated_`.  `_Field_z_` для поля имя указывает, что поле Name является строкой, завершающейся нулем.
- `_Field_range_` для `bufferSize` указывает, что значение `bufferSize` должно находиться в пределах от 1 до `MaxBufferSize` (включительно).
- Конечные результаты `_Struct_size_bytes_` `_Field_size_` заметок и эквивалентны. Для структур или классов, имеющих одинаковый макет, `_Field_size_` проще читать и поддерживать, так как содержит меньше ссылок и вычислений, чем эквивалентная `_Struct_size_bytes_` Аннотация. `_Field_size_` не требует преобразования к размеру в байтах. Если параметр Byte является единственным, например, для поля указателя void, `_Field_size_bytes_` можно использовать. Если оба `_Struct_size_bytes_` и `_Field_size_` существуют, они будут доступны для инструментов. Если две аннотации не согласны, это будет сделано с помощью инструмента.

## <a name="see-also"></a>См. также раздел

- [Использование аннотаций SAL для сокращения количества дефектов в коде C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [Основные сведения о языке SAL](../code-quality/understanding-sal.md)
- [Создание примечаний к параметрам и возвращаемым значениям функций](../code-quality/annotating-function-parameters-and-return-values.md)
- [Аннотация поведения функций](../code-quality/annotating-function-behavior.md)
- [Аннотация поведения блокировки](../code-quality/annotating-locking-behavior.md)
- [Указание времени и места применения примечания](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [Встроенные функции](../code-quality/intrinsic-functions.md)
- [Рекомендации и примеры](../code-quality/best-practices-and-examples-sal.md)
