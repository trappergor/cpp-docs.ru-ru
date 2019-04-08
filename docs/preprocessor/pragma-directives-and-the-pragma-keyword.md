---
title: Директивы Pragma и ключевое слово __Pragma
ms.date: 11/04/2016
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
ms.openlocfilehash: b6c2ff579c6fafa78cbfd0a2879a71fca2bfaa01
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027445"
---
# <a name="pragma-directives-and-the-pragma-keyword"></a>Директивы Pragma и ключевое слово __Pragma

Директивы pragma определяют функции компилятора для конкретного компьютера или операционной системы. **__Pragma** ключевое слово, которое является специфичным для компилятора Microsoft, позволяет кодировать директивы pragma в определениях макросов.

## <a name="syntax"></a>Синтаксис

```
#pragma token-string
__pragma(token-string)
```

## <a name="remarks"></a>Примечания

Каждая реализация C и C++ поддерживает некоторые возможности, уникальные для хост-компьютера или операционной системы. Некоторые программы, например, должны осуществлять точный контроль над областями памяти, где размещаются данные, или контролировать способ получения параметров определенными функциями. **#Pragma** директивы позволяют каждому компилятору предоставлять возможности конкретного компьютера и операционной системы, сохраняя общую совместимость с языками C и C++.

Директивы pragma характерны для конкретного компьютера или операционной системы по определению и обычно отличаются для каждого компилятора. Директивы pragma можно использовать в условных операторах для обеспечения новой функциональности препроцессора или для предоставления компилятору сведений, определенных реализацией.

`token-string` — это последовательность символов, которые предоставляют определенную инструкцию компилятора и аргументы, если таковые имеются. Знак числа (**#**) должен быть первым знаком пустое пространство в строке, которая содержит директиву pragma; символы-разделители можно отделить знак числа и слово «pragma». Следуя **#pragma**, введите любой текст, который преобразователь может проанализировать как токены предварительной обработки. Аргумент **#pragma** подлежит расширению макроса.

Если компилятор обнаруживает нераспознаваемую директиву pragma, он выдает предупреждение и продолжает компиляцию.

Компиляторы Microsoft C и C++ распознают следующие директивы pragma.

||||
|-|-|-|
|[alloc_text](../preprocessor/alloc-text.md)|[auto_inline](../preprocessor/auto-inline.md)|[bss_seg](../preprocessor/bss-seg.md)|
|[check_stack](../preprocessor/check-stack.md)|[code_seg](../preprocessor/code-seg.md)|[комментарий](../preprocessor/comment-c-cpp.md)|
|[component](../preprocessor/component.md)|[соответствует](../preprocessor/conform.md) <sup>1</sup>|[const_seg](../preprocessor/const-seg.md)|
|[data_seg](../preprocessor/data-seg.md)|[deprecated](../preprocessor/deprecated-c-cpp.md)|[detect_mismatch](../preprocessor/detect-mismatch.md)|
|[fenv_access](../preprocessor/fenv-access.md)|[float_control](../preprocessor/float-control.md)|[fp_contract](../preprocessor/fp-contract.md)|
|[функцию](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include_alias](../preprocessor/include-alias.md)|
|[init_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline_depth](../preprocessor/inline-depth.md)|[inline_recursion](../preprocessor/inline-recursion.md)|
|[intrinsic](../preprocessor/intrinsic.md)|[цикл](../preprocessor/loop.md) <sup>1</sup>|[make_public](../preprocessor/make-public.md)|
|[managed](../preprocessor/managed-unmanaged.md)|[сообщение](../preprocessor/message.md)||
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers_to_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|
|[pop_macro](../preprocessor/pop-macro.md)|[push_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|
|[runtime_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|
|[strict_gs_check](../preprocessor/strict-gs-check.md)|[unmanaged](../preprocessor/managed-unmanaged.md)|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|
|[предупреждение](../preprocessor/warning.md)|||

<sup>1</sup> поддерживается только компилятором C++.

## <a name="pragmas-and-compiler-options"></a>Директивы pragma и параметры компилятора

Директивы pragma предоставляют те же функциональные возможности, что и параметры компилятора. При обнаружении директивы pragma в исходном коде она переопределяет поведение, заданное параметром компилятора. Например, если вы указали [/zp8](../build/reference/zp-struct-member-alignment.md), можно переопределить этот параметр компилятора для определенных разделов кода с помощью [пакет](../preprocessor/pack.md):

```
cl /Zp8 ...

<file> - packing is 8
// ...
#pragma pack(push, 1) - packing is now 1
// ...
#pragma pack(pop) - packing is 8
</file>
```

## <a name="the-pragma-keyword"></a>Ключевое слово __pragma()

**Блок, относящийся только к системам Microsoft**

Компилятор также поддерживает **__pragma** ключевое слово, которое имеет ту же функциональность как **#pragma** директивы, но может быть использоваться внутри определения макроса. **#Pragma** директива не может использоваться в определении макроса, так как компилятор интерпретирует символ номера (#) в директиве как [строковый оператор (#)](../preprocessor/stringizing-operator-hash.md).

В следующем примере кода показано, как **__pragma** слово может использоваться в макросе. Этот код — отрывок из заголовка mfcdual.h в образце ACDUAL, представленном в разделе "Примеры поддержки COM компилятором".

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

**Завершение блока, относящегося только к системам Microsoft**

## <a name="see-also"></a>См. также

[Cправочник препроцессора /C++](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
[Прагмы C](../c-language/c-pragmas.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)