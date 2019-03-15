---
title: /Zc:alignedNew (c ++ 17 распределения)
ms.date: 02/28/2018
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: e0d850d54611579288b81a334af4abdfab6e411c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820342"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (c ++ 17 распределения)

Включить поддержку C ++ 17 сверх-выровненные **новый**, динамическое выделение памяти выравниваются по границам, превышающего значение по умолчанию для максимального размера standard выровненного типа, **max\_выровнять\_t**.

## <a name="syntax"></a>Синтаксис

> **/Zc:alignedNew**[-]

## <a name="remarks"></a>Примечания

С помощью Visual Studio версии 15.5 компилятор и поддержка библиотек для C ++ 17 стандартный чрезмерно выровненных динамическое выделение памяти. При **/Zc:alignedNew** параметра динамического выделения, таких как `new Example;` учитывает выравнивание *пример* даже если он больше `max_align_t`, наибольшего выравнивания требуется для любого базового типа. Когда выравнивание выделенного типа составляет не более, гарантируется исходный оператор **новый**, которые доступны для параметра предварительно определенный макрос  **\_ \_STDCPP\_по умолчанию \_NEW\_ВЫРАВНИВАНИЕ\_\_**, инструкция `new Example;` приводит к вызову для `::operator new(size_t)` , как в C ++ 14. Если выравнивание больше  **\_ \_STDCPP\_по умолчанию\_NEW\_ВЫРАВНИВАНИЕ\_\_**, реализация вместо получает память с помощью `::operator new(size_t, align_val_t)`. Аналогичным образом вызывает удаление чрезмерно выровненных типов `::operator delete(void*, align_val_t)` или размера удалить подпись `::operator delete(void*, size_t, align_val_t)`.

**/Zc:alignedNew** параметр доступен только тогда, когда [/std: c ++ 17](std-specify-language-standard-version.md) или [/std: c ++ последнюю](std-specify-language-standard-version.md) включен. В разделе **/std: c ++ 17** или **/std: c ++ последнюю**, **/Zc:alignedNew** включена по умолчанию в соответствии с ISO стандарт C ++ 17. Если единственная причина реализует оператор **новый** и **удалить** является поддержка чрезмерно выровненных выделений, могут больше не нужен этот код в режиме C ++ 17. Отключить этот параметр и вернуться к C ++ 14 поведение **новый** и **удалить** при **/std::c ++ 17** или **/std: c ++ последнюю** указан, Укажите **/Zc:alignedNew-**. Если вы реализуете оператор **новый** и **удалить** , но вы не будете готовы реализовать оператор чрезмерно выровненных **новый** и **удалить** перегрузок, имеющих `align_val_t` параметра, используйте **/Zc:alignedNew-** параметр для предотвращения создания компилятор и стандартная библиотека вызывает чрезмерно выровненных перегрузок. [/ Permissive-](permissive-standards-conformance.md) параметр не меняет значение по умолчанию **/Zc:alignedNew**.

## <a name="example"></a>Пример

В этом примере показано, как оператор **новый** и оператор **удалить** вести, когда **/Zc:alignedNew** параметр имеет значение.

```cpp
// alignedNew.cpp
// Compile by using: cl /EHsc /std:c++17 /W4 alignedNew.cpp
#include <iostream>
#include <malloc.h>
#include <new>

// "old" unaligned overloads
void* operator new(std::size_t size) {
    auto ptr = malloc(size);
    std::cout << "unaligned new(" << size << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size) {
    std::cout << "unaligned sized delete(" << ptr << ", " << size << ")\n";
    free(ptr);
}

void operator delete(void* ptr) {
    std::cout << "unaligned unsized delete(" << ptr << ")\n";
    free(ptr);
}

// "new" over-aligned overloads
void* operator new(std::size_t size, std::align_val_t align) {
    auto ptr = _aligned_malloc(size, static_cast<std::size_t>(align));
    std::cout << "aligned new(" << size << ", " <<
        static_cast<std::size_t>(align) << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size, std::align_val_t align) {
    std::cout << "aligned sized delete(" << ptr << ", " << size <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

void operator delete(void* ptr, std::align_val_t align) {
    std::cout << "aligned unsized delete(" << ptr <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

struct alignas(256) OverAligned {}; // warning C4324, structure is padded

int main() {
    delete new int;
    delete new OverAligned;
}
```

Этот результат является типичным для 32-разрядных сборках. Указатель варьироваться значения зависит от того, где приложение выполняется в памяти.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Сведения о вопросах соответствия в Visual C++, см. в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Zc:alignedNew** или **/Zc:alignedNew-** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)
