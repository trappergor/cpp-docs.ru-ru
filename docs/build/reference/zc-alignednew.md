---
title: "/Zc:alignedNew (c ++ 17 чрезмерно выровненных выделения) | Документы Microsoft"
ms.date: 12/14/2017
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc:alignedNew
dev_langs:
- C++
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a4d6e801b258697154a4b11c7b5e468c090cc94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (c ++ 17 чрезмерно выровненных выделения)

Поддержка C ++ 17 чрезмерно выравниваются **новый**, динамическое распределение памяти выровнены по границам больше, чем значение по умолчанию для максимального размера стандартный выровненный тип **max\_выравнивание\_t**.

## <a name="syntax"></a>Синтаксис

> **/Zc:alignedNew**[-]

## <a name="remarks"></a>Примечания

С помощью Visual Studio версии 15,5 компилятор и поддержку библиотеки C ++ 17 Стандартная чрезмерно выровненных динамическое выделение памяти. При **/Zc:alignedNew** параметра динамического выделения, таких как `new Example;` соблюдает выравнивание *пример* даже если он больше `max_align_t`, наибольшего выравнивания требуется для всех основных типов. Если выравнивание выделенного типа составляет не более, защищаемые с исходной оператор **новый**, которые доступны в качестве значения предопределенного макроса  **\_ \_STDCPP\_по умолчанию \_NEW\_ВЫРАВНИВАНИЕ\_\_**, инструкция `new Example;` приводит к вызову `::operator new(size_t)` , как в C ++ 14. Если выравнивание больше  **\_ \_STDCPP\_по умолчанию\_NEW\_ВЫРАВНИВАНИЕ\_\_**, реализация вместо получает память с помощью `::operator new(size_t, align_val_t)`. Аналогичным образом вызывает удаление чрезмерно выровненные типы `::operator delete(void*, align_val_t)` или по размеру удалить подпись `::operator delete(void*, size_t, align_val_t)`.

**/Zc:alignedNew** параметр доступен только тогда, когда [/std: c ++ 17](std-specify-language-standard-version.md) или [/std: c ++ последнюю](std-specify-language-standard-version.md) включен. В разделе **/std: c ++ 17** или **/std: c ++ последнюю**, **/Zc:alignedNew** включена по умолчанию в соответствии с ISO стандарт C ++ 17. Если единственная причина реализует оператор **новый** и **удалить** предназначен для поддержки чрезмерно выровненных выделений, этот код в C ++ 17 режиме может больше не нужна. Отключить этот параметр и вернуться к C ++ 14 поведение **новый** и **удаление** при **/std::c ++ 17** или **/std: c ++ последнюю** указан, Укажите **/Zc:alignedNew-**. При реализации оператор **новый** и **удалить** , но вы не готовы реализовать оператор чрезмерно выровненных **новый** и **удаление** перегрузок, имеющих `align_val_t` параметра, используйте **/Zc:alignedNew-** параметр для предотвращения создания компилятора и стандартной библиотеке вызовы чрезмерно выровненных перегрузки.

## <a name="example"></a>Пример

В этом примере показано, как оператор **новый** и оператор **удалить** вести, когда **/Zc:alignedNew** был установлен.

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

Этот выход является типичным для 32-разрядных сборок. Указатель, который значения изменяются в зависимости от того, где приложение выполняется в памяти.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Сведения о вопросах соответствия в Visual C++ см. в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **командной строки** на странице свойств в **C/C++** папки.

1. Изменить **Дополнительные параметры** включив **/Zc:alignedNew** или **/Zc:alignedNew-** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)  
