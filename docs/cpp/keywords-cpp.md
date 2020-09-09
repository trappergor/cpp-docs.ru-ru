---
title: Ключевые слова (C++)
description: Содержит ключевые слова языка C++ Standard, ключевые слова Майкрософт и ключевые слова, относящиеся к контексту.
ms.custom: index-page
ms.date: 07/25/2020
helpviewer_keywords:
- keywords [C++]
ms.assetid: d7ca94a8-f785-41ce-9f73-d3c4fd508489
ms.openlocfilehash: 96fb4e6a51630f3b5297c6428297980b5c51ca36
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609150"
---
# <a name="keywords-c"></a>Ключевые слова (C++)

Ключевые слова — это предварительно определенные зарезервированные идентификаторы, имеющие специальные значения. Их нельзя использовать в качестве идентификаторов в программе. Для Microsoft C++ зарезервированы следующие ключевые слова. Имена с начальными символами подчеркивания и именами, указанными для C++/CX и C++/CLI, являются расширениями Майкрософт.

## <a name="standard-c-keywords"></a>Стандартные ключевые слова C++

:::row:::
    :::column:::
        [`alignas`](align-cpp.md)\
        [`alignof`](alignof-operator.md)\
        [`and`](bitwise-and-operator-amp.md)<sup>б</sup>\
        [`and_eq`](assignment-operators.md)<sup>б</sup>\
        [`asm`](../assembler/inline/asm.md)<sup>объект</sup>\
        [`auto`](auto-keyword.md)\
        [`bitand`](bitwise-and-operator-amp.md)<sup>б</sup>\
        [`bitor`](bitwise-inclusive-or-operator-pipe.md)<sup>б</sup>\
        [`bool`](bool-cpp.md)\
        [`break`](break-statement-cpp.md)\
        [`case`](switch-statement-cpp.md)\
        [`catch`](try-throw-and-catch-statements-cpp.md)\
        [`char`](fundamental-types-cpp.md)\
        [`char8_t`](fundamental-types-cpp.md)<sup>c</sup>\
        [`char16_t`](char-wchar-t-char16-t-char32-t.md)\
        [`char32_t`](char-wchar-t-char16-t-char32-t.md)\
        [`class`](class-cpp.md)\
        [`compl`](one-s-complement-operator-tilde.md)<sup>б</sup>\
        **`concept`**<sup>c</sup>\
        [`const`](const-cpp.md)\
        [`const_cast`](const-cast-operator.md)\
        **`consteval`**<sup>c</sup>\
        [`constexpr`](constexpr-cpp.md)
    :::column-end:::
    :::column:::
        **`constinit`**<sup>c</sup>\
        [`continue`](continue-statement-cpp.md)\
        **`co_await`**<sup>c</sup>\
        **`co_return`**<sup>c</sup>\
        **`co_yield`**<sup>c</sup>\
        [`decltype`](decltype-cpp.md)\
        [`default`](switch-statement-cpp.md)\
        [`delete`](delete-operator-cpp.md)\
        [`do`](do-while-statement-cpp.md)\
        [`double`](fundamental-types-cpp.md)\
        [`dynamic_cast`](dynamic-cast-operator.md)\
        [`else`](if-else-statement-cpp.md)\
        [`enum`](enumerations-cpp.md)\
        [`explicit`](user-defined-type-conversions-cpp.md)\
        **`export`**<sup>c</sup>\
        [`extern`](using-extern-to-specify-linkage.md)\
        [`false`](false-cpp.md)\
        [`float`](fundamental-types-cpp.md)\
        [`for`](for-statement-cpp.md)\
        [`friend`](friend-cpp.md)\
        [`goto`](goto-statement-cpp.md)\
        [`if`](if-else-statement-cpp.md)\
        [`inline`](inline-functions-cpp.md)
    :::column-end:::
    :::column:::
        [`int`](fundamental-types-cpp.md)\
        [`long`](fundamental-types-cpp.md)\
        [`mutable`](mutable-data-members-cpp.md)\
        [`namespace`](namespaces-cpp.md)\
        [`new`](new-operator-cpp.md)\
        [`noexcept`](noexcept-cpp.md)\
        [`not`](logical-negation-operator-exclpt.md)<sup>б</sup>\
        [`not_eq`](equality-operators-equal-equal-and-exclpt-equal.md)<sup>б</sup>\
        [`nullptr`](nullptr.md)\
        [`operator`](operator-overloading.md)\
        [`or`](logical-or-operator-pipe-pipe.md)<sup>б</sup>\
        [`or_eq`](assignment-operators.md)<sup>б</sup>\
        [`private`](private-cpp.md)\
        [`protected`](protected-cpp.md)\
        [`public`](public-cpp.md)\
        [`register`](storage-classes-cpp.md#register) [`reinterpret_cast`](reinterpret-cast-operator.md)\
        **`requires`**<sup>c</sup>\
        [`return`](return-statement-cpp.md)\
        [`short`](fundamental-types-cpp.md)\
        [`signed`](fundamental-types-cpp.md)\
        [`sizeof`](sizeof-operator.md)\
        [`static`](storage-classes-cpp.md)\
        [`static_assert`](static-assert.md)
    :::column-end:::
    :::column:::
        [`static_cast`](static-cast-operator.md)\
        [`struct`](struct-cpp.md)\
        [`switch`](switch-statement-cpp.md)\
        [`template`](templates-cpp.md)\
        [`this`](this-pointer.md)\
        [`thread_local`](storage-classes-cpp.md#thread_local)\
        [`throw`](try-throw-and-catch-statements-cpp.md)\
        [`true`](true-cpp.md)\
        [`try`](try-throw-and-catch-statements-cpp.md)\
        [`typedef`](aliases-and-typedefs-cpp.md)\
        [`typeid`](typeid-operator.md)\
        [`typename`](typename.md)\
        [`union`](unions.md)\
        [`unsigned`](fundamental-types-cpp.md)\
        [`using`](using-declaration.md) повторно
        [`using`](namespaces-cpp.md#using_directives) инструкци
        [`virtual`](virtual-cpp.md)\
        [`void`](void-cpp.md)\
        [`volatile`](volatile-cpp.md)\
        [`wchar_t`](fundamental-types-cpp.md)\
        [`while`](while-statement-cpp.md)\
        [`xor`](bitwise-exclusive-or-operator-hat.md)<sup>б</sup>\
        [`xor_eq`](assignment-operators.md)<sup>б</sup>
    :::column-end:::
:::row-end:::

<sup>a</sup> **`__asm`** ключевое слово Майкрософт заменяет **`asm`** синтаксис C++. **`asm`** зарезервировано для совместимости с другими реализациями C++, но не реализовано. Используется **`__asm`** для встроенной сборки на целевых объектах x86. Microsoft C++ не поддерживает встроенную сборку для других целей.

<sup>b</sup> расширенные синонимы оператора — это ключевые слова, если [`/permissive-`](../build/reference/permissive-standards-conformance.md) заданы или [ `/Za` \( отключены языковые расширения](../build/reference/za-ze-disable-language-extensions.md) . Они не являются ключевыми словами при включении расширений Майкрософт.

<sup>c</sup> поддерживается [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) , если указан.

## <a name="microsoft-specific-c-keywords"></a>Ключевые слова Microsoft C++

В C++ идентификаторы, содержащие два последовательных символа подчеркивания, зарезервированы для реализаций компилятора. Соглашение корпорации Майкрософт — перед ключевыми словами, зависящими от корпорации Майкрософт, с двойными символами подчеркивания. Эти слова нельзя использовать в качестве имен идентификаторов.

Расширения Microsoft по умолчанию включены. Чтобы обеспечить полную переносимость программ, можно отключить расширения Майкрософт, указав [`/permissive-`](../build/reference/permissive-standards-conformance.md) параметр или [ `/Za` \( Отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) во время компиляции. Эти параметры отключают некоторые ключевые слова, относящиеся к Microsoft.

Если расширения Microsoft включены, в программах можно использовать ключевые слова, специфические для систем Microsoft. Для совместимости со стандартом ANSI эти ключевые слова начинаются с двух символов подчеркивания. Для обеспечения обратной совместимости поддерживаются версии с одним подчеркиванием многих ключевых слов с двойным подчеркиванием. **`__cdecl`** Ключевое слово доступно без символа подчеркивания в начале.

**`__asm`** Ключевое слово заменяет **`asm`** синтаксис C++. **`asm`** зарезервировано для совместимости с другими реализациями C++, но не реализовано. Используйте **`__asm`**.

**`__based`** Ключевое слово имеет ограниченное использование для целевых компиляций с 32-и 64-битным целевым объектом.

:::row:::
    :::column:::
        [`__alignof`](alignof-operator.md)<sup>д</sup>\
        [`__asm`](../assembler/inline/asm.md)<sup>д</sup>\
        [`__assume`](../intrinsics/assume.md)<sup>д</sup>\
        [`__based`](based-pointers-cpp.md)<sup>д</sup>\
        [`__cdecl`](cdecl.md)<sup>д</sup>\
        [`__declspec`](declspec.md)<sup>д</sup>\
        [`__event`](event.md)\
        [`__except`](try-except-statement.md)<sup>д</sup>\
        [`__fastcall`](fastcall.md)<sup>д</sup>\
        [`__finally`](try-finally-statement.md)<sup>д</sup>\
        [`__forceinline`](inline-functions-cpp.md)<sup>д</sup>
    :::column-end:::
    :::column:::
        [`__hook`](hook.md)<sup>г</sup>\
        [`__if_exists`](if-exists-statement.md)\
        [`__if_not_exists`](if-not-exists-statement.md)\
        [`__inline`](inline-functions-cpp.md)<sup>д</sup>\
        [`__int16`](int8-int16-int32-int64.md)<sup>д</sup>\
        [`__int32`](int8-int16-int32-int64.md)<sup>д</sup>\
        [`__int64`](int8-int16-int32-int64.md)<sup>д</sup>\
        [`__int8`](int8-int16-int32-int64.md)<sup>д</sup>\
        [`__interface`](interface.md)\
        [`__leave`](try-finally-statement.md)<sup>д</sup>\
        [`__m128`](m128.md)
    :::column-end:::
    :::column:::
        [`__m128d`](m128d.md)\
        [`__m128i`](m128i.md)\
        [`__m64`](m64.md)\
        [`__multiple_inheritance`](inheritance-keywords.md)<sup>д</sup>\
        [`__ptr32`](ptr32-ptr64.md)<sup>д</sup>\
        [`__ptr64`](ptr32-ptr64.md)<sup>&</sup>\
        [`__raise`](raise.md)\
        [`__restrict`](extension-restrict.md)<sup>д</sup>\
        [`__single_inheritance`](inheritance-keywords.md)<sup>&</sup>\
        [`__sptr`](sptr-uptr.md)<sup>&</sup>\
        [`__stdcall`](stdcall.md)<sup>д</sup>
    :::column-end:::
    :::column:::
        [`__super`](super.md)\
        [`__thiscall`](thiscall.md)\
        [`__unaligned`](unaligned.md)<sup>д</sup>\
        [`__unhook`](unhook.md)<sup>г</sup>\
        [`__uptr`](sptr-uptr.md)<sup>д</sup>\
        [`__uuidof`](uuidof-operator.md)<sup>д</sup>\
        [`__vectorcall`](vectorcall.md)<sup>д</sup>\
        [`__virtual_inheritance`](inheritance-keywords.md)<sup>д</sup>\
        [`__w64`](w64.md)<sup>д</sup>\
        [`__wchar_t`](fundamental-types-cpp.md)
    :::column-end:::
:::row-end:::

Встроенная функция <sup>d</sup> , используемая при обработке событий.

<sup>д</sup> . для обратной совместимости с предыдущими версиями эти ключевые слова доступны как с двумя символами подчеркивания в начале, так и с одним символом подчеркивания в начале, если включены расширения Майкрософт (по умолчанию).

## <a name="microsoft-keywords-in-__declspec-modifiers"></a>Ключевые слова Майкрософт в модификаторах __declspec

Эти идентификаторы являются расширенными атрибутами для **`__declspec`** модификатора. Они считаются ключевыми словами в этом контексте.

:::row:::
    :::column:::
        [`align`](align-cpp.md)\
        [`allocate`](allocate.md)\
        [`allocator`](allocator.md)\
        [`appdomain`](appdomain.md)\
        [`code_seg`](code-seg-declspec.md)\
        [`deprecated`](deprecated-cpp.md)
    :::column-end:::
    :::column:::
        [`dllexport`](dllexport-dllimport.md)\
        [`dllimport`](dllexport-dllimport.md)\
        [`jitintrinsic`](jitintrinsic.md)\
        [`naked`](naked-cpp.md)\
        [`noalias`](noalias.md)\
        [`noinline`](noinline.md)
    :::column-end:::
    :::column:::
        [`noreturn`](noreturn.md)\
        [`nothrow`](nothrow-cpp.md)\
        [`novtable`](novtable.md)\
        [`process`](process.md)\
        [`property`](property-cpp.md)\
        [`restrict`](restrict.md)
    :::column-end:::
    :::column:::
        [`safebuffers`](safebuffers.md)\
        [`selectany`](selectany.md)\
        [`spectre`](spectre.md)\
        [`thread`](thread.md)\
        [`uuid`](uuid-cpp.md)
    :::column-end:::
:::row-end:::

## <a name="ccli-and-ccx-keywords"></a>Ключевые слова c++/CLI и C++/CX

:::row:::
    :::column:::
        [`__abstract`](../dotnet/declaration-of-a-managed-class-type.md)<sup>f</sup>\
        [`__box`](../dotnet/value-type-semantics.md)<sup>f</sup>\
        [`__delegate`](../dotnet/delegates-and-events.md)<sup>f</sup>\
        [`__gc`](../dotnet/declaration-of-a-clr-reference-class-object.md)<sup>f</sup>\
        [`__identifier`](../extensions/identifier-cpp-cli.md)\
        [`__nogc`](../dotnet/declaration-of-a-clr-reference-class-object.md)<sup>f</sup>\
        [`__noop`](../intrinsics/noop.md)\
        **`__pin`**<sup>f</sup>\
        **`__property`**<sup>f</sup>\
        **`__sealed`**<sup>f</sup>
    :::column-end:::
    :::column:::
        [`__try_cast`](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)<sup>f</sup>\
        [`__value`](../dotnet/value-type-semantics.md)<sup>f</sup>\
        [`abstract`](../extensions/abstract-cpp-component-extensions.md)<sup>ж</sup>\
        [`array`](../extensions/arrays-cpp-component-extensions.md)<sup>ж</sup>\
        [`as_friend`](../preprocessor/hash-using-directive-cpp.md)\
        [`delegate`](../extensions/delegate-cpp-component-extensions.md)<sup>ж</sup>\
        [`enum class`](../extensions/enum-class-cpp-component-extensions.md)\
        [`enum struct`](../extensions/enum-class-cpp-component-extensions.md)\
        [`event`](../extensions/event-cpp-component-extensions.md)<sup>ж</sup>
    :::column-end:::
    :::column:::
        [`finally`](../dotnet/finally.md)\
        [`for each in`](../dotnet/for-each-in.md)\
        [`gcnew`](../extensions/ref-new-gcnew-cpp-component-extensions.md)<sup>ж</sup>\
        [`generic`](../extensions/generics-cpp-component-extensions.md)<sup>ж</sup>\
        [`initonly`](../dotnet/initonly-cpp-cli.md)\
        [`interface class`](../extensions/interface-class-cpp-component-extensions.md)<sup>ж</sup>\
        [`interface struct`](../extensions/interface-class-cpp-component-extensions.md)<sup>ж</sup>\
        [`interior_ptr`](../extensions/interior-ptr-cpp-cli.md)<sup>ж</sup>\
        [`literal`](../extensions/literal-cpp-component-extensions.md)<sup>ж</sup>
    :::column-end:::
    :::column:::
        [`new`](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)<sup>ж</sup>\
        [`property`](../extensions/property-cpp-component-extensions.md)<sup>ж</sup>\
        [`ref class`](../extensions/classes-and-structs-cpp-component-extensions.md)\
        [`ref struct`](../extensions/classes-and-structs-cpp-component-extensions.md)\
        [`safecast`](../extensions/safe-cast-cpp-component-extensions.md)\
        [`sealed`](../extensions/sealed-cpp-component-extensions.md)<sup>ж</sup>\
        [`typeid`](../extensions/typeid-cpp-component-extensions.md)\
        [`value class`](../extensions/classes-and-structs-cpp-component-extensions.md)<sup>ж</sup>\
        [`value struct`](../extensions/classes-and-structs-cpp-component-extensions.md)<sup>ж</sup>
    :::column-end:::
:::row-end:::

<sup>f</sup> применим только к управляемые расширения для C++. В настоящее время использование этого синтаксиса не рекомендуется. Дополнительные сведения см. в статье [Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md).

<sup>g</sup> применимо к C++/CLI.

## <a name="see-also"></a>См. также раздел

[Лексические соглашения](lexical-conventions.md)<br/>
[Встроенные операторы, приоритет и ассоциативность C++](cpp-built-in-operators-precedence-and-associativity.md)
