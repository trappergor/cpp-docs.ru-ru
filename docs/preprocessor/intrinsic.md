---
title: Прагма intrinsic
ms.date: 08/29/2019
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
ms.openlocfilehash: bb4403abf5e278ed3727af660579e22ab69592c7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220938"
---
# <a name="intrinsic-pragma"></a>Прагма intrinsic

Указывает, что функции, заданные в списка аргументов этой директивы, вызываются как встроенные.

## <a name="syntax"></a>Синтаксис

> **Встроенная #pragma (** *функция1* [ **,** _функция2_ ...] **)**

## <a name="remarks"></a>Примечания

**Встроенная** директива pragma сообщает компилятору, что функция имеет известное поведение. Компилятор может вызвать функцию и не заменять вызов функции подставляемыми инструкциями, если это позволит повысить производительность.

Ниже перечислены функции библиотеки со встроенными формами. После того как встроенная директива pragma будет показана, она вступает в силу в первом определении функции, содержащей указанную подставляемую функцию. Результат переходит в конец исходного файла или на внешний вид `function` директивы pragma, указывающей ту же встроенную функцию. **Встроенная** директива pragma может использоваться только за пределами определения функции на глобальном уровне.

Следующие функции имеют встроенные формы, а внутренние формы используются при указании [/Oi](../build/reference/oi-generate-intrinsic-functions.md):

|||||
|-|-|-|-|
|[_disable](../intrinsics/disable.md)|[_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|
|[_enable](../intrinsics/enable.md)|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||

Программы, использующие встроенные функции, выполняются быстрее, так как они не имеют издержек вызовов функций, но могут быть больше из-за создания дополнительного кода.

**Только для x86**

Встроенная `_enable` функция исоздаетинструкциирежимаядрадляотключенияиливключенияпрерыванийиможетбытьполезнавдрайверахрежимаядра.`_disable`

### <a name="example"></a>Пример

Скомпилируйте следующий код из командной строки с помощью `cl -c -FAs sample.c` и взгляните на Sample. ASM, чтобы увидеть, что они включают в себя команды CLI для x86 и сти:

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

**Только для платформы x86**

Перечисленные ниже функции с плавающей запятой не имеют истинных встроенных форм. Однако у них есть версии, позволяющие передавать аргументы напрямую в микросхему операций с плавающей запятой, а не помещать их в стек программы:

|||||
|-|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)||

Перечисленные ниже функции с плавающей запятой имеют истинные встроенные формы при указании [/Oi](../build/reference/oi-generate-intrinsic-functions.md), [/Og](../build/reference/og-global-optimizations.md)и [/FP: Fast](../build/reference/fp-specify-floating-point-behavior.md) (или любого параметра, включающего/OG: [/Ox](../build/reference/ox-full-optimization.md), [/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md)и [/O2](../build/reference/o1-o2-minimize-size-maximize-speed.md)):

|||||
|-|-|-|-|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)||||

Можно использовать [/FP:](../build/reference/fp-specify-floating-point-behavior.md) with или [/Za](../build/reference/za-ze-disable-language-extensions.md) для переопределения создания истинных встроенных параметров с плавающей запятой. В этом случае функции будут создаваться как библиотечные процедуры, которые передают аргументы напрямую в микросхему операций с плавающей запятой, а не в стек программы.

Сведения и пример включения и отключения встроенных функций для блока исходного текста см. в разделе [#pragma функция](../preprocessor/function-c-cpp.md) .

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)
