---
title: Директивы pragma и ключевое слово __pragma
description: Описывает директивы pragma, доступные в Microsoft Visual C и C++ (КОМПИЛЯТОРОМ MSVC)
ms.date: 10/30/2020
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
ms.openlocfilehash: bf4bbdcf74808edd8ef54149f8258f47bd94c600
ms.sourcegitcommit: 4abc6c4c9694f91685cfd77940987e29a51e3143
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93238412"
---
# <a name="pragma-directives-and-the-__pragma-keyword"></a>Директивы pragma и ключевое слово __pragma

Директивы директивы pragma указывают функции компилятора для конкретного компьютера или операционной системы. Ключевое слово **__pragma** , относящееся к компилятору Майкрософт, позволяет кодировать директивы pragma в определениях макросов.

## <a name="syntax"></a>Синтаксис

> **#`pragma`***Строка токена*\
> **`__pragma(`***строка* **`)`** токена два символа подчеркивания в начале — строка расширения, определяемая корпорацией Майкрософт **`_Pragma(`** *— литерал* **`)`** //C99

## <a name="remarks"></a>Remarks

Каждая реализация C и C++ поддерживает некоторые возможности, уникальные для хост-компьютера или операционной системы. Некоторые программы, например, должны выполнять точный контроль над расположением данных в памяти или управлять способом получения параметров определенными функциями. Директивы **#pragma** предлагают каждому компилятору возможность предоставлять функции для конкретного компьютера и операционной системы, сохраняя общую совместимость с языками C и C++.

Директивы pragma являются специфическими для компьютера или операционной системы по определению и обычно отличаются для каждого компилятора. Прагмы можно использовать в условных директивах для предоставления новых функций препроцессора или для предоставления компилятору сведений, определяемых реализацией.

