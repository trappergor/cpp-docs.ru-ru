---
title: /Zc:alignedNew (выделение С++17 с избыточным выравниванием)
ms.date: 05/18/2019
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: 041f62bbbf5f7a2750960d21d1534cf6daf4b874
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335684"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (выделение С++17 с избыточным выравниванием)

Включение поддержки **нового**, динамического выделения памяти с избыточным выравниванием C++17, выравниваемого по границам, превышающим значения по умолчанию для стандартного выровненного типа максимального размера, **max\_align\_t**.

## <a name="syntax"></a>Синтаксис

> **/c:alignedNew**\[-)

## <a name="remarks"></a>Remarks

Поддержка компилятором и библиотекой MSVC стандартного выделения памяти с избыточным выравниванием C++17. Когда указывается **опция /zc:alignedNew,** динамическое распределение, такое как `new Example;` согласование *Примера,* даже если оно больше, чем `max_align_t`самое большое выравнивание, необходимое для любого фундаментального типа. Когда выравнивание выделенного типа не более чем выравнивание, гарантированное новым оператором, доступно как значение `new Example;` заданного ** \_ \_макроса STDCPP\_DEFAULT\_NEW\_ALIGNMENT\_**, оператор приводит к вызову, как **new** `::operator new(size_t)` это было в C-14. Когда выравнивание `::operator new(size_t, align_val_t)`больше, чем ** \_ \_STDCPP\_DEFAULT\_NEW\_ALIGNMENT\_**, реализация вместо этого получает память с помощью . Аналогичным образом удаление типов с избыточным выравниванием вызывает `::operator delete(void*, align_val_t)` или сигнатуру удаления `::operator delete(void*, size_t, align_val_t)` с определенным размером.

Параметр **/Zc:alignedNew** доступен, только если включены [/std:c++17](std-specify-language-standard-version.md) или [/std:c++latest](std-specify-language-standard-version.md). В **/std:c++17** или **/std:c++latest****/Zc:alignedNew** включен по умолчанию для соответствия стандарту ISO C++17. Если единственной причиной реализации оператора **new** и **delete** является поддержка выделений с избыточным выравниванием, этот код может больше не требоваться в режиме C++17. Чтобы отключить этот параметр и вернуться к поведению **new** и **delete** C++14 при использовании **/std::c++17** или **/std:c++latest**, укажите **/Zc:alignedNew-**. Если вы реализуете оператор **new** и **delete**, но не готовы к реализации перегрузок оператора избыточного выравнивания **new** и **delete** с параметром `align_val_t`, используйте параметр **/Zc:alignedNew-**, чтобы запретить компилятору и стандартной библиотеке создавать вызовы к перегрузкам избыточного выравнивания. Оператор [/permissive-](permissive-standards-conformance.md) не изменяет настройку **/Zc:alignedNew** по умолчанию.

Поддержка **/Zc:alignedNew** доступна начиная с Visual Studio 2017 версии 15.5.

## <a name="example"></a>Пример

В этом примере демонстрируется поведение оператора **new** и **delete**, когда задан параметр **/Zc:alignedNew**.

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

Такой результат является типичным для 32-разрядных сборок. Значения указателя могут варьироваться в зависимости от того, где приложение выполняется в памяти.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойства **командной** > **строки** Configuration Properties**C/C'.** > 

1. Измените свойство **Дополнительные параметры**, включив параметр **/Zc:alignedNew** или **/Zc:alignedNew-**, а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также раздел

[/Zc (соответствие)](zc-conformance.md)
