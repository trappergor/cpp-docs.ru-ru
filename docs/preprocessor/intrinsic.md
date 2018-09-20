---
title: встроенные | Документация Майкрософт
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
dev_langs:
- C++
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 496971736e1f303d61b83e15b2ba1c03083f8d53
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422796"
---
# <a name="intrinsic"></a>intrinsic

Указывает, что функции, заданные в списка аргументов этой директивы, вызываются как встроенные.

## <a name="syntax"></a>Синтаксис

```cpp
#pragma intrinsic( function1 [, function2, ...] )
```

## <a name="remarks"></a>Примечания

**Внутренние** директива pragma указывает компилятору, что поведение функции известно.  Компилятор может вызвать функцию и не заменять вызов функции подставляемыми инструкциями, если это позволит повысить производительность.

Ниже перечислены функции библиотеки со встроенными формами. Один раз **внутренние** директивы, он начинает действовать с первого определения функции, содержащее указанную встроенную функцию. Ее действие продолжается до конца исходного файла, или на внешний вид `function` pragma, указав ту же встроенную функцию. **Внутренние** директива pragma может использоваться только за пределами определения функции — на глобальном уровне.

Следующие функции имеют встроенные формы, и которые используются при указании [/Oi](../build/reference/oi-generate-intrinsic-functions.md):

|||||
|-|-|-|-|
|[_disable](../intrinsics/disable.md)|[_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|
|[_enable](../intrinsics/enable.md)|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||

Программы, в которых используются встроенные функции, выполняются быстрее, поскольку они не порождают дополнительную нагрузку, связанную с вызовом функций. Однако они могут иметь больший размер, поскольку в них создается дополнительный код.

**x86 конкретных**

`_disable` И `_enable` встроенные функции создания инструкции режима ядра для прерываний и отключать и могут быть полезны в режиме ядра драйверы.

### <a name="example"></a>Пример

Скомпилируйте следующий код из командной строки с `cl -c -FAs sample.c` и просмотрите sample.asm увидите, что в x86 инструкции CLI и STI для Процессоров:

```cpp
// pragma_directive_intrinsic.cpp
// processor: x86
#include <dos.h>   // definitions for _disable, _enable
#pragma intrinsic(_disable)
#pragma intrinsic(_enable)
void f1(void) {
   _disable();
   // do some work here that should not be interrupted
   _enable();
}
int main() {
}
```

**Конец x86 конкретных**

Функции с плавающей запятой, перечисленные ниже, не имеют полноценных встроенных форм. Однако у них есть версии, позволяющие передавать аргументы напрямую в микросхему операций с плавающей запятой, а не помещать их в стек программы:

|||||
|-|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)||

 Указанные ниже функции с плавающей запятой имеют полноценных встроенных форм, при указании [/Oi](../build/reference/oi-generate-intrinsic-functions.md), [/Og](../build/reference/og-global-optimizations.md), и [/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) (или любой параметр, в котором содержится параметр: [/ Ox](../build/reference/ox-full-optimization.md), [/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md)и/O2):

|||||
|-|-|-|-|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)||||

Можно использовать [/fp: strict](../build/reference/fp-specify-floating-point-behavior.md) или [/Za](../build/reference/za-ze-disable-language-extensions.md) для переопределения поколения true встроенных параметров с плавающей запятой. В этом случае функции будут создаваться как библиотечные процедуры, которые передают аргументы напрямую в микросхему операций с плавающей запятой, а не в стек программы.

См. в разделе [#pragma function](../preprocessor/function-c-cpp.md) сведения и пример о том, как включать и отключать встроенные функции в блоке исходного текста.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)  