*Строка токена* — это последовательность символов, представляющая конкретную инструкцию компилятора и аргументы, если таковые имеются. Знак решетки ( **#** ) должен быть первым символом, не являющимся пробелом, в строке, содержащей директиву pragma. Символы пробела могут отделять знак числа и слово "pragma". После **#pragma** Запишите любой текст, который переводчик может проанализировать в виде токенов предварительной обработки. Аргумент для **#pragma** подлежит раскрытию макросов.

*Строка-литерал* — это входные данные `_Pragma` . Внешние кавычки и начальные и конечные пробелы удаляются. `\"` заменяется на `"` и `\\` заменяется на `\` .

Компилятор выдает предупреждение при обнаружении директивы pragma, которая не распознается, и возобновляет компиляцию.

Компиляторы Microsoft C и C++ распознают следующие директивы pragma.

:::row:::
   :::column span="":::
      [`alloc_text`](../preprocessor/alloc-text.md)\
      [`auto_inline`](../preprocessor/auto-inline.md)\
      [`bss_seg`](../preprocessor/bss-seg.md)\
      [`check_stack`](../preprocessor/check-stack.md)\
      [`code_seg`](../preprocessor/code-seg.md)\
      [`comment`](../preprocessor/comment-c-cpp.md)\
      [`component`](../preprocessor/component.md)\
      [`conform`](../preprocessor/conform.md)<sup>1</sup>\
      [`const_seg`](../preprocessor/const-seg.md)\
      [`data_seg`](../preprocessor/data-seg.md)\
      [`deprecated`](../preprocessor/deprecated-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`detect_mismatch`](../preprocessor/detect-mismatch.md)\
      [`fenv_access`](../preprocessor/fenv-access.md)\
      [`float_control`](../preprocessor/float-control.md)\
      [`fp_contract`](../preprocessor/fp-contract.md)\
      [`function`](../preprocessor/function-c-cpp.md)\
      [`hdrstop`](../preprocessor/hdrstop.md)\
      [`include_alias`](../preprocessor/include-alias.md)\
      [`init_seg`](../preprocessor/init-seg.md)<sup>1</sup>\
      [`inline_depth`](../preprocessor/inline-depth.md)\
      [`inline_recursion`](../preprocessor/inline-recursion.md)
   :::column-end:::
   :::column span="":::
      [`intrinsic`](../preprocessor/intrinsic.md)\
      [`loop`](../preprocessor/loop.md)<sup>1</sup>\
      [`make_public`](../preprocessor/make-public.md)\
      [`managed`](../preprocessor/managed-unmanaged.md)\
      [`message`](../preprocessor/message.md)\
      [`omp`](../preprocessor/omp.md)\
      [`once`](../preprocessor/once.md)\
      [`optimize`](../preprocessor/optimize.md)\
      [`pack`](../preprocessor/pack.md)\
      [`pointers_to_members`](../preprocessor/pointers-to-members.md)<sup>1</sup>
   :::column-end:::
   :::column span="":::
      [`pop_macro`](../preprocessor/pop-macro.md)\
      [`push_macro`](../preprocessor/push-macro.md)\
      [`region`, endregion](../preprocessor/region-endregion.md)\
      [`runtime_checks`](../preprocessor/runtime-checks.md)\
      [`section`](../preprocessor/section.md)\
      [`setlocale`](../preprocessor/setlocale.md)\
      [`strict_gs_check`](../preprocessor/strict-gs-check.md)\
      [`unmanaged`](../preprocessor/managed-unmanaged.md)\
      [`vtordisp`](../preprocessor/vtordisp.md)<sup>1</sup>\
      [`warning`](../preprocessor/warning.md)
   :::column-end:::
:::row-end:::

<sup>1</sup> поддерживается только компилятором C++.

## <a name="pragmas-and-compiler-options"></a>Директивы pragma и параметры компилятора

Директивы pragma предоставляют те же функциональные возможности, что и параметры компилятора. При обнаружении директивы pragma в исходном коде она переопределяет поведение, заданное параметром компилятора. Например, если вы указали [/Zp8](../build/reference/zp-struct-member-alignment.md), вы можете переопределить этот параметр компилятора для определенных разделов кода с помощью [Pack](../preprocessor/pack.md):

```cmd
cl /Zp8 some_file.cpp
```

```cpp
// some_file.cpp - packing is 8
// ...
#pragma pack(push, 1) - packing is now 1
// ...
#pragma pack(pop) - packing is 8 again
// ...
```

## <a name="the-__pragma-keyword"></a>Ключевое слово __pragma ()

Компилятор также поддерживает **`__pragma`** ключевое слово Microsoft, которое имеет те же функциональные возможности, что и **`#pragma`** директива. Разница заключается в том, что **`__pragma`** ключевое слово можно использовать в качестве встроенного в определении макроса. **`#pragma`** Директива не может использоваться в определении макроса, так как компилятор интерпретирует символ решетки (#) в директиве как [оператор строковый (#)](../preprocessor/stringizing-operator-hash.md).

В следующем примере кода показано, как **`__pragma`** ключевое слово может использоваться в макросе. Этот код взят из заголовка *мфкдуал. h* в образце ACDUAL в "примеры поддержки компилятора COM":

```cpp
#define CATCH_ALL_DUAL \
CATCH(COleException, e) \
{ \
_hr = e->m_sc; \
} \
AND_CATCH_ALL(e) \
{ \
__pragma(warning(push)) \
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \
AFX_MANAGE_STATE(pThis->m_pModuleState); \
__pragma(warning(pop)) \
_hr = DualHandleException(_riidSource, e); \
} \
END_CATCH_ALL \
return _hr; \
```

## <a name="the-_pragma-preprocessing-operator-c99-c11"></a>`_Pragma`Оператор предварительной обработки (C99, c++ 11)

`_Pragma` Аналогично [`__pragma`](#the-__pragma-keyword) ключевому слову Microsoft, за исключением того, что оно является частью стандарта. Он появился для C в C99. Для C++ оно было представлено в C++ 11.

 Он позволяет размещать директивы pragma в определении макроса. Он содержит одну начальную подчеркивание `_` вместо двух начальных подчеркивания `__` , которое имеет ключевое слово Microsoft, а первая буква прописной.

Строковый литерал должен быть таким же, как в противном случае после *`#pragma`* оператора. Пример:

```c
#pragma message("--the #pragma way")
_Pragma ("message( \"the _Pragma way\")") 
```

Кавычки и обратные косые черты должны быть экранированы, как показано выше. Строка директивы pragma, которая не распознана, игнорируется.

В следующем примере кода показано, как **`_Pragma`** ключевое слово можно использовать в макросе, похожем на утверждение, если не нужно получать предупреждение, если условие выражения имеет значение Constant. 

В определении макроса используется идиома do/while (0) для макросов с несколькими инструкциями, чтобы его можно было использовать, как будто это одна инструкция. Дополнительные сведения см. в разделе [Многострочный макрос на языке C](https://stackoverflow.com/questions/1067226/c-multi-line-macro-do-while0-vs-scope-block) Stack Overflow. Оператор _Pragma применяется только к строке кода, следующей за ней.

```C
// Compile with /W4

#include <stdio.h>
#include <stdlib.h>

#define MY_ASSERT(BOOL_EXPRESSION) \
    do { \
        _Pragma("warning(suppress: 4127)") /* C4127 conditional expression is constant */  \
        if (!(BOOL_EXPRESSION)) {   \
            printf("MY_ASSERT FAILED: \"" #BOOL_EXPRESSION "\" on %s(%d)", __FILE__, __LINE__); \
            exit(-1); \
        } \
    } while (0)

int main()
{
    MY_ASSERT(0 && "Note that there is no warning: C4127 conditional expression is constant");

    return 0;
}
```

## <a name="see-also"></a>См. также статью

[Справочник по препроцессору C/C++](../preprocessor/c-cpp-preprocessor-reference.md)\
[Директивы pragma](../c-language/c-pragmas.md)\
[Ключевые слова](../cpp/keywords-cpp.md)
